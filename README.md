## 文档

使用文档参考

[VersaAssistant](https://docs.liuwei.vin/projects/VersaAssistant/) 

##  克隆仓库

```bash
git clone https://github.com/vseasky/VersaAssistant.git
```

## 安装 QT

- QT版本 5.14.2
- [Download.Qt](https://download.qt.io/archive/qt/)
- MingW-64/32

## 安装 Clion

- [CLion](https://www.jetbrains.com/clion/download/#section=windows)

## 配置环境

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711b99d2106f.png)

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711b9c804ef1.png)

### 配置工具链

打开设置面板，进行工具链配置

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711babd3d9dc.png)
新建两个工具链
- Qt MinGW 64
	- 对应路径：`QT安装路径`+`Tools/mingw730_64`
- Qt MinGW 32
	- 对应路径：`QT安装路径`+`Tools/mingw730_32`
![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bae786627.png)

### 配置CMake

配置 CMake 

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711ba3a6b532.png)

添加 CMake配置

- Release （Qt MinGW 64)
	- 工具链选择 `Qt MinGW 64`
	- 构建目录：`build\release\x64`
	- 环境：
		- CMAKE_PREFIX_PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_64;
		- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_64/bin
- Debug  （Qt MinGW 64)
	- 工具链选择 `Qt MinGW 64`
	- 构建目录：`build\debug\x64`
	- 环境：
		- CMAKE_PREFIX_PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_64;
		- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_64/bin
- Release （Qt MinGW 32)
	- 工具链选择 `Qt MinGW 32`
	- 构建目录：`build\release\x86`
	- 环境：
		- CMAKE_PREFIX_PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_32;
		- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_32/bin
- Debug  （Qt MinGW 32)
	- 工具链选择 `Qt MinGW 32`
	- 构建目录：`build\debug\x86`
	- 环境：
		- CMAKE_PREFIX_PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_32;
		- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_32/bin

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bbca6cc33.png)
![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bd111dbe2.png)

### 配置编译配置模板

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bde5264b4.png)

新建两个模板

- VersaAssistant (64)
	- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_64/bin
- VersaAssistant (32)
	- PATH=D:/SoftwareTools/Qt/Qt5.14.2/5.14.2/mingw73_32/bin

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711be2f90d72.png)

清空 `build` 构建输出目录

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bee039b6a.png)

重新进行构建

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bec0afb4a.png)

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bf1da188d.png)

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711bf4a5376a.png)

点击运行
![image.png](https://www.liuwei.pub/pic/2024/10/18/6711c035bba10.png)

如果出现 `VersaAppVersionConfig.h` 报错，则需要再次进行重构

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711c260df95b.png)

然后重新编译即可

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711c350a6f6d.png)

输出文件分别在

- build/release/platform/x64/bin
- build/release/platform/x86/bin
- build/debug/platform/x64/bin
- build/debug/platform/x86/bin

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711c38d29087.png)

### 程序打包

```bash
windeployqt VersaAssistant.exe
```

![image.png](https://www.liuwei.pub/pic/2024/10/18/6711c8f9b0ec4.png)
