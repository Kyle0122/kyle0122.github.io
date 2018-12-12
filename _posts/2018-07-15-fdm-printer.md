---
title: FDM printer 新结构构想
layout: post
date: 2018-07-15 07:10:33 +0000

---
现在流行的3D打印机主要有三种结构，卡笛尔(Cartesian)、三角洲(delta)和core XY，另外还有柱机械臂、柱坐标系(polar)还有hang printer。

像Prusa i3和CR10这样有移动的打印平台的打印机属于Cartesian，而像Ultimaker这样有十字交叉结构和上下移动平台的属于core XY，三种打印机中delta printer的移动质量最小，打印速度最快，但是浪费空间大，并且空间几何计算对性能要求较大。