---
layout: page
title: 木卫二全球宜居性改造任务
description: Europa Global Habitability Altering Task (EGHAT)
img: assets/img/eghat1.png
importance: 4
category: 学习内容
math: true
---

> 很幸运能够遇到一群很有意思的朋友们。木卫二宜居性改造课题的完成很大一部分得益于谨睿的头脑风暴、文思泉涌，让我佩服不已。团队成员间的沟通很舒服，很久没有这么愉快的进行小组作业了，大家都非常nice，改造方案和项目汇报的成果在我心目中绝对是排No. 1。
> 
> “赤道氢弹爆破，形成赤道环带海洋；L1点气体采集站建设，输运管道铺设；运行三颗低轨人造太阳，加速融化冰层；仅保留一颗人造太阳，转移至20h高轨；氦氧大气环境改造，电解站建设运行；水下居住基地及配套设施建设；极地物种投放培养，第一产业完善…"以下是对谨睿的文稿进行复制编辑，如下。


我所分到的小组成员是截至当时，让我感受到最有契合感和和谐感的同龄人，对于我这种时有发疯的人员，他们为我带来的社交环境是前所未有的舒适的。我们甚至为夏令营分配的木卫二宜居改造项目，煞有其事地命名为 “EGHAT”，并且为此绘制了如图1的 Logo。

这个命名非常有趣，它可以被拆解为 “Egg + Hat” (鸡蛋帽子)，相当形象地描绘了最终期望改造的木卫二景象：海洋覆盖赤道环带，两极是厚实的冰盖，很像顶着俩鸡蛋壳。

EGHAT 全称为 Europa Global Habitability Altering Task (欧罗巴全球宜居性改造任务)。显然有些词汇是为了符合简称形式硬凑的，但似乎也说得过去。

