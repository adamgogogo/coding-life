# 如何在没有 U 盘的情况下将 2012 年中期的旧 MacOS Catalina 升级到 MacOS Big Sur

- [English Version](blogs/how-I-upgrade-12-mid-catalina-to-bigsur-without-usb-stick.md)

感觉很幸运，我可以继续使用我最喜欢的 Macbook Pro 来制作APP。 我的系统从2012年年中开始使用，目前基于 `MacOS Catalina`。Apple 公司表示不再支持2013年之前的系统升级。好像没有办法升级到 `MacOS Big Sur`。 但是还是有一个例外，你可以自己升级。

首先，我的 catalina 系统从 bug sur 系统来看没有那么老，所以升级起来也不是太难。但如果您有一台更旧的 Mac 电脑，您可能需要做更多的事情来实现这一目标。目前这里我们只讲一种比较简单的把 catalina 升级到 big sur 的方法。

然后，你需要知道三点做好准备:

1. 你的Mac电脑应该有足够的空间升级，你需要两个空间，一个是启动安装程序，它需要至少 `20Gb`，另一个也在 `20Gb` 以上，这意味着你当前的 catalina 系统至少有 `20Gb ` 可用空间。

2. 需要下载 MacOS Big Sur 系统安装包, 比如 [macOS Big Sur 11.6.1 \(20G224\)](https://support.apple.com/en-us/HT211683).

3. 需要下载  [big-sur-micropatcher](https://github.com/barrykn/big-sur-micropatcher) 来帮助你启动安装程序。

准备好这三样东西后。 让我们开始吧。

1. 需要在您的系统应用程序目录中安装 [macOS Big Sur 11.6.1 \(20G224\)](https://support.apple.com/en-us/HT211683) ，安装路径应该是`/Applications/Install\ macOS\ Big\ Sur.app/`.

2. 您应该在磁盘工具中创建一个类型为 Mac OS X 扩展的新分区。大小为 `20Gb`，名称为 `bigsur`。

3. 打开你的终端，执行如下命令：`sudo /Applications/Install\macOS\Big\Sur.app/Contents/Resources/createinstallmedia
--volume /Volumes/bigsur`，它可以帮助您制作一个可启动的卷来安装新系统。

4. 在您​​的终端中，cd 到您下载并解压缩的类别 “big-sur-micropatcher-0.5.1”。运行 `sudo bash micropatcher.sh /Volumes/Install\ macOS\ Big\ Sur` 和 `sudo bash install-setvars.sh /Volumes/Install\ macOS\ Big\ Sur`。

5. 重新启动系统，并按住 `Option` 键，您将进入启动选择界面选择一项进入。现在您可以看到两个选项，包括：“EFI Boot” 和 “Install macOS Big Sur”，默认选项除外。我的默认选项是 `MacOS1013`。

6. 首先你需要选择 `EFI Boot`，它帮助你做以下事情：`禁用SIP，
禁用经过身份验证的 root，并在非 Apple SSD 上启用 TRIM。它会快速关闭您的计算机。

7. 然后你应该再次启动你的电脑，并选择 `Install macOS Big Sur`。您将看到系统还原界面，然后单击 “安装 macOS Big Sur” 按钮，选择您当前的系统磁盘进行升级。剩下的就是等待安装过程完成。

8. 如果无线网卡无法工作，wifi 列表为空。再次启动你的电脑，按住 `Option` 键，并选择 `Install macOS Big Sur`。启动后选择 “Utilities (实用工具) -> Terminal（终端）”，执行如下命令（“MacOS1013” 是默认名称，根据实际名称修改）：`/Volumes/Image\ Volume/patch-kexts.sh /Volumes/MacOS1013
` 也许有些许错误提示，不过可以忽略，重启系统。wifi 列表应该就正常了。

这就是你所能做的。祝你好运！

![Screenshot](https://adamgogogo.github.io/coding-life/img/1638885880082.jpg)








