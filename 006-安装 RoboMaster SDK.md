本文将会安装 RoboMaster SDK，不需要 SDK 的开发者不需要阅读本文。

参考 [RoboMaster SDK 安装](https://robomaster-dev.readthedocs.io/zh-cn/latest/python_sdk/installs.html)

## 在 Windows 中安装必须做的准备工作

由于 Windows 缺少一些必要的开发工具，需要进行一些准备工作。

### 安装 VC 库环境

从 [GitHub](https://github.com/dji-sdk/robomaster-sdk)，[Gitee](https://gitee.com/robomaster-edu/RoboMaster-SDK)，[本地地址](./Python%20%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97/files/VisualCppRedist_AIO_20200707.exe) 下载 VC 库的 exe 可执行文件 `VisualCppRedist_AIO_20200707.exe`，并按步骤安装

### 安装 VC build tools

从 [GitHub](https://github.com/dji-sdk/robomaster-sdk)，[Gitee](https://gitee.com/robomaster-edu/RoboMaster-SDK)，[本地地址](./Python%20%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97/files/visualcppbuildtools_full.exe) 下载 VC 库的 exe 可执行文件 `visualcppbuildtools_full.exe`，并按步骤安装

或者使用 [离线安装包](./Python%20%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97/files/offlineBuildTool.zip)，运行 `install.bat` 并按步骤安装即可

## 安装 RoboMaster SDK

运行命令

```bash
pip install robomaster
```

- 若未找到包，请检查 pip 版本 `pip -V`
- 若安装报错，请检查是否安装 VC build tools
- 若下载十分缓慢，请 [[./005-安装 Python 解释器#配置环境|005-安装 Python 解释器 > 配置环境]]
