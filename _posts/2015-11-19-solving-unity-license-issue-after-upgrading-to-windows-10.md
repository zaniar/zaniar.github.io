---
layout: post
title: Solving Unity License Issue After Upgrading to Windows 10
tags: unity, windows, windows 19, license
---

Few days ago I upgrading my workstation from Windows 8.1 to Windows 10. I have Unity 5 installed on that workstation. Today, for the first time after upgrading to Windows 10, I double-clicking the Unity icon to run it. What I get is a window telling that there is an issue with license and I need to reactivate it. There is a button with "Reactivate" written in it. Clicked that button, filling the usual sign in form, and ... it does not works.

A little consultation session with Google getting me to [this Unity Answer page](http://answers.unity3d.com/questions/888003/getting-unity-to-work-on-windows-10.html). The answers from *misterk99*, who was also post the question, is solving the issue. The solution is **deleting the license file**. For windows it can be found in `C:\ProgramData\Unity\Unity_v5.x.ulf`

I hope this will help you when you run into the same issue.