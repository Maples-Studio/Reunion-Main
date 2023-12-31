# Reunion-main
红色警戒2重聚未来（原名红色警戒2重聚2023）是一款致力于采用新技术改善官方红警体验的MOD，整合了官方原版与尤里的复仇，拥有功能丰富的DTA客户端，让玩家可以进行战役选关、换主题、换单位皮肤、进行对局细化规则设置、添加扩展等操作。并且，重聚未来还拥有用户文档与开发者文档

内容上，重聚未来本身并没有原创的剧情、阵营以及战役，但是整合了大量的遭遇战地图、遭遇战模式、新的AI等内容，并且将被授权引入其他MOD，让你可以在重聚未来中玩其他MOD

[相关文档](https://support.qq.com/products/608985/faqs/147524)<br/><br/>
[重聚未来作者的bilibili主页](https://space.bilibili.com/471856024) | [重聚未来制作组的bilibili主页](https://space.bilibili.com/1993968753)

### 为保证服务器安全性，我们的中国官网服务器是屏蔽海外IP的，海外用户请访问国际站下载<br/>
重聚未来官网：[中国站](https://www.yra2.com) | [国际站](https://www.ru2023.top)

如果你在游玩期间碰到了问题，可以加入官网的QQ群或者在[兔小巢](https://support.qq.com/products/608985)进行反馈

# CnCNet Client #

The MonoGame / XNA CnCNet client, a platform for playing classic Command & Conquer games and their mods both online and offline. Supports setting up and launching both singleplayer and multiplayer games with [a CnCNet game spawner](https://github.com/CnCNet/ts-patches). Includes an IRC-based chat client with advanced features like private messaging, a friend list, a configurable game lobby, flexible and moddable UI graphics, and extras like game setting configuration and keeping track of match statistics. And much more!

Targets
-------

The primary targets of the client project are


* [Dawn of the Tiberium Age](https://www.moddb.com/mods/the-dawn-of-the-tiberium-age)
* [Twisted Insurrection](https://www.moddb.com/mods/twisted-insurrection)
* [Mental Omega](https://www.moddb.com/mods/mental-omega)
* [CnCNet Yuri's Revenge](https://cncnet.org/yuris-revenge)


However, there is no limitation in the client that would prevent incorporating it into other projects. Any game or mod project that utilizes the CnCNet spawner for Tiberian Sun and Red Alert 2 can be supported. Several other projects also use the client or an unofficial fork of it, including [Tiberian Sun Client](https://www.moddb.com/mods/tiberian-sun-client), [Project Phantom](https://www.moddb.com/mods/project-phantom), [YR Red-Resurrection](https://www.moddb.com/mods/yr-red-resurrection), [The Second Tiberium War](https://www.moddb.com/mods/the-second-tiberium-war) and [CnC: Final War](https://www.moddb.com/mods/cncfinalwar).

Development requirements
------------------------

The client has 4 builds: Windows DirectX11, Windows OpenGL, Windows XNA and Universal OpenGL.
* The DirectX11 and OpenGL builds rely on MonoGame.
* The XNA build relies on Microsoft's XNA Framework 4.0 Refresh.

Building the solution for any platform requires Visual Studio 2022 17.3 or newer and/or the .NET SDK 7.0. A modern version of Visual Studio Code, MonoDevelop or Visual Studio for Mac could also work, but are not officially supported.
To debug WindowsXNA builds the .NET SDK 7.0 x86 is additionally required.
When using the included build scripts PowerShell 7.2 or newer is required.

Compiling and debugging
-----------------------

* Compiling itself is simple: assuming you have the .NET 7.0 SDK installed, you can just open the solution with Visual Studio and compile it right away.
* When built as a debug build, the client executable expects to reside in the same directory with the target project's main game executable. Resources should exist in a "Resources" sub-directory in the same directory. The repository contains sample resources and post-build commands for copying them so that you can immediately run the client in debug mode by just hitting the Debug button in Visual Studio.
* When built in release mode, the client executable expects to reside in the "Resources" sub-directory itself. In target projects, the client libraries are named `clientdx.dll`, `clientogl.dll` and `clientxna.dll` respectively for each platform.
* When built on an OS other than Windows, only the Universal OpenGL build is available.
* The `BuildScripts` directory has automated build scripts that build the client for all platforms and copy the output files to a folder named `Compiled` in the project root. You can then copy the contents of this `Compiled` directory into the `Resources` sub-directory of any target project.

End-user usage
--------------

* Windows: Windows 7 SP1 or higher is required. The DirectX11 build is preferred. The XNA build is intended for those whose GPU does not properly support DX11.
* Other OS: Use the Universal OpenGL build.

End-user requirements
---------------------

Windows requirements:
* The [.NET 7.0 Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime) for your specific platform.
* Additionally the [.NET 7.0 Desktop Runtime x86](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-desktop-7.0.0-windows-x86-installer) used by the client launcher and the XNA build.

The XNA build additionally requires:
* [Microsoft XNA Framework Redistributable 4.0 Refresh](https://www.microsoft.com/en-us/download/details.aspx?id=27598).

Windows 7 SP1 and Windows 8.x additionally require:
* Microsoft Visual C++ 2015-2019 Redistributable [64-bit](https://aka.ms/vs/16/release/vc_redist.x64.exe) / [32-bit](https://aka.ms/vs/16/release/vc_redist.x86.exe).

Windows 7 SP1 additionally requires:
* KB3063858 [64-bit](https://www.microsoft.com/download/details.aspx?id=47442) / [32-bit](https://www.microsoft.com/download/details.aspx?id=47409).


Other OS requirements:
* The [.NET 7.0 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime) for your specific platform.

Client launcher
---------------

This repository does not contain the client launcher (for example, `DTA.exe` in Dawn of the Tiberium Age) that selects which platform's client executable is most suitable for each user's system. For that, see [dta-mg-client-launcher](https://github.com/CnCNet/dta-mg-client-launcher).

Branches
--------

Currently there are only two major active branches. `develop` is where development happens, and while things should be fairly stable, occasionally there can also be bugs. If you want stability and reliability, the `master` branch is recommended.

Screenshots
-----------

![Screenshot](cncnetchatlobby.png?raw=true "CnCNet IRC Chat Lobby")
![Screenshot](cncnetgamelobby.png?raw=true "CnCNet Game Lobby")
