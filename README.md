**中文** | **[English](#english)**

> **🧭 收徒 · 我靠这套路子吃饭，你也可以**
>
> 从「发现一个痛点」→「写个几百行的小工具」→「挂上资源位」→「有人付钱」，全流程我在这篇里讲透了。
> 想学这门手艺的，点这里：**[👉 收徒说明（知乎）](https://zhuanlan.zhihu.com/p/54351262)**

> **🧭 收徒 · 我靠这套路子吃饭，你也可以**
>
> 从「发现一个痛点」→「写个几百行的小工具」→「挂上资源位」→「有人付钱」，全流程我在这篇里讲透了。
> 想学这门手艺的，点这里：**[👉 收徒说明（知乎）](https://zhuanlan.zhihu.com/p/54351262)**

# ScrollSound

**鼠标滚一下任务栏，音量就变了。**

不用去点右下角那个喇叭，不用等它弹出来再找那个小滑块，也不用把鼠标从屏幕中间一路挪到底部再挪回来。

[**⬇ 下载最新版（Project1.exe）**](https://github.com/Buir5/-Scroll-the-mouse-on-the-taskbar-to-change-the-system-volume/releases/download/%E7%B3%BB%E7%BB%9F%E9%9F%B3%E9%87%8F/Project1.exe)

Windows 10 / 11 · 单文件 105 KB · 免安装 · 不联网

![预览](https://github.com/user-attachments/assets/dbf60db0-a5c4-4ca2-948e-cff13f080848)

## 这玩意儿解决什么问题

我一天要调十几次音量。看视频嫌吵调小，切到语音会议调大，游戏里队友开麦再调一次。

每一次都要：鼠标移到右下角 → 点喇叭 → 找到那个滑块 → 拖 → 点空白处关掉。五步，十几次，一天七十步。

后来我想明白一件事：**任务栏本来就是一条空的、静止的、没人碰的横条**。那为什么不把它当成一个音量旋钮？

于是就有了这个东西。滚轮向上：加。向下：减。就这样。

## 三个功能，没有第四个

| 功能 | 说明 |
| --- | --- |
| **滚轮调音量** | 任务栏空白处上下滚动，音量一格一格走，右下角同步弹出系统原生音量条 |
| **开机自启** | 写一条注册表 Run 项，登录就生效，不弹窗、不弹广告 |
| **重新 HOOK** | 资源管理器崩溃 / 重启任务栏之后钩子会断，右键托盘图标点一下「重新 HOOK」立刻恢复 |

## 怎么用

1. 下载 `Project1.exe`，双击运行（绿色单文件，不用安装）
2. 鼠标移到**任务栏的空白处**——不是图标上，是图标之间的空白
3. 上下滚

**滚了没反应？** 十有八九是钩子掉了。右键托盘图标 → **重新 HOOK** → 再滚一次。

![使用演示](https://github.com/user-attachments/assets/0ab5c839-04bd-4d80-8f6a-f5c50dbfa748)

## 常见问题

**杀毒软件报毒？**
它需要装一个全局鼠标钩子来监听任务栏区域的滚轮事件，这个行为在杀软眼里和键盘记录器是同一类 API，所以会敏感。程序本身：没有网络请求、没有驱动、没有注入其他进程、没有写系统目录。不放心就扔沙箱里跑一遍，或者直接看资源监视器——它一条外连都没有。

**Win11 某些版本没反应？**
微软在 22H2 之后重写过任务栏，部分版本上原生钩子会失效。先试「重新 HOOK」，还不行就是这一版的任务栏结构变了，等我更新。

**会不会影响我在网页里滚页面？**
不会。只有在任务栏那块矩形区域内滚动才生效，鼠标在浏览器窗口里怎么滚都不管。

**怎么退出？想临时关掉怎么办？**
右键托盘图标，菜单里有「退出」和「重新 HOOK」。没有后台服务、没有开机常驻的隐藏进程，退出就是真没了。

**滚动一格音量变多少？**
跟系统音量条同一步进，滚一格跳一格，不会出现「滚一下从 40 直接到 100」这种事。

## 更新日志

**v1.0**
- 滚轮调音量（任务栏空白处，滚一格一格）
- 开机自启
- 重新 HOOK（资源管理器重启后可恢复）

## 作者

作者：[**知乎老哥**](https://www.zhihu.com/people/svip3) —— 点开在新窗口打开

<a id=english></a>

# ScrollSound

> Scroll the empty area of the Windows taskbar — system volume changes. One 105 KB exe, no installer.

## What it is

A tiny Windows utility that hooks the mouse wheel over the taskbar and maps it to the system volume slider. Scroll up to raise, scroll down to lower. It does not touch web page scrolling, so you can still scroll inside Chrome normally.

## Install and use

1. Download `Project1.exe` from the Releases page.
2. Put it in a permanent folder and double-click — no installer, no dependencies.
3. Scroll on the taskbar to change volume.
4. Right-click the tray icon (or the exe menu) to toggle autostart, re-hook, or exit.

Because it installs a global low-level mouse hook, Windows Defender SmartScreen and some AV engines flag it. That is a false positive typical for hook-based utilities: there is no network code, no persistence beyond the optional autostart entry, and no file access.

## FAQ

Does it affect scrolling inside apps? No — the hook only reacts when the cursor is over the taskbar window.
Nothing happens after a Windows update? Windows 11 22H2+ rewrote the taskbar; re-hook from the menu, or update to the latest build.
How much does one notch change? One notch, step matching the system volume step.

## Author

[知乎老哥](https://www.zhihu.com/people/svip3) — MIT licensed, keep the credit if you redistribute.

> **🧭 收徒 · 我靠这套路子吃饭，你也可以**
>
> 从「发现一个痛点」→「写个几百行的小工具」→「挂上资源位」→「有人付钱」，全流程我在这篇里讲透了。
> 想学这门手艺的，点这里：**[👉 收徒说明（知乎）](https://zhuanlan.zhihu.com/p/54351262)**

> **🧭 收徒 · 我靠这套路子吃饭，你也可以**
>
> 从「发现一个痛点」→「写个几百行的小工具」→「挂上资源位」→「有人付钱」，全流程我在这篇里讲透了。
> 想学这门手艺的，点这里：**[👉 收徒说明（知乎）](https://zhuanlan.zhihu.com/p/54351262)**
