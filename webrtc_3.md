#WebRTC源码目录介绍

> WebRTC源码包含了音频、视频、P2P等多项技术，代码比较复杂。由于WebRTC的代码变动很大，网上一些源码目录分析的文章已经和现在最新的目录结构不一样了。我整理了份最新的源码目录结构的文档如下。

+ api

WebRTC 接口层。包括 DataChannel, MediaStream, SDP相关的接口。各浏览器都是通过该接口层调用的 WebRTC。

+ audio

存放音频网络逻辑层相关的代码。音频数据逻辑上的发送，接收等代码。

+ base

基础类如base64等。

+ build

编译脚本和环境配置脚本代码。

+ build_overrides

+ buildtools

编译使用到的工具

+ call

存放的是 WebRTC “呼叫（Call）” 相关逻辑层的代码。

+ common_audio

存放一些音频的基本算法。包括环形队列，博利叶算法，滤波器等。

+ common_video

存放了视频算法相关的常用工具，如libyuv, sps/pps分析器，I420缓冲器等。

+ data

模块测试数据。

+ examples

webrtc 使用例子和测试，没有IOS的完整版。

+ infra

+ ios

依赖的ios三方库等

+ logging

 webrtc 日志工具

+ media

存放媒体相关的代码。

+ modules

这个目录是 WebRTC 代码中最重要的一个目录。里面包括了音视频的采集，处理，编解码器，混音等。

> 视频的渲染部分已经从这里删除了。因为没有浏览器需要用到这里的渲染代码。如果使用Native API 做二次开发，需要自己写视频渲染相关的代码。

modules 目录下还包括以下几个子目录：

- audio_coding : 音频编解码相关代码。

- audio_conference_mixer : 会议混音相关代码。

- audio_device : 音频采集与音频播放相关代码。

- audio_mixer : 混音相关代码，这部分是后加的。

- audio_processing : 音频前后处理的相关代码。

- bitrate_controller : 码率控制相关代码。

- congestion_controller : 流控相关的代码。

- desktop_capture : 桌面采集相关的代码。

- media_file : 播放媒体文件相关的代码。

- pacing : 码率探测相关的代码。

- remote_bitrate_estimator : 远端码率估算相关的代码。

- rtp_rtcp : rtp/rtcp协议相关代码。

- video_capture : 视频采集相关的代码。

- video_coding : 视频编解码相关的代码。

- video_processing : 视频前后处理相关的代码。

+ ortc
+ out

生成的各平台工程文件，clone下来代码本身没有，用gn生成

+ out_ios_libs

编译出的IOS框架代码， clone下来代码本身没有，编译ios webrtc框架时生成。
+ p2p

p2p相关的代码。

+ pc

存放一些业务逻辑层的代码。如 channel, session等。

+ resources
+ rtc_base

存放了一些基础代码。如线程，事件，socket等相关的代码。

+ rtc_tools

存放了一些工具代码。如视频帧比较，I420转RGB，视频帧分析。

+ sdk

存放了 Android 和 IOS 层代码。如视频的采集，渲染代码都在这里。

+ stats

存放各种数据统计相关的类。

+ system_wrapper

与操作系统相关的代码，如 CPU特性，原子操作，读写锁，时钟等。

+ test

测试相关代码

+ testing

测试相关

+ third_party

依赖的三方库，例如Android的ndk

+ tools

依赖的一些工具，如gdb、git、gn等

+ tools_webrtc

各平台的编译脚本等

+ video

存放视频逻辑层及视频引擎层的相关的代码。视频数据逻辑上的发送，接收等代码。
>视频引擎层就是指如何控制视频采集，处理和编解码操作的逻辑。