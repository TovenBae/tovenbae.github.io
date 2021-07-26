---
title: "맥북 배터리 소모시 대기모드 설정 변경"
date: 2020-02-10 11:46:28 -0400
categories: MacBook
---

```
baesunghan  ~/git/bj/mcp   master  pmset -g | grep standbydelay
 standbydelaylow      10800
 standbydelayhigh     86400
 baesunghan  ~/git/bj/mcp   master  sudo pmset standbydelaylow 1800 standbydelayhigh 3600
Password:
 baesunghan  ~/git/bj/mcp   master  pmset -g | grep standbydelay
 standbydelaylow      1800
 standbydelayhigh     3600
 baesunghan  ~/git/bj/mcp   master 
 ```