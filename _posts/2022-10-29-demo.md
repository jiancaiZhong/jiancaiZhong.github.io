---
layout: mypost
title: demo
categories: [demo]
---

```xml
<view class="ser-time-con">
    <view class="ser-time-l">订单服务对象</view>
    <view class="ser-time-r" bindtap="selectServiceObjectt" data-selectedCarts="{{selectedCarts}}">
      <text wx:if="{{item.serviceObjName}}">{{item.serviceObjName}}（{{item.relation}}）</text>
      <text wx:if="{{!item.serviceObjName}}">请选择服务对象</text>
    </view>
  </view>
```

[下载东西](demo.zip)

![demo](demo.jpg)