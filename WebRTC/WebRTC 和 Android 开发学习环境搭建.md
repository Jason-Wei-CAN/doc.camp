# [WebRTC 和 Android 开发学习环境搭建](https://github.com/Jason-Wei-CAN/doc.camp/blob/master/WebRTC/WebRTC%20%E5%92%8C%20Android%20%E5%BC%80%E5%8F%91%E5%AD%A6%E4%B9%A0%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md)


介绍一下 WebRTC 源码编译以及 Android 开发环境的搭建。

## 安装 depot_tools 工具包

首先需要下载 `depot_tools` 工具包，Git 命令如下：

```shell
git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
```

之后要把 `depot_tools` 目录添加到系统环境变量中。

```shell
export PATH=$PATH:/path/depot_tools
```

通过如下命令验证是否安装成功

```cpp
fetch --help
```

显示如下内容说明 `depot_tools` 配置好了。

![img](https://image.glumes.com/config-depot-tolos.png)

## 下载 WebRTC 源码

接下来就要用到 `depot_tools` 去下载 WebRTC 源码了。

WebRTC 的源码地址如下：

```shell
https://webrtc.googlesource.com/src/+/refs/heads/master/tools_webrtc/
```

下载执行如下命令：

```shell
mkdir webrtc
cd webrtc
fetch --nohooks webrtc_android
gclient sync
```

中间的下载过程耗时取决于你的网速了。

执行完如上命令后，就已经在本地拉取 WebRTC 源码了。

如果你对以上命令感到疑惑，不知道为什么这么写的话，可以参考一下 depot_tools 的使用。

如下文章：

> https://www.pianshen.com/article/3086804649/

### fetch 命令

其中 fetch 命令是用来获取源码的，有如下两个可选参数：

- –nohooks。这个参数表示获取代码完成之后不执行runhooks动作。也就仅仅获取代码。
- –no-history。这个参数表示对代码仓库执行git shallow clones，就不会获得原仓库的全部历史提交，这样可以减少拷贝代码仓库的大小。

### gclient 命令

其中 gclient 命令是用来管理多个模块源代码仓库的工具。它封装了一些常用的 git 命令，对所有的模块生效。除了 sync 外，还有如下参数：

- config。创建一个.gclient配置文件。
- diff。类似git的diff命令，用来比较所有模块提交代码的差异。
- fetch。获取所有模块上游的提交。
- help。显示命令的帮助。
- revert。revert一个提交。
- runhooks。根据DEPS文件的描述执行hook任务。
- stauts。类似git status命令，用来显示所有模块代码的状态。
- sync。用来同步所有模块的代码。

这里下载的是 Android 源码，如果是其他平台源码只需要改一下 fetch 命令最后的参数就行：

```cpp
// 下载 iOS 平台源码
fetch --nohooks webrtc_ios
```

### 安装依赖

下载完 WebRTC 后需要安装相关的依赖，进入到 WebRTC 源码的 `src` 目录中，执行如下命令：

```shell
cd src
./build/install-build-deps.sh
./build/install-build-deps-android.sh
```

执行如上两个命令就可以下载好相关依赖了。

> 要注意的是，如果用的 MAC 电脑下载不了依赖，这个命令是给 Linux 系统用的。

![img](https://image.glumes.com/mac-no-lsb-release.png)

要下载的话，就得在 Mac 上安装虚拟机，走虚拟机的方式了，这里不是很推荐。

## WebRTC 源码编译

通过如下命令进行编译：

```cpp
./build/android/envsetup.h
gn gen out/release/armeabi-v7a --args='target_os="android" target_cpu=“arm" is_debug=false'
ninja -C out/release/armeabi-v7a
```

编译成功后会输出两个文件：

```cpp
out/release/armeabi-v7a/lib.java/sdk/android/libwebrtc.jar
out/release/armeabi-v7a/libjingle_peerconnection_so.so
```

一个 jar 包和一个 so 动态库，这就是最终的编译产物。利用 WebRTC 进行开发就需要导入编译产物。

## Android 环境搭建

除了编译 WebRTC 源码得到 so 动态库和 jar 包之外，WebRTC 还提供了 Maven 仓库供我们下载，就像引入其他开源库一样：

```cpp
// 目前版本
implementation 'org.webrtc:google-webrtc:1.0.28513'
// 仓库地址：
https://bintray.com/google/webrtc/google-webrtc/1.0.28513
```

一行代码就能把编译的产物引入进来，省去了那么多编译步骤。

![img](https://image.glumes.com/webrtc-library-for-android.png)

这个 `1.0.28513` 对应的实现可能不是最新的，但是对于学习 WebRTC 代码来说已经足够了，毕竟大家都是基于 WebRTC 进行二次开发，而 Android 层的代码仅仅是对外的 API 接口而已，更多的是要去探究其 Natice 底层代码。

好在我们已经下载了源码，完全可以通过 API 的调用去深入研究 Native 层源码。

源码路径如下：

> src/sdk/android/

如下图：

![img](https://image.glumes.com/webrtc-android-source-code.png)

## 参考文章：

1. https://zhuanlan.zhihu.com/p/56233917
2. https://www.pianshen.com/article/3086804649/

