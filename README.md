# XamarinTest
A test sandbox for Xamarin

For this reproduction case, I followed the steps below. Most of it should be easy to follow in the git commit log as well.
All builds are for configuration Debug|iPhoneSimulator.

Steps
* Created new 'SingleView' iOS project
* Confirmed building
  * Visual Studio on Windows
  * Xamarin Studio on Mac
  * Command line
    * Working directory is same as solution directory
	* /usr/local/bin/xbuild SingleViewExample.sln /p:Configuration="Debug" /p:Platform="iPhoneSimulator" /verbosity:diagnostic
* Added "MissingDependencyLibrary"
  * portable library (iOS, Android, Windows)
  * Has solution GUID FD8664BE-1F5A-4B55-A9CD-E1B3DF9B7EAA
  * No modifications made to SingleView project files
  * Added as a dependency of 'SingleView' project
  * Again, No modifications made to SingleView project files
* Reconfirmed builds on all platforms
* Removed library project files only (no solution or main project changes)
   * Note that this change broke the command line build, see next change.
* Removed library project from building for all configurations
* Added verbose mtouch output flag(s)
* Tested final example build status, captured logs
	* Confirmed build still works on Visual Studio Windows
	* Confirmed build still works on command line
	* Build is now failing in Xamarin Studio Mac, 1 Error, Description:"Project Unavailable", Project:"MissingDependencyLibrary"
	
Log info:
* For command line output in final example case see file [command_line_verbose_log.txt](command_line_verbose_log.txt)
* For Xamarin Studio build output in final example case see file: [Xamarin_Studio_verbose_log.txt](Xamarin_Studio_verbose_log.txt)
* All IDEs and tools should be latest stable versions as of May 25th, 2016. Full information is below
* Help -> About Microsoft Visual Studio -> Copy Info

