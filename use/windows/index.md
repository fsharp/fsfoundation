---
layout: default
title: Use F# on Windows | The F# Software Foundation
headline: Use F# on Windows
---


### Option 1: Install the Visual F# Tools from Microsoft

![logo](/images/thumbs/vstudio.png)&nbsp;On Windows, F# programmers commonly use the Visual F# Tools from Microsoft.

   Install a free trial edition of [Visual Studio 2013  (Professional or higher)](http://www.visualstudio.com/downloads/download-visual-studio-vs)

OR:

   Install the free [Visual Studio 2013 Desktop Express](http://www.microsoft.com/download/details.aspx?id=40787) plus the free [Visual F# Tools 3.1.1](http://www.microsoft.com/download/details.aspx?id=41654)

OR:

   Install the free [Visual Studio 2013 Web Express](http://www.microsoft.com/download/details.aspx?id=40747) plus the free [Visual F# Tools 3.1.1](http://www.microsoft.com/download/details.aspx?id=41654)

OR:

   Install the free [Visual Studio Express 2012 for Web](http://www.microsoft.com/en-us/download/details.aspx?id=30669)  plus the free [Visual F# Tools 3.0](http://go.microsoft.com/fwlink/?LinkID=261287)


The tools include the command-line compiler (`fsc.exe`) and F# Interactive (`fsi.exe`).
See [fsharp.net](http://msdn.microsoft.com/en-us/vstudio/hh388569.aspx) for more information about the Visual F# Tools from Microsoft.

##### ![logo](/images/thumbs/FSharpVSPowerTools.png)&nbsp;[Visual F# Power Tools](http://fsprojects.github.io/VisualFSharpPowerTools/) #####

Optionally, install the community-provided [Visual F# Power Tools](http://fsprojects.github.io/VisualFSharpPowerTools/),
for use with Visual Studio 2012 and 2013 (Professional or higher). They include [source code formatting](http://fsprojects.github.io/VisualFSharpPowerTools/codeformatting.html), 
[auto-generating XML Docs](http://fsprojects.github.io/VisualFSharpPowerTools/xmldoc.html), 
[source code formatting](http://fsprojects.github.io/VisualFSharpPowerTools/codeformatting.html), 
[navigation bar](http://fsprojects.github.io/VisualFSharpPowerTools/navbar.html), 
[highlight](http://fsprojects.github.io/VisualFSharpPowerTools/highlightusage.html) and [find](http://fsprojects.github.io/VisualFSharpPowerTools/findallreferences.html) references, 
[rename refactoring](http://fsprojects.github.io/VisualFSharpPowerTools/rename.html),
[depth colorizer](http://fsprojects.github.io/VisualFSharpPowerTools/depthcolorizer.html),
[implement interface](http://fsprojects.github.io/VisualFSharpPowerTools/implementinterface.html),
[record stub generation](http://fsprojects.github.io/VisualFSharpPowerTools/recordstubgeneration.html),
[union pattern match case generation](http://fsprojects.github.io/VisualFSharpPowerTools/unionpatternmatchcasegeneration.html) and the
[navigate-to command](http://fsprojects.github.io/VisualFSharpPowerTools/navigateto.html).

##### ![logo](/images/thumbs/vstudio.png)&nbsp;Note to ReSharper users #####

With some versions of ReSharper, the `Alt+Enter` shortcut key for the `Execute in Interactive`
command of the Visual F# Tools  doesn't work, as ReSharper overrides this for its own purposes.
To fix this, either upgrade to ReSharper 8.0.10.1959 or greater, or install the [resharper-fsi-friendly](https://github.com/citizenmatt/resharper-fsi-friendly) plugin.

If you are using Visual F# Power Tools along side with ReSharper, there is a [known issue](http://youtrack.jetbrains.com/issue/RSRP-409199) where some F# commands are hidden by ReSharper. Until it is fixed, you can workaround by disabling the ReSharper option "Hide overridden Visual Studio menu items" (ReSharper -> Options -> Keyboard & Menus).

<br />

### Option 2: Install F# and Xamarin Studio 

![logo](/images/thumbs/xamarin-studio.png)&nbsp;[Xamarin Studio](http://xamarin.com/studio) is a free IDE for general purpose development with commercial add-ins for mobile development. [MonoDevelop](http://monodevelop.com) is a free and open source IDE based on the same code.  F# can be used with either.

1. Install the free standalone F# compiler tools, following _Option 1_ above or _Option 3_ below. 
2. Install [Xamarin Studio](http://xamarin.com/studio) or [MonoDevelop](http://monodevelop.com) for Windows

<br />


### Option 3: Install the free F# compiler and tools alone

If you're just looking for F# command-line tools, e.g. for a build server or cloud VM image, then use the 
following requirements and installation steps:

1. Requires .NET 4.5:

   - On Windows 8 and Windows 2012 Server, this is already present by default
   
   - On Windows 7 and Windows 2008 Server, [install .NET 4.5](http://www.microsoft.com/net/download) from Microsoft

2. Requires the Windows SDK:

   - On Windows 8.1 use the [Windows 8.1 and .NET 4.5.1 SDK](http://msdn.microsoft.com/windows/desktop/bg162891) from Microsoft
   
   - On Windows 8 or Windows 2012 Server use the [Windows 8 and .NET 4.5 SDK](http://msdn.microsoft.com/windows/hardware/hh852363.aspx) from Microsoft
   
   - On Windows 7 or Windows 2008 Server use the [Windows 7 and .NET 4.0 SDK](http://www.microsoft.com/download/details.aspx?id=8279) from Microsoft
   
3. [Install the free Visual F# Tools 3.1.1](http://www.microsoft.com/download/details.aspx?id=41654) from Microsoft

   Alternatively, do a quiet install from a PowerShell administrator prompt (the URL is the redirect of the above). 

        $webclient = New-Object Net.WebClient
        $url = 'http://download.microsoft.com/download/3/0/A/30A5D6DD-5B5C-4E06-B331-A88AA0B53150/FSharp_Bundle.exe'
        $webclient.DownloadFile($url, "$pwd\FSharp_Bundle.exe")
        .\FSharp_Bundle.exe /install /quiet

4. Apply [the additional installation step described here](http://stackoverflow.com/a/21318488) in order to 
   build existing F# project files.

The compiler tools are installed at

    C:\Program Files (x86)\Microsoft SDKs\F#\3.1\Framework\v4.0\fsc.exe
    C:\Program Files (x86)\Microsoft SDKs\F#\3.1\Framework\v4.0\fsi.exe
    C:\Program Files (x86)\Microsoft SDKs\F#\3.1\Framework\v4.0\fsiAnyCpu.exe
    
If you're looking for Visual F# Tools 3.0 specifically, its standalone version could be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=261286). 
    
<br />

### Option 4: Install Tsunami

[Tsunami](http://tsunami.io) is an innovative fully featured F# IDE. 
It has a number of unique features ideally suited for Big Data, Data Science and Machine Learning. It is capable of being embedded directly into other Desktop Applications and Websites.

- Desktop: Install MSI from [Download](http://tsunami.io/download.html)
- Browser: Embed the object in [Cloud Tsunami](http://tsunami.io/cloud_tsunami.html)


<br />

### Option 5: Build F# from source

* Build and contribute to the F# compiler and library from [the source](http://visualfsharp.codeplex.com)

