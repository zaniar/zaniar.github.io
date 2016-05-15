---
layout: post
title: "Installing Unity on ArchLinux: Huge AUR Package"
---
I'm talking about the game engine one, not the one made by Canonical.

Some months ago I installed ArchLinux on my laptop. That was my first time to try ArchLinux. Around that time, I found out that the Linux version of Unity is available. Actualy I have heard about it some years ago, but I heard that at that time it was not stable enough. So, I was curious to try it and see if the current version will be usable enough.

Fortunately, Unity is available on AUR repository. I have Yaourt installed. So, I just need to run:  
```
# yaourt unity-editor
```  
Then I just need to follow the flow of Yaourt.

Unfortunately I got message like this  
```
...
tar: unity-editor-5.3.2f1/Editor/libcef.so: Cannot write: No space left on device
...
/usr/lib/yaourt/pkgbuild.sh: line 63: echo: write error: No space left on device
/usr/lib/yaourt/pkgbuild.sh: line 64: echo: write error: No space left on device
/usr/lib/yaourt/pkgbuild.sh: line 65: echo: write error: No space left on device
/usr/lib/yaourt/pkgbuild.sh: line 66: echo: write error: No space left on device
/usr/lib/yaourt/pkgbuild.sh: line 67: echo: write error: No space left on device
/usr/lib/yaourt/pkgbuild.sh: line 68: echo: write error: No space left on device
```  

By default, yaourt extract the package to /tmp directory then copy the files to the installation directory. Unfortunately, my /tmp is set to 2 GB. The download size of Unity package is around 1.3 GB. The installation failed because it have no space left to write the files.

After many attempt to tackle this problem, finally I got the solution. Yaourt has --tmp option that allow you to specified the temporary directory used by Yaourt. So, I create a temporary directory on my home directory and have Yaourt to use that directory.  
```
# yaourt --tmp ~/.tmp unity-editor
```  
