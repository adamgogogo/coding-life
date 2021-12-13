# How I Upgraded 2012-mid Old MacOS Catalina to MacOS Big Sur without Usb Stick

- [中文版](blogs/cn-how-I-upgrade-12-mid-catalina-to-bigsur-without-usb-stick.md)

Feel so lucky that I can continue to use my best favorite Macbook Pro to make APPs. My system is based on `MacOS Catalina` since the mid of 2012. It was not supported by Apple Inc. cause it was made before 2013. Generally there is no way to upgrade the new system like `MacOS Big Sur`. But one exception is still there, you can upgrade by yourself. 

First, my catalina system is not so old from the bug sur system, so it is not too difficult to upgrade. But If you have an older Mac computer, you may have more things to do to achive that. Here we just talk about the simplist way to upgrade catalina to big sur.

Then, there are three point you should know that can help you find the way out.

1. You Mac Computer Should have enough space to upgrade, You need two spaces, one is for start installer, it needs over `20Gb`, another is also above `20Gb`, which means you curent catalina system shold at least have `20Gb` free space.

2. You need to download the MacOS Big Sur system package, like [macOS Big Sur 11.6.1 \(20G224\)](https://support.apple.com/en-us/HT211683).

3. you need to download  [big-sur-micropatcher](https://github.com/barrykn/big-sur-micropatcher) to help you to start the installer.

After you get those three things ready. Let's go to do it.

1. You need to install [macOS Big Sur 11.6.1 \(20G224\)](https://support.apple.com/en-us/HT211683) in your Applications category, which the installed path should be `/Applications/Install\ macOS\ Big\ Sur.app/`.

2. You should create a new partition which type is Mac OS X Extended in the Disk Utility Tools. The size is `20Gb` and the name is `bigsur`.

3. Open your terminal, excute the follow cmd: `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia 
--volume /Volumes/bigsur`, which help you to make a bootable volume to install new system.

4. In your terminal, cd to the category `big-sur-micropatcher-0.5.1` which you downloaded and unziped. run `sudo bash micropatcher.sh /Volumes/Install\ macOS\ Big\ Sur` and `sudo bash install-setvars.sh /Volumes/Install\ macOS\ Big\ Sur`.

5. Restart your system, and keep holding the `Option` key, you will enter the Start Screen to choose one to enter. Now you can see two options which include: `EFI Boot` and `Install macOS Big Sur` except your default option. My default option is `MacOS1013`.

6. First you need to choose `EFI Boot`, which help to do the following things: `disabling SIP, 
disabling authenticated root, and enabling TRIM on non-Apple SSDs`. It will close you computer quickly.

7. Then you should power up your computer again, and choose `Install macOS Big Sur`. You will see the restore screen, and click the button of `Install macOS Big Sur`, choose your current system disk to upgrade.
THe left is waiting for the install process is finished.

8. If you find WIFI list is empty, you need to restart system with holding the `Option` key, and choose `Install macOS Big Sur`. Open Terminal in Utilities, run the following cmd: `/Volumes/Image\ Volume/patch-kexts.sh /Volumes/MacOS1013
`, and restart again, you will find WIFI list is normal.

That's all you can do. Good Luck!

![Screenshot](https://adamgogogo.github.io/coding-life/img/1638885880082.jpg)








