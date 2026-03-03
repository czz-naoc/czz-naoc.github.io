---
layout: page
title: 凌日巨行星透射光谱法仿真
description: 模拟凌日过程中恒星光线穿过行星的大气层，使我们能够分析吸收特征并推断大气成分和结构。
img: assets/img/trans1.png
importance: 1
category: 学习内容
math: true
giscus_comments: true
---

> 在系外行星（特别是巨行星）的研究中，系外行星大气成分和结构对了解其形成与演化过程尤为重要。透射光谱法是观测系外行星大气的主要手段之一，已被广泛应用于系外行星的研究中。透射光谱的原理是：当行星经过它的主恒星前方（即“凌日”现象）时，部分恒星光会穿过行星的高层大气（图 1）。大气中的分子，如 $$ \mathrm{H_2O, CO_2, CH_4, NH_3} $$ 等，会选择性地吸收特定波长的光，形成在不同波长上光强减弱的现象，即吸收线。通过观测这些吸收线的波长和强度，可以推断出行星大气中存在的分子类型及其相对丰度。

## 背景

透射光谱法的关键在于对光学厚度 $$ \tau_{\nu} $$ 的测量。光学厚度反映了光线穿过行星大气时被吸收的程度，它与大气中的气体组成、温度、压力和大气层的几何结构密切相关。$$ \alpha_{\nu} $$ 为吸收系数。它表示特定频率 $$ \nu $$ 下介质对光的吸收能力。吸收系数与光学厚度密切相关，光学厚度是吸收系数沿着光的传播路径长度 $$ s $$ 进行积分后得到的一个无量纲量：

$$ \tau_{\nu}=\int_{0}^{s} \alpha_{\nu} d s \quad (1) $$

透射光谱不仅可以揭示大气中的化学成分，还可以提供行星的大气温度、重力、金属丰度等物理参数。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans1.png" title="透射光谱法原理图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 1：透射光谱法原理图，引自谭先瑜教授课程课件。
</div>

光线在大气传播路径上随着距离 $$ s $$ 的变化而减弱的过程如下：

$$ \frac{d I_{\nu}}{d s}=-\alpha_{\nu} I_{\nu} \quad (2) $$

其中 $$ I_{v} $$ 是指在频率 $$ \nu $$ 下的辐射光强。吸收系数 $$ \alpha_{\nu} $$ 的定义如下：

$$ \alpha_{\nu}=\epsilon \rho \kappa_{\nu} \quad (3) $$

其中 $$ \epsilon $$ 是比例因子，$$ \rho $$ 为大气密度，$$ \kappa_{\nu} $$ 代表吸收不透明度。行星大气垂直结构用大气标高 $$ H $$ 表示：

$$ H=\frac{k T}{m g} \quad (4) $$

在定量计算行星透射光谱信号强度时近似为：

$$ R_{0}-R_{\mathrm{ref}} \approx H \ln \left(\frac{\rho_{\mathrm{ref}} \epsilon \kappa_{\nu}}{2 \pi R_{0} H}\right) \quad (5) $$

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans2.png" title="透射光谱示意图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 2：透射光谱示意图，引自谭先瑜教授课程课件。
</div>

当分析透射光谱中 $$ \mathrm{H_2O} $$ 和 $$ \mathrm{CO_2} $$ 的吸收线时，可以基于公式 (5) 计算行星大气中的碳氧比 (C/O):

$$ R_{\mathrm{H_2O}} - R_{\mathrm{CO_2}} \approx H \ln \left( \frac{\epsilon_{\mathrm{H_2O}}}{\epsilon_{\mathrm{CO_2}}} \frac{\kappa_{\mathrm{H_2O}}}{\kappa_{\mathrm{CO_2}}} \right) \quad (6) $$

利用透射光谱中雷利散射的斜率提供的行星中氢和氦等轻元素的比例信息，可以确定行星的大气金属丰度：

$$ R(\lambda)-R_{\mathrm{ref}} \propto-4 H \ln \lambda \quad (7) $$

## 方法

本课题通过模拟巨行星的透射光谱，探索行星大气的各种物理与化学特性。项目使用 **PICASO** 大气辐射传输模型进行仿真模拟。该模型能够生成自洽的辐射-对流平衡温度-压力剖面，基于给定的恒星辐照度、行星内部发热量和大气金属丰度，计算出行星大气的结构。

我们主要通过选择性包含或排除某些气体分子来研究它们对光谱的特定波段影响。此外，我们通过改变不同的行星大气层温度和重力条件从而影响光谱中的吸收线强度和波长位移。

## 结果与讨论

行星大气模型的最初设定涵盖气体：$$ \mathrm{H_2, He, CH_4, H_2O, CO, NH_3, CO_2, K, Na, TiO, HCN} $$，初始温度设置为 1000K，模拟热木星类巨行星，结果如图 3 所示：

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans3.png" title="热木星原始大气设置" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 3：热木星原始大气设置。a. 气体混合比例; b. 初始温度; c. 全部气体元素存在的光谱图。
</div>

首先进行不同气体分子对应不同波段光谱特征峰的影响研究。结果如图 4 所示，$$ \mathrm{HCN, H_2, He, Na} $$ 对于整体光谱的影响几乎没有，而其他气体分子的影响均能有效识别。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans4.png" title="选择性去除气体分子研究" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 4：选择性去除某种气体分子研究不同元素对应特征峰波段。
</div>

在研究温度对于光谱特征的影响时，可以看出在 $$ 2\mu m $$ 至 $$ 3\mu m $$ 的位置上存在明显的吸收线强度改变和波长位移（图 5a）。温度升高会导致“热多普勒展宽”现象，吸收线变宽且强度增强。

重力对吸收线的强度影响体现在其决定了大气标高 $$ H $$。较高的重力会压缩大气层，使得大气层更薄、更密集，导致吸收信号特征变得更强（图 5b, 5c）。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans5.png" title="温度和重力影响" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 5：温度和重力影响下光谱线的变化。
</div>

云层和气溶胶能够显著改变光谱的形状。灰云（Gray Clouds）对所有波长的光线均匀散射，导致光谱平坦化。瑞利散射则主要影响短波长部分，使可见光波段呈现平滑背景。

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans6.png" title="云层与瑞利散射影响" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 6：云层、光深以及瑞利散射影响下的光谱线变化趋势。
</div>

> Thanks for Prof. Tan and all professors in TDLI.