<!-- 这里的 col-sm-6 表示占据 6/12 的宽度，即 50% -->
<div class="row justify-content-center">
    <div class="col-sm-6 mt-3 mt-md-0 mx-auto">
        {% include figure.html path="assets/img/eghat1.png" title="EGHAT Logo" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 1：EGHAT Logo。寓意为破冰的木卫二，冰帽像蛋壳一样覆盖两极。橙黄色线条表示氦氧混合大气，圆点表示在轨人造太阳。
</div>


实际上很多小组都只考虑了局部改造，但我往往有比较大的野心。在我提出的方案中，改造是全球性的——我们想把它改造成一个极地星球，固体表面覆盖着苔原生态系统，浅海则是冰海生态系统。我喜欢关心一些整体的、系统的、宏大的问题，尽管这在科学界容易被界定为“选题过大”。

木卫二（Europa）是一颗和月球规模接近的天然卫星，表面被冰层覆盖，其下存在巨大的全球性海洋（图 2）。如果更早确认这种具备全球性液态水海洋的天体，我相信会催生出更多的科幻电影。

<div class="row mt-3">
    <div class="col-sm-6 mt-3 mt-md-0 mx-auto">
        {% include figure.html path="assets/img/eghat2.png" title="木卫二冰壳剖面" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 2：木卫二冰圈和水圈剖面结构。海底热泉被认为是极有可能发现地外生命的位置。
</div>

为了产生环绕赤道的海洋，我们需要：破冰。考虑到成本，我们认为最简单的方式是氢弹爆破：在赤道环带冰层深处均匀布设氢弹并引爆。

暴露海洋后，我们需要对整个卫星升温。我们引入了在轨人造太阳：三颗人造太阳呈等边三角形分布于低轨，融化坚冰并释放气态碳酸，后期保留一颗转移至 20h 逆自转方向高轨，模拟地球处的天然太阳。

其动力源自可控核聚变。我们设想在木卫二与木星的 $$ L_1 $$ 点布设气体采集站，利用纳米材料管道从木星大气抽取燃料。经计算，维持极地生态系统均温所需氢气消耗量约 $$ 7160\ \mathrm{t/s} $$。这要求建设直径数十米、长达六十万公里的巨构管道。

我们设计了一种适宜人类呼吸的 “heliox” 氦氧混合大气（参考 Farahnaz et al. 2014）：
*   $$ 79.7\% $$ 的 $$ \mathrm{He} $$
*   $$ 20\% $$ 的 $$ \mathrm{O_2} $$
*   $$ 0.3\% $$ 的 $$ \mathrm{CO_2} $$ (供植物生长)

这种混合大气的平均分子量为 $$ \bar{M}_r = 14.314 $$。根据气体的玻尔兹曼分布关系：

$$ P=P_{0}e^{-\frac{M_{r}gh}{RT}} $$

若规定目标表面气压为 $$ 50.73\ \mathrm{kPa} $$，可求得大气厚度约为 $$ h_0 = 468\ \mathrm{km} $$。通过积分求得总大气质量 $$ M $$ 约为 $$ 1.044 \times 10^{13}\ \mathrm{t} $$：

$$ M=\int_{0}^{h_{0}} \rho_{0} e^{-\frac{\bar{M}_{r} g h}{R T}} 4 \pi(h+R)^{2} d h $$

依据热逃逸通量公式：

$$ F=\frac{n v e^{-K}(1+K)}{2 \sqrt{\pi K}}, \quad K=\frac{G M_p m}{kRT} $$

计算得出 $$ \mathrm{O_2} $$ 和 $$ \mathrm{CO_2} $$ 的热逃逸通量 $$ F \to 0 $$，而 $$ \mathrm{He} $$ 则需要通过木星采集站进行长期补充。

我们将改造后的设计均温定在 $$ 230\ \mathrm{K} $$。赤道约为 $$ 260\ \mathrm{K} $$，两极约为 $$ 200\ \mathrm{K} $$。由于 $$ \mathrm{CO_2} $$ 的沸点为 $$ 216.5\ \mathrm{K} $$，极地会出现“二氧化碳雪”。

<div class="row mt-3">
    <div class="col-sm-6 mt-3 mt-md-0 mx-auto">
        {% include figure.html path="assets/img/eghat3.png" title="木卫二气候概念图" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 3：改造后的地理-大气地貌概念图，形成冷温带海洋性气候和极地气候。
</div>

在生态方面，投放苔原植被和南极磷虾。人类居住区则设计为水下建筑，以利用厚重的水层屏蔽木星强大的辐射（图 4）。

<div class="row mt-3">
    <div class="col-sm-6 mt-3 mt-md-0 mx-auto">
        {% include figure.html path="assets/img/eghat4.png" title="居住基地方案" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    图 4：水下定居点设计，布局类似于地球南极科考站。
</div>

根据 Kashyap (2017)，地球相似指数 ESI 计算方式为：

$$ \mathrm{ESI} = \prod_{i=1}^{n} \left(1 - \left| \frac{x_i - x_0}{x_i + x_0} \right| \right)^{w_i} $$

我们引入自定义的 “模糊 ESI” (aESI) 进行评估：

$$ \mathrm{aESI} = \left( 1 - \left| \frac{230\ \mathrm{K} - T}{230\ \mathrm{K} + T} \right| \right)^{5.78} \left( 1 - \left| \frac{P_{rot} - 1\ \mathrm{yr}}{P_{rot} + 1\ \mathrm{yr}} \right| \right)^{0.7} $$

改造前，均温 $$ 102\ \mathrm{K} $$，$$ \mathrm{aESI} = 0.016 $$；改造后，均温 $$ 230\ \mathrm{K} $$，等效公转周期 $$ 1.78\ \mathrm{yr} $$，$$ \mathrm{aESI} = 0.86 $$。

这意味着改造后的木卫二将达到相当高的宜居水平。

### 参考文献

1. Hashemian SM, et al. *The use of heliox in critical care*. Int J Crit Illn Inj Sci. 2014.
2. Ding, S., et al. *A high-density and high-confinement tokamak plasma regime for fusion energy*. Nature. 2024.
3. Kashyap JM. *Quantitative indexing and Tardigrade analysis of exoplanets*. arXiv. 2017.
4. Mendez, A. *Standard Planetary Habitability (SPH) of Global Land Areas*. 2009.
