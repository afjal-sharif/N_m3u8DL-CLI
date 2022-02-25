```

███╗   ██╗        ███╗   ███╗██████╗ ██╗   ██╗ █████╗ ██████╗ ██╗       ██████╗██╗     ██╗
████╗  ██║        ████╗ ████║╚════██╗██║   ██║██╔══██╗██╔══██╗██║      ██╔════╝██║     ██║
██╔██╗ ██║        ██╔████╔██║ █████╔╝██║   ██║╚█████╔╝██║  ██║██║█████╗██║     ██║     ██║
██║╚██╗██║        ██║╚██╔╝██║ ╚═══██╗██║   ██║██╔══██╗██║  ██║██║╚════╝██║     ██║     ██║
██║ ╚████║███████╗██║ ╚═╝ ██║██████╔╝╚██████╔╝╚█████╔╝██████╔╝███████╗ ╚██████╗███████╗██║
╚═╝  ╚═══╝╚══════╝╚═╝     ╚═╝╚═════╝  ╚═════╝  ╚════╝ ╚═════╝ ╚══════╝  ╚═════╝╚══════╝╚═╝
                                                                                          
```
---
[![img](https://img.shields.io/github/stars/nilaoda/N_m3u8DL-CLI?label=%E7%82%B9%E8%B5%9E)](https://github.com/nilaoda/N_m3u8DL-CLI)  [![img](https://img.shields.io/github/last-commit/nilaoda/N_m3u8DL-CLI?label=%E6%9C%80%E8%BF%91%E6%8F%90%E4%BA%A4)](https://github.com/nilaoda/N_m3u8DL-CLI)  [![img](https://img.shields.io/github/release/nilaoda/N_m3u8DL-CLI?label=%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC)](https://github.com/nilaoda/N_m3u8DL-CLI/releases)  [![img](https://img.shields.io/github/license/nilaoda/N_m3u8DL-CLI?label=%E8%AE%B8%E5%8F%AF%E8%AF%81)](https://github.com/nilaoda/N_m3u8DL-CLI)  [![img](https://img.shields.io/badge/URL-%E7%94%A8%E6%88%B7%E6%96%87%E6%A1%A3-blue)](https://nilaoda.github.io/N_m3u8DL-CLI/)


# [ENGLISH VERSION](https://github.com/nilaoda/N_m3u8DL-CLI/blob/master/README_ENG.md)

# 下载使用
* 发行版: https://github.com/nilaoda/N_m3u8DL-CLI/releases
* 自动构建版`(供测试)`: https://github.com/nilaoda/N_m3u8DL-CLI/actions
 
# 关于开源
本项目已于2019年10月9日开源，采用MIT许可证，各取所需。

# 关于跨平台
搁置了

# N_m3u8DL-CLI
一个**简单易用的**m3u8下载器，下载地址：https://github.com/nilaoda/N_m3u8DL-CLI/releases  

支持下载m3u8链接或文件为`mp4`或`ts`格式，并提供丰富的命令行选项。
  * **不支持**优酷视频解密
  * **不支持**气球云视频解密
  * 支持`AES-128-CBC`加密自动解密
  * 支持多线程下载
  * 支持下载限速
  * 支持断点续传
  * 支持`Master List`
  * 支持直播流录制(`BETA`)
  * 支持自定义`HTTP Headers`
  * 支持自动合并 (二进制合并或使用ffmpeg合并)
  * 支持选择下载`m3u8`中的指定时间段/分片内容
  * 支持下载路径为网络驱动器的情况
  * 支持下载外挂字幕轨道、音频轨道
  * 支持仅合并为音频
  * 支持设置特定http代理
  * 支持自动使用系统代理（默认行为, 可禁止）
  * 提供SimpleG简易的`GUI`生成常用参数



![运行截图](https://nilaoda.github.io/N_m3u8DL-CLI/source/images/%E7%9B%B4%E6%8E%A5%E4%BD%BF%E7%94%A8.gif)  

# 命令行选项
```
N_m3u8DL-CLI.exe <URL|File|JSON> [OPTIONS]  

    --workDir    Directory      Set the program working directory
    --saveName   Filename       Set the storage file name (excluding suffix)
    --baseUrl    BaseUrl        Set Baseurl
    --headers    headers        Set the request header, format key:value Use | to separate different key&value
    --maxThreads Thread         Set the maximum number of threads for the program (default is 32)
    --minThreads Thread         Set the minimum number of threads for the program (default is 16)
    --retryCount Count          Set the number of retries for the program (default is 15)
    --timeOut    Sec            Set the timeout time for the program network request (in seconds, the default is 10 seconds)
    --muxSetJson File           Define muxing options using an external json file
    --useKeyFile File           Define the AES-128 decryption KEY using an external 16-byte file
    --useKeyBase64 Base64String Define AES-128 decryption KEY using Base64 string
    --useKeyIV     HEXString    Define AES-128 decryption IV with HEX string
    --downloadRange Range       Download only a portion or length of a video
    --liveRecDur HH:MM:SS       During live recording, the software will automatically exit when this length is reached
    --stopSpeed  Number         When the speed is lower than this value, retry (in KB/s)
    --maxSpeed   Number         Set the download speed upper limit (in KB/s)
    --proxyAddress http://xx    Set HTTP proxy, such as http://127.0.0.1:8080
                   socks5://xx set SOCKS5 proxy, such as socks5://127.0.0.1:8080
    --enableDelAfterDone        Enable the function of deleting temporary folders after downloading
    --enableMuxFastStart        Enable the FastStart feature of mixed-stream mp4
    --enableBinaryMerge         Enable binary merge sharding
    --enableParseOnly           Turn on parse-only mode (the program only goes to meta.json)
    --enableAudioOnly           Wrap only audio tracks when merging
    --disableDateInfo           Turn off date writing in mux
    --noMerge                   Disable automatic merging
    --noProxy                   Do not use system proxy automatically
    --disableIntegrityCheck     Does not check whether the number of shards is complete

```

# 用户文档
https://nilaoda.github.io/N_m3u8DL-CLI/

# 聊聊
https://discord.gg/W5tvcRJDPs

# 赞赏
![Wow](https://nilaoda.github.io/N_m3u8DL-CLI/source/images/alipay.png)
