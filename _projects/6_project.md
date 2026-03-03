---
layout: page
title: 基于液晶电光效应的光学混沌系统构建
description: 混沌运动是非线性系统的典型行为，是一种复杂、不可预测的动态行为，通常表现为似乎无规律的波动或振荡。
img: /assets/img/chaos/chaos.png
importance: 2
category: 学习内容
---

> 此章用以回顾 2023 年暑期参加大物实验建立的光学混沌模型，感谢叉歪和 lucky 的鼎力合作才使得这个项目顺利完成。同时感谢赵改清老师和 206 实验室的所有帮助，老赵带领的 206 团队百花齐放人才辈出。

## 摘要

混沌运动是非线性系统的典型行为，是一种复杂、不可预测的动态行为，通常表现为似乎无规律的波动或振荡。液晶分子同时具有有序性和流动性，具备独特的电光双稳特性，是研究光学混沌的理想选择。液晶的电光效应是指液晶盒在受到外界电场的作用下，其光学性质发生改变。基于近代物理实验中的基础实验“液晶的电光效应”，本团队采用 $$ 40^\circ $$ 扭曲向列相液晶盒，设计了一套用于深入研究液晶电光效应的复杂情况和光学混沌的实验仪器，构建了基于液晶本质特性的反馈公式和光学混沌系统的理论模型。通过计算机仿真模拟出周期态和混沌态的液晶光学性质，验证了所构建的光学混沌系统模型的有效性。

## 引言

液晶光学双稳性的研究始于 20 世纪后半叶。研究人员发现，当某些液晶系统受到外部光场的作用时，它们在相同的条件下会表现出两种稳定状态。自 1969 年 Seidel 和 Szöke 提出光学双稳态理论以来，该理论得到了完善的发展 [[1,2]]。Ikeda 等人在理论上指出光学双稳系统在失稳情况下可能出现混沌现象 [[3]]。

随着进入 21 世纪，光学混沌在通信与信息处理等领域的应用日益受到关注。J. P. Toomey 在 2001 年提出利用混沌半导体激光器进行安全通信的方法 [[8]]。目前的研究人员越来越有兴趣将计算机技术与实验研究相结合，以更好地理解和预测液晶中光学双稳性和混沌的动力学。

## 实验原理与设计

### 1. 实验原理

#### 液晶与扭曲向列相液晶盒
液晶作为一种处于固液之间的相态，具有各向异性和弹性性质。本次实验采取的是 $$ 40^\circ $$ 扭曲向列相液晶盒（TN-LC）。液晶盒的内部结构如图 1 所示：

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/1.png" title="液晶盒内部结构示意图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 1：扭曲向列相液晶盒内部结构。
</div>

#### 液晶的电光效应
液晶电光效应是指对液晶盒导电层施加外界电场时，液晶分子的长轴会重新排列，趋向于与电场方向平行。如图 2 所示，当自然光通过第一层偏振膜后变成线偏振光，经过液晶分子后发生旋光效应。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/2.png" title="液晶分子受电场调控示意图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 2：液晶分子的旋光效应及电场调制。
</div>

### 2. 液晶光学混沌系统设计

#### 仪器设计
实验装置如图 4 所示。激光经过偏振片 $$ P_1 $$ 转变为线偏振光，再经过偏振片 $$ P_2 $$ 改变入射光强 $$ I_{\text{in}} $$，信号由光传感器采集。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/4.png" title="实验装置光路图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 4：实验系统光路结构。
</div>

#### 反馈电压设计
定义光强透过率 $$ T_{\lambda} $$ 为：
$$ T_{\lambda} = \frac{I_{\text{out}}}{I_{\text{in}}} = f(V) $$

设计反馈电压迭代公式：
$$ V_{n+1} = C_{1} I_{\text{out}} + C_{2} V_{n} $$

#### 理论建模
假设电场使液晶分子轴方向偏转角度 $$ \theta $$，随电压 $$ V $$ 变化关系为：
$$ \theta = \begin{cases} 0 & V \leq V_{th} \\ \frac{\pi}{2} - 2 \tanh\left[\exp\left(\frac{V_{th}-V}{V_{0}}\right)\right] & V > V_{th} \end{cases} $$

