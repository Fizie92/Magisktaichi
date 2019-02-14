# How to use TaiChi·Magisk ？

## Notice

1. TaiChi·Magisk is designed for advanced users, If you do not want to unlock bootloader/flash system images, please use the normal TaiChi, you can still use Xposed modules with it. In addition, the APK file of TaiChi·Magisk and the normal TaiChi is the same, when TaiChi magisk modules is flashed, the normal TaiChi becomes into TaiChi·Magisk automatically.
2. TaiChi·Magisk is mainly developed for Android Pie. It is widely tested on Android Pie but little on Android Oreo, and system below Oreo (MarshMarrow/Nogaut) is never tested. Please do not use TaiChi·Magisk if you are using system below Oreo.
 
## Usage

首先你必须安装好了 Magisk，可以参考 [Magisk in XDA](https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445)

### 安装太极

Magisk 版需要安装最新的安装包，可以在 [Release 页面](https://github.com/tiann/Tai-Chi/releases) 找到安装包。
 
### 刷入 Magisk 模块

**必须先安装好了 Magisk，否则无法进行**。然后，在 [Release 页面](https://github.com/tiann/Tai-Chi/releases) 找到太极提供的 magisk 模块，注意：这是一个 ZIP 包，不是 APK 文件。

1. 打开 Magisk Manager，点击左上角侧滑菜单。
2. 选择 `模块` 打开 模块管理页面
3. 点击页面下方的 ➕ 从文件选择器选择 太极 提供的 magisk 模块的安装包。
4. 等待安装结束，重启手机。

另外，你也可以通过 TWRP 直接刷入 太极的 magisk 模块，不赘述。

### 使用

万事俱备之后，下面就是使用方法：

1. 打开太极，添加你需要使用 Xposed 模块的 APP，如微信到太极中。
2. 进入模块管理，勾选上你需要使用的 Xposed 模块，如 全部成为F。
3. 强制停止你需要观察效果的APP，如上面的微信。
4. 打开微信观察效果。

注意：太极·Magisk版有一些使用方法与 Xposed 不同，请知悉：

1. **必须把 APP 添加到太极中，太极才会对这个 APP 启用Xposed 功能。**
2. 不是作用于系统的模块，无需重启手机即可生效。
3. 模块重新安装之后，需要重新勾选。

关于第一点，

与普通的太极不同的是，Magisk 版添加 APP 基本不执行任何操作，它所做的就是简单的把你选择的这个 APP 添加到一个名单；仅此而已。不会修改签名，也不会有任何影响。

另外，没有添加到太极中的 APP，它运行的时候没有任何 Xposed 环境，就跟安装在没有 Xposed 的手机上一样；因此银行类等检测Xposed 的APP，只需要开启 Magisk Hide 即可正常使用！

并且，这并非表示 太极 无法使用作用于全局的 Xposed 模块。实际上，所谓的全局模块，一般指 拦截 system_server 和 systemui 两个进程模块，这一点太极是完全支持的。比如说 边缘手势模块，核心破解模块。

需要使用 Xposed 功能的APP相对于整个系统，毕竟是少数；仅对你需要的 APP 开启 Xposed 功能，这是太极的特性之一。美中不足的是，类似“谁动了我的剪切板”，这种要求拦截所有APP的模块，就只能监控到你添加进的APP。当然，这个问题有办法解决，我们以后再说。