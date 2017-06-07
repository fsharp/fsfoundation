---
layout: default
title: Use F# on Linux | The F# Software Foundation
headline: Use F# on Linux
---

To help with Linux packages, please join the [F# Core Engineering Group](http://fsharp.github.io).  You can also 
[submit an edit to this page](https://github.com/fsharp/fsfoundation/blob/gh-pages/use/linux/index.md).

### Option 1: Use the F# Debian/Ubuntu packages 

To use the latest stable version of the F# Debian/Ubuntu package, it is highly
recommended that you:

1. [Follow these instructions](http://www.mono-project.com/docs/getting-started/install/linux/#debian-ubuntu-and-derivatives). 

2. Then install packages `mono-complete` and `fsharp`.

        sudo apt-get update
        sudo apt-get install mono-complete fsharp

This installs `fsharpc` and `fsharpi`. If you don't have access to these repositories, compile from source or see Option 6 below. Once installed, see the [Linux and Cross-Platform Development Guide](/guides/mac-linux-cross-platform) to
go further.

F# is also available as a [Debian package](http://packages.qa.debian.org/f/fsharp.html) though the package
tends to be less up-to-date than the packages above.

<br />

### Option 2: Install Visual Studio Code

![logo](/images/thumbs/VSCode.png)&nbsp;[Visual Studio Code](https://code.visualstudio.com) is a free, [open source](https://github.com/microsoft/vscode), cross platform source code editor
supporting [a lot of languages](https://code.visualstudio.com/docs/languages/overview).
F# is supported by the [Ionide](http://ionide.io/) project and is a nice integration.

1. Install [Visual Studio Code](https://code.visualstudio.com/download) for Linux
2. Press `Ctrl+P` and enter the following to install the Ionide package for VS Code.

        ext install Ionide-fsharp

You will also need to install the F# packages from Step 1.

<br />

### Option 3: Install JetBrains Rider

![logo](/images/thumbs/rider.png)&nbsp;[JetBrains Rider](https://www.jetbrains.com/rider) is a cross-platform .NET IDE built using IntelliJ and ReSharper technology. It offers support for .NET and .NET Core applications on all platforms.

1. Install [JetBrains Rider](https://www.jetbrains.com/rider/download/) for Linux.
2. [Follow these instructions](http://www.mono-project.com/download/#download-lin-ubuntu). 
3. Then install packages `mono-complete`, `msbuild` and `fsharp`.

        sudo apt-get update
        sudo apt-get install mono-complete msbuild fsharp
		
4. (optional) Install latest `dotnet-dev-x.y.z` [.NET Core packages](https://www.microsoft.com/net/core#linuxubuntu)

<br />

### Option 4: Build and install the F# runtime, compiler and tools


1. Get Mono, the cross-platform, open source .NET runtime implementation used by F#. Preferably use a package from your distribution or Xamarin. If this is not possible, [install from source by following these instructions](https://github.com/mono/mono).

   Note that if you are installing to a private prefix, [follow these instructions](http://mono-project.com/Parallel_Mono_Environments) and ensure `LD_LIBRARY_PATH` includes the "lib" directory of that prefix location and `PKG_CONFIG_PATH` includes the "lib/pkgconfig" directory of that prefix location, e.g.
   
        export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/user/mono/lib/
        export PKG_CONFIG_PATH=/home/user/mono/lib/pkgconfig/

2. Build and install the F# Compiler (open edition) from source. If using a VM or other memory-constrained system, be aware that errors during compilation may be due to insufficient memory (in particular error 137).

        sudo apt-get install autoconf libtool pkg-config make git automake
        git clone https://github.com/fsharp/fsharp
        cd fsharp
        ./autogen.sh --prefix /usr
        make
        sudo make install

   If installing to a different prefix, use the same prefix as for the Mono runtime above.

Once installed, see the [Linux and Cross-Platform Development Guide](/guides/mac-linux-cross-platform) to
go further.


<br />

### Option 5: Get F# on CentOS (RHEL/Amazon/Fedora)

To use the latest stable version of the F# RHEL/CentOS/Amazon/Fedora package, it is highly
recommended that you:

1. [Follow these instructions](http://www.mono-project.com/docs/getting-started/install/linux/#centos-7-fedora-19-and-later-and-derivatives). 

2. Then install packages `mono-complete` and `fsharp`.

        sudo yum update
        sudo yum install mono-complete fsharp

Once installed, see the [Linux and Cross-Platform Development Guide](/guides/mac-linux-cross-platform) to
go further.

<br />

### Option 6: Get F# on Gentoo (Sabayon/Funtoo/Calculate)

From portage tree:

       emerge fsharp

Alternatively there is an overlay available with current versions of various .NET programs, including F#, FAKE, NuGet and others.

1. Add the "dotnet" overlay from layman. (If you need to set it up, there is a [Manual](http://www.gentoo.org/proj/en/overlays/userguide.xml) on the Gentoo site.)
   
       layman -a dotnet 
   
2. Now you can build F#.
   
       emerge fsharp
   
3. (Optional) There are emacs mode and monodevelop bindings, you can chose what you want by setting use flags alike in following example:
   
       USE="+emacs -monodevelop" emerge fsharpbinding

Once installed, see the [Linux and Cross-Platform Development Guide](/guides/mac-linux-cross-platform) to
go further.

<br />

### Option 7: Use a Vagrant VM on Windows

To use F# on Linux VMs on Windows, use [F# with Vagrant](http://christoph.ruegg.name/blog/test-csharp-fsharp-on-mono-with-vagrant.html).


<br />

### Option 8: Slackware Slackbuild

1. Get Mono Slackbuild from this page [http://slackbuilds.org/repository/14.1/development/mono/](http://slackbuilds.org/repository/14.1/development/mono/) and run :

     ./mono.SlackBuild

2. Get last FSharp Slackbuild from this page [http://slackbuilds.org/repository/14.1/development/fsharp/](http://slackbuilds.org/repository/14.1/development/fsharp/) and run :

    ./fsharp.SlackBuild
   
<br />

### Option 9: Using Nix on any Linux distribution or Mac OS X

1. Install Nix if you don't already have it:

        sudo mkdir /nix && sudo chown `id -u`.`id -g` /nix # create /nix
        sudo -k                                            # give up root privileges
        curl https://nixos.org/nix/install | bash          # install Nix
        . $HOME/.nix-profile/etc/profile.d/nix.sh          # update PATH accordingly
 
2. Get F#

        nix-env -iA nixpkgs.fsharp
    
3. You might also like…

        # List all the .NET packages that are readily available in the Nix
        # package collection:
        nix-instantiate --eval --expr 'with import <nixpkgs> {};
                                         lib.attrNames dotnetPackages' 
    
        # Download FSharp.Data in the Nix store and make it available in ./FSData
        nix-build '<nixpkgs>' -A dotnetPackages.FSharpData --out-link FSData

Find out more about the [Nix package manager](https://nixos.org/nix/) and [NixOS](https://nixos.org/) (the purely functional Linux distribution based on it)

Explore (and contribute to) the collection of .NET applications and libraries in the [Nixpkgs GitHub repo](https://github.com/NixOS/nixpkgs/blob/master/pkgs/top-level/dotnet-packages.nix)
   
<br />
