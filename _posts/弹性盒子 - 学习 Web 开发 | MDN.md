> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [developer.mozilla.org](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)

[MDN Web DocsClear search inputSearchTheme](/zh-CN/)

[](/zh-CN/)*   [](/zh-CN/)[Already a subscriber?](/users/fxa/login/authenticate/?next=%2Fzh-CN%2Fdocs%2FLearn%2FCSS%2FCSS_layout%2FFlexbox)
*   [Get MDN Plus](/zh-CN/plus)

1.  [学习 Web 开发](/zh-CN/docs/Learn)
2.  [CSS](/zh-CN/docs/Learn/CSS)
3.  [CSS 布局](/zh-CN/docs/Learn/CSS/CSS_layout)
4.  [弹性盒子](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)

Article Actions

*   中文 (简体)

[此页面由社区从英文翻译而来。了解更多并加入 MDN Web Docs 社区。](/zh-CN/docs/MDN/Community/Contributing/Translated_content#活跃语言)

In this article
---------------

*   [为什么是弹性盒子？](#为什么是弹性盒子？)
*   [一个简单的例子](#一个简单的例子)
*   [指定元素的布局为 flexible](#指定元素的布局为_flexible)
*   [flex 模型说明](#flex_模型说明)
*   [列还是行？](#列还是行？)
*   [换行](#换行)
*   [flex-flow 缩写](#flex-flow_缩写)
*   [flex 项的动态尺寸](#flex_项的动态尺寸)
*   [flex：缩写与全写](#flex：缩写与全写)
*   [水平和垂直对齐](#水平和垂直对齐)
*   [flex 项排序](#flex_项排序)
*   [flex 嵌套](#flex_嵌套)
*   [跨浏览器兼容性](#跨浏览器兼容性)
*   [测试你的技能](#测试你的技能)
*   [总结](#总结)
*   [参见](#参见)
*   [模块](#模块)

#### Related Topics

1.  [**新手请从这开始！**](/zh-CN/docs/Learn/Getting_started_with_the_web)
2.  Web 入门
    
    1.  [Web 概述](/zh-CN/docs/Learn/Getting_started_with_the_web)
    2.  [安装基本软件](/zh-CN/docs/Learn/Getting_started_with_the_web/Installing_basic_software)
    3.  [你的网站会是什么样？](/zh-CN/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)
    4.  [处理文件](/zh-CN/docs/Learn/Getting_started_with_the_web/Dealing_with_files)
    5.  [HTML 基础](/zh-CN/docs/Learn/Getting_started_with_the_web/HTML_basics)
    6.  [CSS 基础](/zh-CN/docs/Learn/Getting_started_with_the_web/CSS_basics)
    7.  [JavaScript 基础](/zh-CN/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
    8.  [发布你的网站](/zh-CN/docs/Learn/Getting_started_with_the_web/Publishing_your_website)
    9.  [Web 如何运作](/zh-CN/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
    
3.  [**HTML——构建 Web**](/zh-CN/docs/Learn/HTML)
4.  HTML 介绍
    
    1.  [HTML 概述](/zh-CN/docs/Learn/HTML/Introduction_to_HTML)
    2.  [开始学习 HTML](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
    3.  [head 标签里面有什么？HTML 中的元数据](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)
    4.  [HTML 文本基础](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)
    5.  [建立超链接](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
    6.  [高级文本格式](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)
    7.  [文档和网站架构](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
    8.  [HTML 调试](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML)
    9.  [测验：标记信件](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Marking_up_a_letter)
    10.  [测验：构建网页内容](/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Structuring_a_page_of_content)
    
5.  多媒体与嵌入
    
    1.  [多媒体与嵌入概述](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding)
    2.  [HTML 中的图片](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
    3.  [视频和音频内容](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
    4.  [从对象到 iframe——其他嵌入技术](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies)
    5.  [为 Web 新增矢量图](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web)
    6.  [响应式图片](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
    7.  [测验：Mozilla 醒目页面](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Mozilla_splash_page)
    
6.  HTML 表格
    
    1.  [HTML 表格概述](/zh-CN/docs/Learn/HTML/Tables)
    2.  [HTML 表格基础](/zh-CN/docs/Learn/HTML/Tables/Basics)
    3.  [HTML 高级表格特性和无障碍](/zh-CN/docs/Learn/HTML/Tables/Advanced)
    4.  [测验：构建行星数据](/zh-CN/docs/Learn/HTML/Tables/Structuring_planet_data)
    
7.  [**CSS——设计 Web**](/zh-CN/docs/Learn/CSS)
8.  CSS 第一步
    
    1.  [CSS 第一步概述](/zh-CN/docs/Learn/CSS/First_steps)
    2.  [什么是 CSS](/zh-CN/docs/Learn/CSS/First_steps/What_is_CSS)
    3.  [让我们开始 CSS 之旅](/zh-CN/docs/Learn/CSS/First_steps/Getting_started)
    4.  [如何构建 CSS](/zh-CN/docs/Learn/CSS/First_steps/How_CSS_is_structured)
    5.  [CSS 如何运行](/zh-CN/docs/Learn/CSS/First_steps/How_CSS_works)
    6.  [测验：传记页的风格设计](/zh-CN/docs/Learn/CSS/First_steps/Styling_a_biography_page)
    
9.  CSS 构建基础
    
    1.  [CSS 构建基础概述](/zh-CN/docs/Learn/CSS/Building_blocks)
    2.  [层叠与继承](/zh-CN/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
    3.  [CSS 选择器](/zh-CN/docs/Learn/CSS/Building_blocks/Selectors)
    4.  [盒模型](/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model)
    5.  [背景与边框](/zh-CN/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)
    6.  [处理不同方向的文本](/zh-CN/docs/Learn/CSS/Building_blocks/Handling_different_text_directions)
    7.  [溢出的内容](/zh-CN/docs/Learn/CSS/Building_blocks/Overflowing_content)
    8.  [CSS 值和单位](/zh-CN/docs/Learn/CSS/Building_blocks/Values_and_units)
    9.  [在 CSS 中调整大小](/zh-CN/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS)
    10.  [图像、媒体和表单元素](/zh-CN/docs/Learn/CSS/Building_blocks/Images_media_form_elements)
    11.  [样式化表格](/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables)
    12.  [调试 CSS](/zh-CN/docs/Learn/CSS/Building_blocks/Debugging_CSS)
    13.  [组织你的 CSS](/zh-CN/docs/Learn/CSS/Building_blocks/Organizing)
    14.  [测验：CSS 基础理解](/zh-CN/docs/Learn/CSS/Building_blocks/Fundamental_CSS_comprehension)
    15.  [测验：制作精美的信纸](/zh-CN/docs/Learn/CSS/Building_blocks/Creating_fancy_letterheaded_paper)
    16.  [测验：看起来很酷的盒子](/zh-CN/docs/Learn/CSS/Building_blocks/A_cool_looking_box)
    
10.  样式化文本
    
    1.  [样式化文本概述](/zh-CN/docs/Learn/CSS/Styling_text)
    2.  [基础文本与字体样式化](/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals)
    3.  [样式化列表](/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists)
    4.  [样式化链接](/zh-CN/docs/Learn/CSS/Styling_text/Styling_links)
    5.  [Web 字体](/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts)
    6.  [测验：排版社区大学首页](/zh-CN/docs/Learn/CSS/Styling_text/Typesetting_a_homepage)
    
11.  CSS 排版
    
    1.  [CSS 排版概述](/zh-CN/docs/Learn/CSS/CSS_layout)
    2.  [CSS 布局简介](/zh-CN/docs/Learn/CSS/CSS_layout/Introduction)
    3.  [正常布局流](/zh-CN/docs/Learn/CSS/CSS_layout/Normal_Flow)
    4.  _[弹性区块](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)_
    5.  [网格](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)
    6.  [浮动](/zh-CN/docs/Learn/CSS/CSS_layout/Floats)
    7.  [定位](/zh-CN/docs/Learn/CSS/CSS_layout/Positioning)
    8.  [多栏式布局](/zh-CN/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
    9.  [响应式设计](/zh-CN/docs/Learn/CSS/CSS_layout/Responsive_Design)
    10.  [媒体查询](/zh-CN/docs/Learn/CSS/CSS_layout/Media_queries)
    11.  [传统的布局方法](/zh-CN/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)
    12.  [支持旧版浏览器](/zh-CN/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers)
    13.  [测验：对布局基础知识的理解](/zh-CN/docs/Learn/CSS/CSS_layout/Fundamental_Layout_Comprehension)
    
12.  [**JavaScript——用户端动态脚本**](/zh-CN/docs/Learn/JavaScript)
13.  JavaScript 第一步
    
    1.  [JavaScript 第一步概述](/zh-CN/docs/Learn/JavaScript/First_steps)
    2.  [什么是 JavaScript？](/zh-CN/docs/Learn/JavaScript/First_steps/What_is_JavaScript)
    3.  [初次接触 JavaScript](/zh-CN/docs/Learn/JavaScript/First_steps/A_first_splash)
    4.  [出现了什么问题？JavaScript 疑难解答](/zh-CN/docs/Learn/JavaScript/First_steps/What_went_wrong)
    5.  [储存你所需的信息——变量](/zh-CN/docs/Learn/JavaScript/First_steps/Variables)
    6.  [JavaScript 基础概念——数字与运算符](/zh-CN/docs/Learn/JavaScript/First_steps/Math)
    7.  [文本处理——JavaScript 中的字符串](/zh-CN/docs/Learn/JavaScript/First_steps/Strings)
    8.  [有用的字符串方法](/zh-CN/docs/Learn/JavaScript/First_steps/Useful_string_methods)
    9.  [数组](/zh-CN/docs/Learn/JavaScript/First_steps/Arrays)
    10.  [测验：傻瓜故事产生器](/zh-CN/docs/Learn/JavaScript/First_steps/Silly_story_generator)
    
14.  JavaScript 基础要件
    
    1.  [JavaScript 基础要件概述](/zh-CN/docs/Learn/JavaScript/Building_blocks)
    2.  [在代码中决策——条件](/zh-CN/docs/Learn/JavaScript/Building_blocks/conditionals)
    3.  [代码循环](/zh-CN/docs/Learn/JavaScript/Building_blocks/Looping_code)
    4.  [函数 - 可重复利用的代码块](/zh-CN/docs/Learn/JavaScript/Building_blocks/Functions)
    5.  [建立自己的函数](/zh-CN/docs/Learn/JavaScript/Building_blocks/Build_your_own_function)
    6.  [函数返回值](/zh-CN/docs/Learn/JavaScript/Building_blocks/Return_values)
    7.  [事件介绍](/zh-CN/docs/Learn/JavaScript/Building_blocks/Events)
    8.  [测验：图库](/zh-CN/docs/Learn/JavaScript/Building_blocks/Image_gallery)
    
15.  JavaScript 对象介绍
    
    1.  [JavaScript 对象概述](/zh-CN/docs/Learn/JavaScript/Objects)
    2.  [对象基础概念](/zh-CN/docs/Learn/JavaScript/Objects/Basics)
    3.  [对象原型](/zh-CN/docs/Learn/JavaScript/Objects/Object_prototypes)
    4.  [面向对象编程基本概念](/zh-CN/docs/Learn/JavaScript/Objects/Object-oriented_programming)
    5.  [JavaScript 中的类](/zh-CN/docs/Learn/JavaScript/Objects/Classes_in_JavaScript)
    6.  [使用 JSON 数据](/zh-CN/docs/Learn/JavaScript/Objects/JSON)
    7.  [对象构建实践](/zh-CN/docs/Learn/JavaScript/Objects/Object_building_practice)
    8.  [测验：为弹球示例新增功能](/zh-CN/docs/Learn/JavaScript/Objects/Adding_bouncing_balls_features)
    
16.  异步 JavaScript
    
    1.  [异步 JavaScript 概述](/zh-CN/docs/Learn/JavaScript/Asynchronous)
    2.  [异步 JavaScript 简介](/zh-CN/docs/Learn/JavaScript/Asynchronous/Introducing)
    3.  [如何使用 promise](/zh-CN/docs/Learn/JavaScript/Asynchronous/Promises)
    4.  [实现基于 promise 的 API](/zh-CN/docs/Learn/JavaScript/Asynchronous/Implementing_a_promise-based_API)
    5.  [worker 简介](/zh-CN/docs/Learn/JavaScript/Asynchronous/Introducing_workers)
    6.  [测验：序列动画](/zh-CN/docs/Learn/JavaScript/Asynchronous/Sequencing_animations)
    
17.  客户端 Web API
    
    1.  [客户端 Web API](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs)
    2.  [客户端 Web API 简介](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)
    3.  [操作文档](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents)
    4.  [从服务器获取数据](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)
    5.  [第三方 API](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Third_party_APIs)
    6.  [画图](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Drawing_graphics)
    7.  [视频与音频 API](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
    8.  [客户端存储](/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage)
    
18.  [**Web 表单——与用户数据打交道**](/zh-CN/docs/Learn/Forms)
19.  Web 表单核心
    
    1.  [Web 表单概述](/zh-CN/docs/Learn/Forms)
    2.  [你的第一个表单](/zh-CN/docs/Learn/Forms/Your_first_form)
    3.  [如何构造 Web 表单](/zh-CN/docs/Learn/Forms/How_to_structure_a_web_form)
    4.  [原生表单控件](/zh-CN/docs/Learn/Forms/Basic_native_form_controls)
    5.  [HTML5 的 input 类型](/zh-CN/docs/Learn/Forms/HTML5_input_types)
    6.  [其它表单控件](/zh-CN/docs/Learn/Forms/Other_form_controls)
    7.  [样式化 Web 表单](/zh-CN/docs/Learn/Forms/Styling_web_forms)
    8.  [高级表单样式](/zh-CN/docs/Learn/Forms/Advanced_form_styling)
    9.  [UI 伪类](/zh-CN/docs/Learn/Forms/UI_pseudo-classes)
    10.  [客户端表单验证](/zh-CN/docs/Learn/Forms/Form_validation)
    11.  [发送表单数据](/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data)
    
20.  Web表单进阶
    
    1.  [如何构造自定义表单控件](/zh-CN/docs/Learn/Forms/How_to_build_custom_form_controls)
    2.  [使用 JavaScript 发送表单](/zh-CN/docs/Learn/Forms/Sending_forms_through_JavaScript)
    3.  [表单组件兼容性列表](/zh-CN/docs/Learn/Forms/Property_compatibility_table_for_form_controls)
    
21.  [**无障碍——使每个人都能使用 Web**](/zh-CN/docs/Learn/Accessibility)
22.  无障碍指南
    
    1.  [无障碍概述](/zh-CN/docs/Learn/Accessibility)
    2.  [什么是无障碍](/zh-CN/docs/Learn/Accessibility/What_is_accessibility)
    3.  [HTML: 无障碍的好基础](/zh-CN/docs/Learn/Accessibility/HTML)
    4.  [CSS 和 JavaScript 无障碍最佳实践](/zh-CN/docs/Learn/Accessibility/CSS_and_JavaScript)
    5.  [WAI-ARIA 基础](/zh-CN/docs/Learn/Accessibility/WAI-ARIA_basics)
    6.  [多媒体无障碍](/zh-CN/docs/Learn/Accessibility/Multimedia)
    7.  [移动端无障碍](/zh-CN/docs/Learn/Accessibility/Mobile)
    
23.  无障碍测评
    
    1.  [测验：无障碍疑难解答](/zh-CN/docs/Learn/Accessibility/Accessibility_troubleshooting)
    
24.  [**MathML — Writing mathematics with MathML**](/zh-CN/docs/Learn/MathML)
25.  MathML first steps
    
    1.  [MathML first steps overview](/zh-CN/docs/Learn/MathML/First_steps)
    2.  [Getting started with MathML](/zh-CN/docs/Learn/MathML/First_steps/Getting_started)
    3.  [Assessment: Three famous mathematical formulas](/zh-CN/docs/Learn/MathML/First_steps/Three_famous_mathematical_formulas)
    
26.  [**工具与测试**](/zh-CN/docs/Learn/Tools_and_testing)
27.  客户端 web 开发工具
    
    1.  [客户端 web 开发工具索引](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools)
    2.  [客户端工具概述](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview)
    3.  [命令行速成课](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
    4.  [包管理基础](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management)
    5.  [一个完整的工具链](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Introducing_complete_toolchain)
    6.  [发布你的应用](/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Deployment)
    
28.  客户端框架介绍
    
    1.  [客户端框架概述](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction)
    2.  [框架的主要特性](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features)
    
29.  React
    
    1.  [React 入门](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started)
    2.  [开始我们的 React 待办清单](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning)
    3.  [组合我们的 React 应用](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components)
    4.  [React 交互：事件和状态](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state)
    5.  [React 交互：编辑、筛选、条件渲染](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering)
    6.  [React 中的无障碍](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility)
    7.  [React 资源](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources)
    
30.  Ember
    
    1.  [Ember 入门](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_getting_started)
    2.  [Ember 应用结构和组成](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_structure_componentization)
    3.  [Ember 交互：事件、类和状态](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_interactivity_events_state)
    4.  [Ember Interactivity: Footer functionality, conditional rendering](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_conditional_footer)
    5.  [Ember 路由](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_routing)
    6.  [Ember 资源和常见问题](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_resources)
    
31.  Vue
    
    1.  [开始使用 Vue](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_getting_started)
    2.  [创建第一个 Vue 组件](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_first_component)
    3.  [渲染一个 Vue 组件列表](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_rendering_lists)
    4.  [添加一个新的待办表单: Vue 事件、方法、模型](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_methods_events_models)
    5.  [用 CSS 样式化 Vue 组件](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_styling)
    6.  [使用 Vue 计算属性](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_computed_properties)
    7.  [Vue 条件渲染：编辑存在的待办清单](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_conditional_rendering  )
    8.  [使用 Vue ref 进行管理](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_refs_focus_management)
    9.  [Vue 资源](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_resources)
    
32.  Svelte
    
    1.  [Svelte 入门](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_getting_started)
    2.  [开始我们的 Svelte 待办清单应用](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_Todo_list_beginning)
    3.  [Svelte 动态表现：变量和 props](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_variables_props)
    4.  [组织我们的 Svelte 应用](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_components)
    5.  [高级 Svelte：响应式、生命周期和无障碍](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_reactivity_lifecycle_accessibility)
    6.  [Svelte 存储](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_stores)
    7.  [Svelte 对 TypeScript 的支持](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_TypeScript  )
    8.  [部署和下一步](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_deployment_next)
    
33.  Angular
    
    1.  [Angular 入门](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_getting_started)
    2.  [开始我们的 Angular todo 列表应用](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_todo_list_beginning)
    3.  [样式化我们的 Angular 应用](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_styling)
    4.  [创建一个事项组件](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_item_component)
    5.  [筛选 todo 事项](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_filtering)
    6.  [构建 Angular 应用以及更多资源](/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Angular_building)
    
34.  Git 和 GitHub
    
    1.  [Git 和 GitHub 概述](/zh-CN/docs/Learn/Tools_and_testing/GitHub)
    2.  [Hello World](https://guides.github.com/activities/hello-world/)
    3.  [Git Handbook](https://guides.github.com/introduction/git-handbook/)
    4.  [Forking Projects](https://guides.github.com/activities/forking/)
    5.  [About pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)
    6.  [Mastering Issues](https://guides.github.com/features/issues/)
    
35.  跨浏览器测试
    
    1.  [跨浏览器测试概述](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing)
    2.  [跨浏览器测试介绍](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Introduction)
    3.  [执行测试策略](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Testing_strategies)
    4.  [处理常见的 HTML 与 CSS 问题](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/HTML_and_CSS)
    5.  [处理常见的 JavaScript 问题](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/JavaScript)
    6.  [处理常见的无障碍问题](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility)
    7.  [建置功能侦测](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)
    8.  [自动测试介绍](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Automated_testing)
    9.  [设置你的自动测试环境](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Your_own_automation_environment)
    
36.  [**服务端网页编程**](/zh-CN/docs/Learn/Server-side)
37.  第一步
    
    1.  [第一步概述](/zh-CN/docs/Learn/Server-side/First_steps)
    2.  [服务端介绍](/zh-CN/docs/Learn/Server-side/First_steps/Introduction)
    3.  [用户端概述](/zh-CN/docs/Learn/Server-side/First_steps/Client-Server_overview)
    4.  [服务端网络框架](/zh-CN/docs/Learn/Server-side/First_steps/Web_frameworks)
    5.  [网站安全](/zh-CN/docs/Learn/Server-side/First_steps/Website_security)
    
38.  Django 网站框架 (Python)
    
    1.  [Django 网站框架 (Python) 概述](/zh-CN/docs/Learn/Server-side/Django)
    2.  [介绍](/zh-CN/docs/Learn/Server-side/Django/Introduction)
    3.  [搭建开发环境](/zh-CN/docs/Learn/Server-side/Django/development_environment)
    4.  [在线教学：本地图书馆网站](/zh-CN/docs/Learn/Server-side/Django/Tutorial_local_library_website)
    5.  [在线教学 2：建立网站框架](/zh-CN/docs/Learn/Server-side/Django/skeleton_website)
    6.  [在线教学 3：使用模型](/zh-CN/docs/Learn/Server-side/Django/Models)
    7.  [在线教学 4：Django 管理网站](/zh-CN/docs/Learn/Server-side/Django/Admin_site)
    8.  [在线教学 5：建立我们的首页](/zh-CN/docs/Learn/Server-side/Django/Home_page)
    9.  [在线教学 6：通用列表与细节检查](/zh-CN/docs/Learn/Server-side/Django/Generic_views)
    10.  [在线教学 7：会话框架](/zh-CN/docs/Learn/Server-side/Django/Sessions)
    11.  [在线教学 8：用户授权与许可](/zh-CN/docs/Learn/Server-side/Django/Authentication)
    12.  [在线教学 9：搭配表单](/zh-CN/docs/Learn/Server-side/Django/Forms)
    13.  [在线教学 10：测试 Django 的 Web 应用](/zh-CN/docs/Learn/Server-side/Django/Testing)
    14.  [在线教学 11：部署 Django 至产品](/zh-CN/docs/Learn/Server-side/Django/Deployment)
    15.  [Web 应用安全性](/zh-CN/docs/Learn/Server-side/Django/web_application_security)
    16.  [测验：DIY 博客](/zh-CN/docs/Learn/Server-side/Django/django_assessment_blog)
    
39.  Express 网页框架 (node.js/JavaScript)
    
    1.  [Express 网页框架 (Node.js/JavaScript) 概述](/zh-CN/docs/Learn/Server-side/Express_Nodejs)
    2.  [Express/Node 介绍](/zh-CN/docs/Learn/Server-side/Express_Nodejs/Introduction)
    3.  [架设 Node (Express) 开发环境](/zh-CN/docs/Learn/Server-side/Express_Nodejs/development_environment)
    4.  [Express 教程： 本地图书馆网站](/zh-CN/docs/Learn/Server-side/Express_Nodejs/Tutorial_local_library_website)
    5.  [Express 教程 2： 新建网站骨架](/zh-CN/docs/Learn/Server-side/Express_Nodejs/skeleton_website)
    6.  [Express 教程 3： 使用数据库 (Mongoose)](/zh-CN/docs/Learn/Server-side/Express_Nodejs/mongoose)
    7.  [Express 教程 4： 路由和控制器](/zh-CN/docs/Learn/Server-side/Express_Nodejs/routes)
    8.  [Express 教程 5： 呈现图书馆数据](/zh-CN/docs/Learn/Server-side/Express_Nodejs/Displaying_data)
    9.  [Express 教程 6： 使用表单](/zh-CN/docs/Learn/Server-side/Express_Nodejs/forms)
    10.  [Express 教程 7： 部署至生产环境](/zh-CN/docs/Learn/Server-side/Express_Nodejs/deployment)
    
40.  [**更多资源**](#)
41.  常见问题
    
    1.  [常见问题概述](/zh-CN/docs/Learn/Common_questions)
    2.  [HTML 问题](/zh-CN/docs/Learn/HTML/Howto)
    3.  [CSS 问题](/zh-CN/docs/Learn/CSS/Howto)
    4.  [JavaScript questions](/zh-CN/docs/Learn/JavaScript/Howto)
    5.  [Web 是如何运作的](/zh-CN/docs/Learn/Common_questions#Web_mechanics)
    6.  [工具与安装](/zh-CN/docs/Learn/Common_questions#Tools_and_setup)
    7.  [设计与无障碍](/zh-CN/docs/Learn/Common_questions#Design_and_accessibility)
    

In this article
---------------

*   [为什么是弹性盒子？](#为什么是弹性盒子？)
*   [一个简单的例子](#一个简单的例子)
*   [指定元素的布局为 flexible](#指定元素的布局为_flexible)
*   [flex 模型说明](#flex_模型说明)
*   [列还是行？](#列还是行？)
*   [换行](#换行)
*   [flex-flow 缩写](#flex-flow_缩写)
*   [flex 项的动态尺寸](#flex_项的动态尺寸)
*   [flex：缩写与全写](#flex：缩写与全写)
*   [水平和垂直对齐](#水平和垂直对齐)
*   [flex 项排序](#flex_项排序)
*   [flex 嵌套](#flex_嵌套)
*   [跨浏览器兼容性](#跨浏览器兼容性)
*   [测试你的技能](#测试你的技能)
*   [总结](#总结)
*   [参见](#参见)
*   [模块](#模块)

弹性盒子
====

*   [上一页](/zh-CN/docs/Learn/CSS/CSS_layout/Practical_positioning_examples)
*   [Overview: CSS layout](/zh-CN/docs/Learn/CSS/CSS_layout)
*   [下一页](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)

[弹性盒子](/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout)是一种用于按行或按列布局元素的一维布局方法。元素可以膨胀以填充额外的空间，收缩以适应更小的空间。本文将解释所有的基本原理。

<table class="learn-box standard-table"><tbody><tr><th scope="row">前提：</th><td>HTML 基础（学习 <a href="/zh-CN/docs/Learn/HTML/Introduction_to_HTML">HTML 介绍</a>），和了解 CSS 如何工作的（学习 <a href="/en-US/docs/Learn/CSS/First_steps">CSS 介绍</a>）。</td></tr><tr><th scope="row">目标：</th><td>学会如何使用弹性盒子布局系统来创建 Web 布局。</td></tr></tbody></table>

[为什么是弹性盒子？](#为什么是弹性盒子？)
-----------------------

长久以来，CSS 布局中唯一可靠且跨浏览器兼容的创建工具只有 [floats](/zh-CN/docs/Learn/CSS/CSS_layout/Floats) 和 [positioning](/zh-CN/docs/Learn/CSS/CSS_layout/Positioning)。这两个工具大部分情况下都很好使，但是在某些方面它们具有一定的局限性，让人难以完成任务。

以下简单的布局需求是难以或不可能用这样的工具（[floats](/zh-CN/docs/Learn/CSS/CSS_layout/Floats) 和 [positioning](/zh-CN/docs/Learn/CSS/CSS_layout/Positioning)）方便且灵活的实现的：

*   在父内容里面垂直居中一个块内容。
*   使容器的所有子项占用等量的可用宽度/高度，而不管有多少宽度/高度可用。
*   使多列布局中的所有列采用相同的高度，即使它们包含的内容量不同。

正如你将在后面的章节中看到的一样，弹性盒子使得很多布局任务变得更加容易。让我们继续吧！

[一个简单的例子](#一个简单的例子)
-------------------

在本文中，我们将通过一系列练习来帮助你了解弹性盒子的工作原理。开始前，你应该拷贝 mozilla github 仓库的 [弹性盒子 0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox0.html) 到本地。在现代浏览器里打开它（比如 Firefox 或 Chrome），然后打开你的编辑器看一眼它的代码。你可以看它的[线上](https://mdn.github.io/learning-area/css/css-layout/flexbox/flexbox0.html)实例。

![显示 Flexbox 教程开始的图像](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/bih741v.png)

你可以看到这个页面有一个含有顶级标题的 [`<header>`](/zh-CN/docs/Web/HTML/Element/header) 元素，和一个包含三个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 的 [`<section>`](/zh-CN/docs/Web/HTML/Element/section)。我们将使用这些来创建相当标准的三列布局。

[指定元素的布局为 flexible](#指定元素的布局为_flexible)
---------------------------------------

首先，我们需要选择将哪些元素将设置为弹性的盒子。我们需要给这些 flexible 元素的父元素 [`display`](/zh-CN/docs/Web/CSS/display) 设置一个特定值。在本例中，我们想要设置 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素，因此我们给 [`<section>`](/zh-CN/docs/Web/HTML/Element/section)（变成了 flex 容器）设置 display：

```
section {
  display:flex
} 
```

Copy to Clipboard

结果如下：

![两行容器，包括第一行的单列和第二行的三列布局，显示如何根据内容将网页划分为不同的布局](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example2.png)

所以，就这样一个简单的声明就给了我们所需要的一切—非常不可思议，对吧？我们的多列布局具有大小相等的列，并且列的高度都是一样。这是因为这样的 flex 项（flex 容器的子项）的默认值是可以解决这些的常见问题的。后面还有更多内容。

为了更清晰的表述，让我们重申这里发生的事情。关于它如何与页面其余部分交互，我们给的 [`display`](/zh-CN/docs/Web/CSS/display) 值为 `flex` 的元素就像一个块级元素，但是它的子元素布局为 flex 项。下个部分将更详细地描述这些意味着什么。请注意，如果你希望该元素的子元素作为 flex 项，你也可以使用 `display` 值为 `inline-flex`，但是该元素的行为类似于行内元素。

[flex 模型说明](#flex_模型说明)
-----------------------

当元素表现为 flex 框时，它们沿着两个轴来布局：

![在从左到右的语言中，三个 flex 项并排放置在 flex 容器中。主轴——弹性容器布置 flex 方向上的轴——是水平的。主轴的两端是开始端和结束端，分别位于左侧和右侧。交叉轴是垂直的；垂直于主轴。交叉轴的开始端和结束端分别位于顶部和底部。flex 项沿着主轴排列，在这种情况下，宽度称为主轴尺寸，flex 项沿交叉轴排列，在这种情况下，高度称为交叉尺寸。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png)

*   **主轴**（main axis）是沿着 flex 元素放置的方向延伸的轴（比如页面上的横向的行、纵向的列）。该轴的开始和结束被称为 **main start** 和 **main end**。
*   **交叉轴**（cross axis）是垂直于 flex 元素放置方向的轴。该轴的开始和结束被称为 **cross start** 和 **cross end**。
*   设置了 `display: flex` 的父元素（在本例中是 [`<section>`](/zh-CN/docs/Web/HTML/Element/section)）被称之为 **flex 容器（flex container）。**
*   在 flex 容器中表现为弹性的盒子的元素被称之为 **flex 项**（**flex item**）（本例中是 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素。

了解这些术语以便你阅读后续章节。如果你对使用的任何术语感到困惑，你可以随时返回这里。

[列还是行？](#列还是行？)
---------------

弹性盒子提供了 [`flex-direction`](/zh-CN/docs/Web/CSS/flex-direction) 这样一个属性，它可以指定主轴的方向（弹性盒子子类放置的地方）——它默认值是 `row`，这使得它们在按你浏览器的默认语言方向排成一排（在英语/中文浏览器中是从左到右）。

尝试将以下声明添加到 [`<section>`](/zh-CN/docs/Web/HTML/Element/section) 元素的 css 规则里：

```
flex-direction: column; 
```

Copy to Clipboard

你会看到，这会将那些元素设置为列布局，就像我们添加这些 CSS 之前。在继续之前，请从示例中删除此规则。

**备注：** 你还可以使用 `row-reverse` 和 `column-reverse` 值反向排列 flex 项。用这些值试试看吧！

[换行](#换行)
---------

当你在布局中使用定宽或者定高的时候，可能会出现问题即处于容器中的弹性盒子子元素会溢出，破坏了布局。你可以看一下[弹性盒子——wrap0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox-wrap0.html) 示例（你也可以拷贝到本地），如下所示：

![简单弹性盒子示例，将所有 flex 项都布置在弹性容器的一行中。第八个 flex 项在浏览器窗口溢出，页面具有可见的水平和垂直滚动条，因为它无法容纳在窗口的宽度内，因为前七个 flex 项占用了视口中的可用空间。默认情况下，如果将弹性方向设置为行，浏览器会尝试将所有 flex 项放在一行中；如果弹性方向设置为列，则会尝试将所有 flex 项置于单列中。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example3.png)

在这里我们看到，子代确实超出了它们的容器。解决此问题的一种方法是将以下声明添加到 section css 规则中：

```
flex-wrap: wrap 
```

Copy to Clipboard

同时，把以下规则也添加到 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 规则中：

```
flex: 200px; 
```

Copy to Clipboard

现在尝试一下吧；你会看到布局比原来好多了：

![flex 项在弹性容器中分多行排列。flex-wrap 属性在弹性容器中设置为“wrap”，如果上一行中的 flex 项在弹性容器外溢出，则弹性容器中显示新行中的 flex 项。每个 flex 项的宽度为 200 像素。所有物品都被拉伸到相同的高度，与内容最多的 flex 项一样高。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example4.png)

我们现在有多个行。每行都安装了尽可能多的 flex 项。任何溢出都会向下移动到下一行。在 article 上设置的 `flex：200px` 声明意味着每个声明将至少为 200px 宽。我们稍后会更详细地讨论这个属性。你可能还注意到，最后一行上的最后几个项每个都变得更宽，以便把整个行填满。

但是这里我们可以做得更多。首先，改变 [`flex-direction`](/zh-CN/docs/Web/CSS/flex-direction) 属性值为 `row-reverse`——你会看到仍然有多行布局，但是每一行元素排列的方向和原来是相反的了。

[flex-flow 缩写](#flex-flow_缩写)
-----------------------------

到这里，应当注意到存在着 [`flex-direction`](/zh-CN/docs/Web/CSS/flex-direction) 和 [`flex-wrap`](/zh-CN/docs/Web/CSS/flex-wrap)——的缩写 [`flex-flow`](/zh-CN/docs/Web/CSS/flex-flow)。比如，你可以将

```
flex-direction: row;
flex-wrap: wrap; 
```

Copy to Clipboard

替换为

```
flex-flow: row wrap; 
```

Copy to Clipboard

[flex 项的动态尺寸](#flex_项的动态尺寸)
---------------------------

现在让我们回到第一个例子，看看是如何控制 flex 项占用空间的比例的。打开你本地的 [弹性盒子 0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox0.html)，或者拷贝 [弹性盒子 1.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox1.html) 作为新的开始（[查看线上](https://mdn.github.io/learning-area/css/css-layout/flexbox/flexbox1.html)）。

第一步，将以下规则添加到 CSS 的底部：

```
article {
  flex: 1;
} 
```

Copy to Clipboard

这是一个无单位的比例值，表示每个 flex 项沿主轴的可用空间大小。本例中，我们设置 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素的 flex 值为 1，这表示每个元素占用空间都是相等的，占用的空间是在设置 padding 和 margin 之后剩余的空间。因为它是一个比例，这意味着将每个 flex 项的设置为 400000 的效果和 1 的时候是完全一样的。

现在在上一个规则下添加：

```
article:nth-of-type(3) {
  flex: 2;
} 
```

Copy to Clipboard

现在当你刷新，你会看到第三个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素占用了两倍的可用宽度和剩下的一样——现在总共有四个比例单位可用。前两个 flex 项各有一个，因此它们占用每个可用空间的 1/4。第三个有两个单位，所以它占用 2/4 或者说是 1/2 的可用空间。

你还可以指定 flex 的最小值。尝试修改现有的 article 规则：

```
article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 2 200px;
} 
```

Copy to Clipboard

这表示“每个 flex 项将首先给出 200px 的可用空间，然后，剩余的可用空间将根据分配的比例共享”。尝试刷新，你会看到分配空间的差别。

![简单的 flexbox 示例，flex 容器中有三个 flex 项。所有 flex 项的最低宽度为 200 像素——使用“flex”设置。前两个 flex 项的 flex 值为 1，第三个项的 flex 值为 2。这会将弹性容器中的剩余空间分成 4 个比例单位。前两个 flex 项各分配一个单元，第三个 flex 项分配两个单元，使第三个 flex 项比宽度相同的其他两个更宽。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example1.png)

弹性盒子的真正价值可以体现在它的灵活性/响应性，如果你调整浏览器窗口的大小，或者增加一个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素，这时的布局仍旧是好的。

[flex：缩写与全写](#flex：缩写与全写)
-------------------------

[`flex`](/zh-CN/docs/Web/CSS/flex) 是一个可以指定最多三个不同值的缩写属性：

*   第一个就是上面所讨论过的无单位比例。可以单独指定全写 [`flex-grow`](/zh-CN/docs/Web/CSS/flex-grow) 属性的值。
*   第二个无单位比例——[`flex-shrink`](/zh-CN/docs/Web/CSS/flex-shrink)——一般用于溢出容器的 flex 项。这指定了从每个 flex 项中取出多少溢出量，以阻止它们溢出它们的容器。这是一个相当高级的弹性盒子功能，我们不会在本文中进一步说明。
*   第三个是上面讨论的最小值。可以单独指定全写 [`flex-basis`](/zh-CN/docs/Web/CSS/flex-basis) 属性的值。

我们建议不要使用全写属性，除非你真的需要（比如要去覆盖之前写的）。使用全写会多写很多的代码，它们也可能有点让人困惑。

[水平和垂直对齐](#水平和垂直对齐)
-------------------

还可以使用弹性盒子的功能让 flex 项沿主轴或交叉轴对齐。让我们一起看一下新例子——[flex-align0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flex-align0.html)（[在线浏览](https://mdn.github.io/learning-area/css/css-layout/flexbox/flex-align0.html)）——我们将会有一个整洁，灵活的按钮/工具栏。此时，你看到了一个水平菜单栏，其中一些按钮卡在左上角，就像下面这样：

![带有 Smile、Laugh、Wink、Shrug & Blush 标签的五个按钮排列在一个弹性容器中。按钮卡在左上角，看起来不整洁。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example5.png)

首先，拷贝一份到本地。

然后，将下面的 CSS 添加到例子的底部：

```
div {
  display: flex;
  align-items: center;
  justify-content: space-around;
} 
```

Copy to Clipboard

![带有 Smile、Laugh、Wink、Shrug & Blush 标签的五个按钮排在一个弹性容器中。通过将对齐项属性设置为中心，flex 项位于横轴的中心。通过将 justify-content 属性设置为 space-around，flex 项沿着主轴均匀间隔。](/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox_center_space-around.png)

刷新一下页面，你就会看到这些按钮很好的垂直水平居中了。我们是通过下面所说的两个新的属性做到的。

[`align-items`](/zh-CN/docs/Web/CSS/align-items) 控制 flex 项在交叉轴上的位置。

*   默认的值是 `stretch`，其会使所有 flex 项沿着交叉轴的方向拉伸以填充父容器。如果父容器在交叉轴方向上没有固定宽度（即高度），则所有 flex 项将变得与最长的 flex 项一样长（即高度保持一致）。我们的第一个例子在默认情况下得到相等的高度的列的原因。
*   在上面规则中我们使用的 `center` 值会使这些项保持其原有的高度，但是会在交叉轴居中。这就是那些按钮垂直居中的原因。
*   你也可以设置诸如 `flex-start` 或 `flex-end` 这样使 flex 项在交叉轴的开始或结束处对齐所有的值。查看 [`align-items`](/zh-CN/docs/Web/CSS/align-items) 了解更多。

你可以用 [`align-self`](/zh-CN/docs/Web/CSS/align-self) 属性覆盖 [`align-items`](/zh-CN/docs/Web/CSS/align-items) 的行为。比如，你可以这样：

```
button:first-child {
  align-self: flex-end;
} 
```

Copy to Clipboard

！[带有 Smile、Laugh、Wink、Shrug & Blush 标签的五个按钮排在一个弹性容器中。除第一个项外，所有 flex 项都通过将对齐项属性设置为中心，位于十字轴的中心或垂直居中。第一项与交叉轴末端的弹性容器底部齐平，对齐自属性设置 flex 端。flex 项沿着容器的主轴或宽度均匀间隔。](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox/flexbox_first-child_flex-end.png)

去看看它产生的效果，然后删除它。

[`justify-content`](/zh-CN/docs/Web/CSS/justify-content) 控制 flex 项在主轴上的位置。

*   默认值是 `flex-start`，这会使所有 flex 项都位于主轴的开始处。
*   你也可以用 `flex-end` 来让 flex 项到结尾处。
*   `center` 在 `justify-content` 里也是可用的，可以让 flex 项在主轴居中。
*   而我们上面用到的值 `space-around` 是很有用的——它会使所有 flex 项沿着主轴均匀地分布，在任意一端都会留有一点空间。
*   还有一个值是 `space-between`，它和 `space-around` 非常相似，只是它不会在两端留下任何空间。

在继续下面之前，多多使用提到过的属性吧，看看它们的效果。

[flex 项排序](#flex_项排序)
---------------------

弹性盒子也有可以改变 flex 项的布局位置的功能，而不会影响到源顺序（即 dom 树里元素的顺序）。这也是传统布局方式很难做到的一点。

代码也很简单，将下面的 CSS 添加到示例代码下面。

```
button:first-child {
  order: 1;
} 
```

Copy to Clipboard

刷新下，然后你会看到“Smile”按钮移动到了主轴的末尾。下面我们谈下它实现的一些细节：

*   所有 flex 项默认的 [`order`](/zh-CN/docs/Web/CSS/order) 值是 0。
*   order 值大的 flex 项比 order 值小的在显示顺序中更靠后。
*   相同 order 值的 flex 项按源顺序显示。所以假如你有四个元素，其 order 值分别是 2，1，1 和 0，那么它们的显示顺序就分别是第四，第二，第三，和第一。
*   第三个元素显示在第二个后面是因为它们的 order 值一样，且第三个元素在源顺序中排在第二个后面。

你也可以给 order 设置负值使它们比值为 0 的元素排得更前面。比如，你可以设置“Blush”按钮排在主轴的最前面：

```
button:last-child {
  order: -1;
} 
```

Copy to Clipboard

[flex 嵌套](#flex_嵌套)
-------------------

弹性盒子也能创建一些颇为复杂的布局。设置一个元素为 flex 项，那么他同样成为一个 flex 容器，它的孩子（直接子节点）也表现为弹性盒子。看一下 [复杂弹性盒子.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/complex-flexbox.html)（[在线浏览](https://mdn.github.io/learning-area/css/css-layout/flexbox/complex-flexbox.html)）。

[简单 Flexbox 示例，连续列出三个 flex 项的子元素。前两个宽度相同，第三个略宽。第三个 flex 项也是一个弹性容器。它有一组两行的按钮，后跟文本。第一行按钮有 4 个按钮，排列成一排；按钮的宽度相同，占据了容器的全部宽度。第二行只有一个按钮，可以单独占据该行的整个宽度。这是复杂的布局，很少有 flex 项继续被视为弹性容器。](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example7.png)

这个例子的 HTML 是相当简单的。我们用一个 [`<section>`](/zh-CN/docs/Web/HTML/Element/section) 元素包含了三个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article)元素。第三个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素包含了三个 [`<div>`](/zh-CN/docs/Web/HTML/Element/div)：

```
section - article
          article
          article - div - button
                    div   button
                    div   button
                          button
                          button

```

Copy to Clipboard

现在让我们看一下布局用到的代码。

首先，我们设置 [`<section>`](/zh-CN/docs/Web/HTML/Element/section) 的子节点布局为弹性盒子。

```
section {
  display: flex;
} 
```

Copy to Clipboard

下面我们给 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素设置 flex 值。特别注意这里的第二条 CSS 规则——我们设置第三个 [`<article>`](/zh-CN/docs/Web/HTML/Element/article) 元素的子节点的布局同样为 flex，但是属性值为列布局。

```
article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 3 200px;
  display: flex;
  flex-flow: column;
} 
```

Copy to Clipboard

接下来，我们选择了第一个 [`<div>`](/zh-CN/docs/Web/HTML/Element/div)。首先使用 `flex: 1 100px;` 简单的给它一个最小的高度 100px，然后设置它的子节点（[`<button>`](/zh-CN/docs/Web/HTML/Element/button) 元素）为 flex 项。在这里我们将它们放在一个包装行（wrap row）中，使它们居中对齐，就像我们在前面看到的单个按钮示例中做的那样。

```
article:nth-of-type(3) div:first-child {
  flex: 1 100px;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: space-around;
} 
```

Copy to Clipboard

最后，我们给按钮设置大小，有意思的是我们给它一个值为 1 的 flex 属性。如果你调整浏览器窗口宽度，你会看到这是一个非常有趣的效果。按钮将尽可能占用最多的空间，尽可能多的堆在同一条线上，但是当它们不再适合在同一条线上，他们中的一些会到下一行去。

```
button {
  flex: 1;
  margin: 5px;
  font-size: 18px;
  line-height: 1.5;
} 
```

Copy to Clipboard

[跨浏览器兼容性](#跨浏览器兼容性)
-------------------

大多数浏览器都支持弹性盒子，诸如 Firefox、Chrome、Opera、Microsoft Edge 和 IE 11，较新版本的 Android/iOS 等等。但是你应该要意识到仍旧有被人使用的老浏览器不支持弹性盒子（或者支持，但是只是支持非常非常老版本的弹性盒子）。

虽然你只是在学习和实验，这不太要紧; 然而，如果你正在考虑在真实网站中使用弹性盒子，则需要进行测试，并确保在尽可能多的浏览器中你的用户体验仍然可以接受。

弹性盒子相较其他一些 CSS 特性可能更为棘手。例如，如果浏览器缺少 CSS 阴影，则该网站可能仍然可用。但是假如不支持弹性盒子功能就会完全打破布局，使其不可用。

我们在[跨浏览器测试](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing)模块中讨论了克服跨浏览器支持问题的策略。

[测试你的技能](#测试你的技能)
-----------------

我们在文章里面覆盖了很多内容，但你是否能记住最重要的知识？在你继续学习前，你可以进行[测试 (en-US)](/en-US/docs/Learn/CSS/CSS_layout/Flexbox_skills "Currently only available in English (US)")来验证你是否掌握了这些知识。

[总结](#总结)
---------

到这里，介绍弹性盒子的基础知识就结束了。我们希望你体会到乐趣，并且玩的开心，能随着你的学习与你一起向前。接下来，我们将看到 CSS 布局的另一个重要方面：[CSS 网格系统](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)

*   [上一页](/zh-CN/docs/Learn/CSS/CSS_layout/Practical_positioning_examples)
*   [Overview: CSS layout](/zh-CN/docs/Learn/CSS/CSS_layout)
*   [下一页](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)

[参见](#参见)
---------

*   [CSS 弹性盒子技巧](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)——一篇以视觉吸引人的方式解释弹性盒子所有内容的文章
*   [弹性盒子青蛙游戏](https://flexboxfroggy.com/)——学习和更好地了解弹性盒子基础知识的教育游戏

*   [上一页](/zh-CN/docs/Learn/CSS/CSS_layout/Normal_Flow)
*   [Overview: CSS layout](/zh-CN/docs/Learn/CSS/CSS_layout)
*   [下一页](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)

[模块](#模块)
---------

*   [介绍 CSS 布局](/zh-CN/docs/Learn/CSS/CSS_layout/Introduction)
*   [常规流](/zh-CN/docs/Learn/CSS/CSS_layout/Normal_Flow)
*   [弹性盒子](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)
*   [网格](/zh-CN/docs/Learn/CSS/CSS_layout/Grids)
*   [浮动](/zh-CN/docs/Learn/CSS/CSS_layout/Floats)
*   [定位](/zh-CN/docs/Learn/CSS/CSS_layout/Positioning)
*   [多栏布局](/zh-CN/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
*   [响应式设计](/zh-CN/docs/Learn/CSS/CSS_layout/Responsive_Design)
*   [初学者媒体查询的指导](/zh-CN/docs/Learn/CSS/CSS_layout/Media_queries)
*   [传统的布局方法](/zh-CN/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)
*   [支持旧的浏览器](/zh-CN/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers)
*   [几本布局理解](/zh-CN/docs/Learn/CSS/CSS_layout/Fundamental_Layout_Comprehension)

### Found a problem with this page?

*   [Edit on **GitHub**](https://github.com/mdn/translated-content/edit/main/files/zh-cn/learn/css/css_layout/flexbox/index.md "You're going to need to sign in to GitHub first (Opens in a new tab)")
*   [Source on **GitHub**](https://github.com/mdn/translated-content/blob/main/files/zh-cn/learn/css/css_layout/flexbox/index.md?plain=1 "Folder: zh-cn/learn/css/css_layout/flexbox (Opens in a new tab)")
*   [Report a problem with this content on **GitHub**](https://github.com/mdn/translated-content/issues/new?template=page-report-zh-CN.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fzh-CN%2Fdocs%2FLearn%2FCSS%2FCSS_layout%2FFlexbox&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60zh-cn%2Flearn%2Fcss%2Fcss_layout%2Fflexbox%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fzh-CN%2Fdocs%2FLearn%2FCSS%2FCSS_layout%2FFlexbox%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Ftranslated-content%2Fblob%2Fmain%2Ffiles%2Fzh-cn%2Flearn%2Fcss%2Fcss_layout%2Fflexbox%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Ftranslated-content%2Fcommit%2F446db940755dfa5db6a279f8b46bbed291aef001%0A*+Document+last+modified%3A+2022-11-07T09%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue")
*   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** 2022年11月7日, [by MDN contributors](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox/contributors.txt)