```
	Microsoft Visual Studio Enterprise 2015
	Version 14.0.25123.00 Update 2
	Microsoft .NET Framework
	Version 4.6.01055

	Installed Version: Enterprise

	Architecture and Modeling Tools   00322-80000-00000-AA455
	Microsoft Architecture and Modeling Tools
		
	UML® and Unified Modeling Language™ are trademarks or registered trademarks of the Object Management Group, Inc. in the United States and other countries.

	Visual Basic 2015   00322-80000-00000-AA455
	Microsoft Visual Basic 2015

	Visual C# 2015   00322-80000-00000-AA455
	Microsoft Visual C# 2015

	Visual C++ 2015   00322-80000-00000-AA455
	Microsoft Visual C++ 2015

	Visual F# 2015   00322-80000-00000-AA455
	Microsoft Visual F# 2015

	Windows Phone SDK 8.0 - ENU   00322-80000-00000-AA455
	Windows Phone SDK 8.0 - ENU

	Application Insights Tools for Visual Studio Package   5.2.60328.3
	Application Insights Tools for Visual Studio

	ASP.NET and Web Tools 2015 (RC1 Update 1)   14.1.11120.0
	ASP.NET and Web Tools 2015 (RC1 Update 1)

	ASP.NET Web Frameworks and Tools 2012.2   4.1.41102.0
	For additional information, visit http://go.microsoft.com/fwlink/?LinkID=309563

	ASP.NET Web Frameworks and Tools 2013   5.2.40314.0
	For additional information, visit http://www.asp.net/

	Azure App Service Tools v2.8.1   14.0.11123.0
	Azure App Service Tools v2.8.1

	Common Azure Tools   1.7
	Provides common services for use by Azure Mobile Services and Microsoft Azure Tools.

	DataFactoryProject   1.0
	Microsoft Data Factory Package

	EditProj   1.0
	This packages allows you to edit project files without the need to unload them first.

	GitHub.VisualStudio   1.0
	A Visual Studio Extension that brings the GitHub Flow into Visual Studio.

	JavaScript Language Service   2.0
	JavaScript Language Service

	JavaScript Project System   2.0
	JavaScript Project System

	JetBrains ReSharper Ultimate 2015.2   Build 103.0.20150818.200216
	JetBrains ReSharper Ultimate package for Microsoft Visual Studio. For more information about ReSharper Ultimate, visit http://www.jetbrains.com/resharper. Copyright © 2016 JetBrains, Inc.

	Microsoft Azure Data Factory Node Node   1.0
	Azure Data Factory extension for Visual Studio Server Explorer.

	Microsoft Azure HDInsight HQL Service   2.0.2900.0
	Language service for Hive query

	Microsoft Azure HDInsight Tools for Visual Studio   2.0.2900.0
	An integrated development environment for HDInsight application development.

	Microsoft Azure Mobile Services Tools   1.4
	Microsoft Azure Mobile Services Tools

	Microsoft Azure Tools   2.8
	Microsoft Azure Tools for Microsoft Visual Studio 2015 - v2.8.31121.1

	Microsoft Team Foundation Server 2015 Power Tools   14.0
	Power Tools that extend the Team Foundation Server integration with Visual Studio.

	Microsoft Visual Studio Process Editor   1.0
	Process Editor for Microsoft Visual Studio Team Foundation Server

	Multilingual App Toolkit   4.0.1573.0
	Multilingual App Toolkit helps you localize your Windows Store app by providing file management, pseudo and machine translation, translation editor, and build integration. http://aka.ms/matinstallv4

	NuGet Package Manager   3.4.1
	NuGet Package Manager in Visual Studio. For more information about NuGet, visit http://docs.nuget.org/.

	PreEmptive Analytics Visualizer   1.2
	Microsoft Visual Studio extension to visualize aggregated summaries from the PreEmptive Analytics product.

	SQL Server Data Tools   14.0.60311.1
	Microsoft SQL Server Data Tools

	TypeScript   1.8.30.0
	TypeScript tools for Visual Studio

	Visual Studio Tools for Universal Windows Apps   14.0.25208.00
	The Visual Studio Tools for Universal Windows apps allow you to build a single universal app experience that can reach every device running Windows 10: phone, tablet, PC, and more. It includes the Microsoft Windows 10 Software Development Kit.

	Xamarin   4.0.3.214 (0dd817c)
	Visual Studio extension to enable development for Xamarin.iOS and Xamarin.Android.

	Xamarin.Android   6.0.3.5 (a94a03b)
	Visual Studio plugin to enable development for Xamarin.Android.

	Xamarin.iOS   9.6.1.8 (3a25bf1)
	Visual Studio extension to enable development for Xamarin.iOS.
```

* Xamarin Studio -> About Xamarin Studio -> Show Details -> Copy Infomration

```
    === Xamarin Studio Enterprise ===

    Version 5.10.3 (build 51)
    Installation UUID: 075488b4-d2e2-45b6-9e91-c78fdcd21926
    Runtime:
    Mono 4.2.4 (explicit/71b88f3)
    GTK+ 2.24.23 (Raleigh theme)

	Package version: 402040004

	=== Xamarin.Profiler ===

	Version: 0.30.0
	Location: /Applications/Xamarin Profiler.app/Contents/MacOS/Xamarin Profiler

	=== Apple Developer Tools ===

	Xcode 7.3.1 (10188.1)
	Build 7D1014

	=== Xamarin.iOS ===

	Version: 9.6.2.4 (Xamarin Enterprise)
	Hash: d8bedd0
	Branch: master
	Build date: 2016-05-05 17:43:01-0400

	=== Xamarin.Android ===

	Not Installed

	=== Xamarin Android Player ===

	Not Installed

	=== Xamarin.Mac ===

	Version: 2.4.2.3 (Xamarin Enterprise)

	=== Build Information ===

	Release ID: 510030051
	Git revision: f3c0d982165f785772d125f02668370d929014fb
	Build date: 2016-03-24 18:51:31-04
	Xamarin addins: ee5cfd3ecb6b20de47c1d25efb9a9abc101e8ce7
	Build lane: monodevelop-lion-cycle6-c6sr3

	=== Operating System ===

	Mac OS X 10.11.5
	Darwin lttimjensen.vcs.coaxis.net 15.5.0 Darwin Kernel Version 15.5.0
	Tue Apr 19 18:36:36 PDT 2016
	root:xnu-3248.50.21~8/RELEASE_X86_64 x86_64
```