最后形成了完整的混沌体系模型：
$$ \begin{cases} I_{\text{out}} = I_{\text{in}} \left|\begin{array}{c} \cos \beta \cos \alpha + \sin \beta \sin \alpha e^{-i \delta} \\ -\sin \beta \cos \alpha + 2 \sin \alpha \cos \beta e^{-i \delta} \end{array}\right|^{2} \\ \delta = \frac{2 \pi \Delta n}{\lambda} \\ \Delta n(T) = \Delta n_{0}\left(1-\frac{T}{T_{c}}\right)^{\beta} \\ V_{n+1} = C_{1} I_{\text{out}} + C_{2} V_{n} \\ I_{\text{in}} = I_{0} \cos^{2} \omega \Delta t \end{cases} $$

## 实验结果

### 1. 计算机仿真
基于以上模型，我们分别仿真出了周期态和混沌态的液晶光学状态：

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/5.png" title="周期态计算机仿真结果" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 5：周期态仿真结果（含时序图、相图与频谱）。
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/6.png" title="混沌态计算机仿真结果" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 6：双吸引子混沌态仿真结果。
</div>

### 2. 液晶电光效应机理探究
液晶具有“光开关”特性。阈值电压 $$ V_{th} $$ 定义为透过率为 $$ 90\% $$ 时的驱动电压。实验中观察到在方波电压作用下，输出光强存在明显的振荡和滞后性（图 7）。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/7.png" title="时间响应曲线" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 7：液晶对电压信号的时间响应。
</div>

在直流电压驱动下，不同温度下的输出光强形态如图 8 所示。可以发现，在 $$ 25^\circ\mathrm{C} $$ 和 $$ 48^\circ\mathrm{C} $$ 下，液晶的回弹速率和振荡幅度表现出明显差异。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/8.png" title="直流驱动下的电光曲线" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 8：不同电压间隔与温度下的光强振荡。
</div>

### 3. 光学混沌状态分析

#### 双周期态
当光强大小在非振荡区间时，系统表现为双周期态。其特征是两个相邻的峰高度不一致（图 13）。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/13.png" title="双周期态结果" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 13：双周期态相图与频谱。
</div>

#### 混沌态
当反馈电压与输入光强在振荡区间耦合时，系统进入混沌态。相图中运动轨迹局部不稳定，但全局拘束在双稳态区域内（图 15）。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/chaos/15.png" title="混沌态实验结果" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 15：混沌态的时序图与吸引子相图。
</div>

## 讨论与未来展望

本文通过构建一套混合型电光双稳系统，测得了 $$ 40^\circ $$ 扭曲向列相液晶盒的电光效应和时间响应。我们发现，温度、电压频率和反馈系数是控制系统在周期态与混沌态之间转换的关键因子。

未来，我们期望基于该理论模型设计出一套线上仿真平台，以忽略外界环境干扰，降低实验成本，使非线性光学的研究更具普适性。

## 参考文献

[1] F. T. Arecchi, et al. *Atomic coherent states in quantum optics*. Phys. Rev. A, 1972.  
[2] R. Bonifacio and L. A. Lugiato. *Cooperative effects and bistability*. Opt. Comm., 1976.  
[3] M. J. Feigenbaum. *Quantitative universality for a class of nonlinear transformations*. J. Stat. Phys., 1978.  
[4] H. Gibbs, et al. *Differential gain and bistability using Fabry-Perot interferometer*. Phys. Rev. Lett., 1976.  
[5] K. Ikeda. *Multiple-valued stationary state and its instability*. Optics Comm., 1979.  
[6] A. L. Lewis, et al. *Dynamics and chaos in an acousto-optic system*. J. Opt. Soc. Am. B, 1991.  
[7] 张洪钧. 《光学混沌》. 上海科学教育出版社, 1997.  
[8] J. P. Toomey, et al. *Secure communication using chaotic semiconductor lasers*. IEEE J. Quantum Electron., 2001.

## 专业团队

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0 mx-auto" style="max-width: 600px;">
        {% include figure.html path="assets/img/chaos/17.jpg" title="206 实验室团队合影" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
