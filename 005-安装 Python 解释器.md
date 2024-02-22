在 RoboMaster App 中，使用的 Python 版本为 3.6.6，本文将以 3.8.10 版本作为示例。

> [!quote] 关于 Python 版本  
> 截止至 2024/2/19，Python 已经发布 3.13 prerelease  
> 但 RoboMaster EP 最新固件内置的 Python 版本仍然是 2018/6/27 发布的 Python 3.6.6  
> 且 RoboMaster SDK 仅支持 Python 3.6-3.8，因此我们使用 Python 3.8.10 作为示例

> [!quote] 关于 Python 版本共存
> 在 Windows 系统中，可以同时安装多个 Python 版本，但需要注意环境变量的配置。默认的 `python` 所对应的 Python 版本由 Path 优先级决定。可以使用 `python -V` 查看默认的 `python` 所对应的版本  
> 当有多个版本共存时，可以使用 `py -3.8` 指定强制使用 Python 3.8  
> 可以使用 `py -3.8 -m pip` 来替换 `pip` 命令安装 PyPI 包

- [[005-安装 Python 解释器#在 Windows 中安装|在 Windows 中安装]]

## 在 Windows 中安装

在 Windows 系统中，系统并不自带 Python 解释器，因此需要手动安装。

### 下载 Python 安装包

- [Python 官网](https://www.python.org/downloads/)
- [阿里镜像源](https://registry.npmmirror.com/binary.html?path=python/)

 以 Python 3.8.10 为例
- Python 官网
	- [Windows installer (32-bit)](https://www.python.org/ftp/python/3.8.10/python-3.8.10.exe)
	- [Windows installer (64-bit)](https://www.python.org/ftp/python/3.8.10/python-3.8.10-amd64.exe)
- 阿里镜像源
	- [Windows installer (32-bit)](https://registry.npmmirror.com/-/binary/python/3.8.10/python-3.8.10.exe)
	- [Windows installer (64-bit)](https://registry.npmmirror.com/-/binary/python/3.8.10/python-3.8.10-amd64.exe)

### 安装 Python

- 运行 Python 安装包
- **勾选 `Add Python 3.8 to PATH`** (界面下方)
- 点击 Install Now (快速安装)
- 等待安装流程
- 安装流程完成后点击 `Disable path length limit` (可选，取消 Path 长度限制)

### 配置环境

在中国大陆地区，由于网络环境的原因，可能需要配置 PyPI 镜像源。

使用 `pip config set global.index-url <pip_mirror_url>` 配置 PyPI 镜像源

常见加速源有：

- [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/) `https://pypi.tuna.tsinghua.edu.cn/simple`
	```bash
	pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
	```
- [北京大学开源镜像站](https://mirrors.pku.edu.cn/) `https://mirrors.pku.edu.cn/pypi/web/simple`
	```bash
	pip config set global.index-url https://mirrors.pku.edu.cn/pypi/web/simple
	```
- [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror/) `http://mirrors.aliyun.com/pypi/simple/`
	```bash
	pip config set global.index-url http://mirrors.aliyun.com/pypi/simple/
	```



## 在 Linux 中安装

在 Linux 系统中，大部分发行版都自带 Python 解释器，但可能不是最新版本。
要安装指定版本 Python，可以下载源码编译安装

### 下载源码

- 更新系统软件包
	```bash
	sudo apt update
	```
- 安装依赖项
	```bash
	sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget
	```
- 下载Python 3.8.10源代码包：
	```bash
	wget https://www.python.org/ftp/python/3.8.10/Python-3.8.10.tgz
	```
	也可以使用镜像  
	```bash
	wget https://registry.npmmirror.com/-/binary/python/3.8.10/Python-3.8.10.tgz
	```
- 解压源代码包：
	```bash
	tar -xf Python-3.8.10.tgz
	```
- 进入解压后的目录：
	```bash
	cd Python-3.8.10
	```
### 编译

- 配置安装选项：
	```bash
	./configure --enable-optimizations
	```
	注意：`--enable-optimizations` 选项将启用优化，以提高Python的性能。根据您的系统和需求，您可以选择是否启用该选项。
- 编译源代码：
	```bash
	make -j 4
	```
- 安装Python 3.8.10：
	```bash
	sudo make altinstall
	```
	使用 `altinstall` 而不是 `install` 命令可以避免覆盖系统默认的 Python 版本。
- 在终端中输入以下命令验证安装是否成功
	```bash
	python3.8 --version
	```
	应该会显示Python 3.8.10的版本信息。

### 配置环境

参考 [[005-安装 Python 解释器#配置环境|配置环境]]
