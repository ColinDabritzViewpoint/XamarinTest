# XamarinTest
A test sandbox for Xamarin

Steps
* Created new 'SingleView' iOS project
* Confirmed building
  * Visual Studio on Windows
  * Xamarin Studio on Mac
  * Command line
    * Working directory is same as solution directory]
	* /usr/local/bin/xbuild SingleViewExample.sln /p:Configuration="Debug" /p:Platform="iPhoneSimulator" /verbosity:detailed
* Added "MissingDependencyLibrary"
  * portable library (iOS, Android, Windows)
  * Has solution GUID FD8664BE-1F5A-4B55-A9CD-E1B3DF9B7EAA
  * No modifications made to SingleView project files
  
TODOs:
* Created a portable library
* Made portable library project a dependency - but NOT A REFERENCE! Note main project did not change.
* Confirmed this ran from Visual Studio Windows and Xamarin Studio Mac
* deleted files for portable library project (did NOT edit solution dependency)
* Opening on windows confirms dependency is missing
* Confirmed build still works on Visual Studio Windows
* Confirmed Build works from xbuild command line:
    EXAMPLE HERE
* Build fails with EXAMPLE ERROR on Xamarin Studio Mac

Log info:
* Verbosity - Increase logging
* Provide full logs
* Provide requested info about environments
* provide commit log numbers for key points