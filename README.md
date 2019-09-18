# SOIL (Build SOIL.a in Mac OS and Use SOIL in XCode)

## Introduction:

 SOIL is a tiny C library used primarily for uploading textures into OpenGL. It is based on stb_image version 1.16, the public domain code from Sean Barrett (found [here](https://github.com/nothings/stb) ). I have extended it to load TGA and DDS files, and to perform common functions needed in loading OpenGL textures. SOIL can also be used to save and load images in a variety of formats (useful for loading height maps, non-OpenGL applications, etc.)

## Download: 

 You can grab the latest version of SOIL [here](http://www.lonesock.net/soil.html). (July 7, 2008: see the change log at the bottom of this page.)You can also checkout the latest code from the new SVN repository, login as guest/guest:svn://www.twisted-works.com/jdummer/public/SOIL(thanks for the SVN hosting, Sherief!) 

## License: 
 Public Domain 
 
 ## Read me
 1、This is a clone repository of http://www.lonesock.net/soil.html  .Convenient to use with github
 
 2、This repository support mac os to make install library

 3、If you make install and met error like 
 
 Error: In file included from /Users/thomasuster/haxe/haxe_libraries/nme-toolkit/6.2.0/haxelib/sdl/src/video/cocoa/SDL_cocoakeyboard.m:31:
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/System/Library/Frameworks/Carbon.framework/Headers/Carbon.h:34:10: fatal error: 'CarbonSound/CarbonSound.h' file not found
#include <CarbonSound/CarbonSound.h>
         ^~~~~~~~~~~~~~~~~~~~~~~~~~~
         
   when you make install the code. You can open Carbon.h and commente the code "#include <CarbonSound/CarbonSound.h>" and 
   
   "#include <NavigationServices/NavigationServices.h>" 
   
   4、I use SQIL with XCode, when I run my OpenGL project, there are the error:
   
   Undefined symbols for architecture x86_64:
  "_CFBundleCreate", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
  "_CFBundleGetFunctionPointerForName", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
  "_CFRelease", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
  "_CFStringCreateWithCString", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
  "_CFURLCreateWithFileSystemPath", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
  "___CFConstantStringClassReference", referenced from:
      CFString in libSOIL.a(SOIL.o)
  "_kCFAllocatorDefault", referenced from:
      _query_DXT_capability in libSOIL.a(SOIL.o)
ld: symbol(s) not found for architecture x86_64

 You need to add Cocoa.framework to fix these errors. project TARGETS -> Build Phases -> Link Binary With Libraries -> add 
 Cocoa.framework and run your project. it's allright

   
   
