extract AAX_SDK_1p0p6.zip here 

make the following mods to compile on 10.68 / Xcode 3.26

  - set SDKROOT to macosx10.5 for debug and release targets of AAXLibrary static lib
 
  - modify ExamplePlugIns/Common/Mac/CommonDebugSettings.xcconfig and ExamplePlugIns/Common/Mac/CommonReleaseSettings.xcconfig...

  GCC_VERSION = com.apple.compilers.gcc.4_2
  SDKROOT = macosx10.5
  MACOSX_DEPLOYMENT_TARGET = 10.5
  ARCHS = x86_64 i386

  - comment out/fix error AAX_CInstrumentParameters.cpp:75: error: 'index' cannot appear in a constant-expression


On windows you need to open Libs/AAXLibrary/WinBuild/AAXLibrary.vcproj with VS2010 in order to upgrade the project. You will also need to set the project to link statically to the MSVC2010 runtime library - change to /MT rather than /MD