---
layout: mypost
title: Kylin OS安装ffmpeg
categories: [Linux, ffmpeg]
---



1. **安装yasm编译器**  [点击下载](http://www.tortall.net/projects/yasm/releases/yasm-1.3.0.tar.gz) (version:1.3.0) [版本选择](http://www.tortall.net/projects/yasm/releases/)

   - 进入到文件相应目录后，解压yasm

     ```bash
     tar zxvf yasm-1.3.0.tar.gz
     ```

   - 进入解压目录

     ```bash
     cd yasm-1.3.0
     ```

   - 编译

     ```bash
     make
     ```

   - 安装

     ```bash
     make install
     ```

2. **安装ffmpeg**  [点击下载](http://www.ffmpeg.org/releases/ffmpeg-5.1.1.tar.gz) (version:5.1.1)  [版本选择](http://www.ffmpeg.org/releases/)

   - 进入到文件相应目录后，解压ffmpeg
   
     ```bash
     tar -zxvf ffmpeg-5.1.1.tar.gz
     ```
   
   - 进入解压目录
   
     ```bash
     cd ffmpeg-5.1.1
     ```
   
   - 指定的安装目录
   
     ```bash
     ./configure --prefix=/data/ffmpeg
     ```
   
   - 编译 (十分钟左右)
   
     ```bash
     make
     ```
   
   - 安装
   
     ```bash
     make install
     ```
   
3. **配置变量** 
   
   ```bash
   vim /etc/profile
   
   # 在最后PATH添加环境变量：
   export PATH=$PATH:/data/ffmpeg/bin
   
   # 保存、退出
   # 刷新配置文件
   source /etc/profile 
   ```