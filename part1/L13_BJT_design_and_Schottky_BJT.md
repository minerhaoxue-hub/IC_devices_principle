# 核心概念

## Verticle BJT design

<img src="./figures/L13_1.jpg" width=50% style="float:left;margin-left:10px;"/>

<div style="clear:both;"></div>

针对工艺的细节改进如下：

1. 为了让基极的输入阻抗没有那么大，通常使得base整体的水平长度减小，来减少电阻

2. n和n+区的距离要综合考虑两方面影响：第一点是反向偏压较大时n里面的耗尽区可能会延申到n+区，导致延申长度小，电场高，容易击穿，所以要做宽；第二点是做宽了之后的电阻会比较大。

3. base的掺杂浓度比较低那么 $\gamma$ 就会比较小，如果太高就会导致Early电阻增加（基区掺杂增加 $V_A$ 增加，而集电极掺杂增加 $V_A$ 减少）。

## Lateral BJT design

<img src="./figures/L13_2.jpg" width =50%  style="float:left; margin-left:10px"/>

<div style="clear:both;"></div>

水平BJT由于电子可能在基区漫游的距离过长，导致复合率上升。而为了避免这一现象，我们增加集电极的纵深距离，缩短发射极的水平宽度（保证右侧的扩散距离比较短,以及向衬底的竖直注入）并在另一侧加上集电极。

## Transient of turn-on and turn-off

<table>
    <tr>
    <td><img src="./figures/L13_4.jpg"></td>
    <td><img src="./figures/L13_3.jpg"></td>
    </tr>
</table>

在下面的讨论中，我们认为

1. 饱和区和正向放大区的界线在 $V_{BC}=0\leftrightarrow V_{CE}=V_{on}$ 时，因为此时BC结两端载流子浓度一样。

2. 由于 $I_{BE}=I_S(e^{\frac{qV_{BE}}{kT}}-1)$ 当超过了一定电压后电流随便变电压几乎不变，我们认为当 $V_{BE}$ 达到了 $V_{on}$ 之后不会上升，稳定在 $V_{on}$

理解暂态过程的关键是**基区电荷 $Q_B$ 的暂态变化情况**

### Turn on

- $I_B$: 当我们给带电阻基极施加阶跃电压时，首先因为基极和发射极之间没有电压，所以流向基极的电流就是施加的电压除以电阻。在正向导通了之后，由于 $V_{BE}=V_{on}$ 所以电流趋于稳定值。

- $Q_B$: charge at base, 代表了在基区 $Q_B$ 数量的电子电荷和空穴电荷（浓度梯度形成）。由于BE结有较多的电子可以输运，而空穴要积累相同的量，所以决定 $Q_B$ 大小的因素为空穴电流，即 $I_B$。   
    
    $Q_B$ 的填充状态是：先填满 $BE$ 结，再填满 $BC$ 结。而刚好填充了一半时，达到了正向放大和饱和区的分界线。

- $V_{out}$：正向放大区和饱和区的分界点在于 $V_{out}=V_{on}$. 把握这个即可。

### Turn off

利用相同的方法思考 $Q_B$ 的变化图像。

- $I_B$: 在一开始时 $V_B$ 保持 $V_{on}$ 不变（BE结维持电压的电荷不变）。所以电流不变。当进入正向放大区之后电流逐渐衰减到0.（因为电压减小）

- $V_{out}$ 开始由零开始缓慢增加到 $V_{on}$ (时间为 $\frac{Q_B}{2I_B} $ ) 

由于 $I_{Boff} <<I_{Bon}$ 所以限制BJT转换时间的主要因素是关闭状态

## Schottky BJT

<img src="./figures/L13_5.jpg" width=50% style="float:left;margin-left=10px">

<div style="clear:both"></div>

利用Schottky二极管的开启电压较小的特点，当输入电压建立平衡之后，$V_{BC}=0.3 \ V$ (对比原来是 $0.7V$) 这样从饱和区过渡到正向放大区的放电量（原来是一半的 $Q_B$ ）就能大幅减少，从而减少关闭所需时间。

实际工程中使用Au,和p构成欧姆接触，n构成Schottky接触实现。