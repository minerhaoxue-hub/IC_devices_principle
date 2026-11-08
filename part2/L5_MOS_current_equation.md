# 核心概念

## Charge and velocity of channel carriers

对于NMOS,只有当中间的p区处于反型状态下，才能使得沟道两侧的多子电子进入。

又因为我们知道反型时，在单位水平长度上反型电子的总电荷量为 $WC_{ox}(V_G-V_T)$

对于位置 $X$ 处，使用 $V_T=V_{T0}+V_X+\gamma(\sqrt{2\phi_B+V_{XB}}-\sqrt{2\phi_B})$. 在忽略体效应时, 电荷量就是 $WC_{ox}(V_G-V_{T0}-V_X)$

当电子运动时，其速度和电场强度存在以下关系：

$$v=\mu E$$

所以 $$I_D=\mu E WC_{ox}(V_G-V_X-V_{T0})\tag{1}$$

## Linear region current equation

线性区，我们保证始终有反型电子，即

$$V_G-V_{T0}>V_X$$

由(1)式，$E=\frac{dV_X}{dx}$ 利用 $I_D$ 是常量的特性，两边同时积分（0到 $L$ 和 $V_S$ 到 $V_D$ ），得到电流表达式如下：

$$I_D=\frac{1}{2}\mu C_{ox}\frac{W}{L}(2(V_{GS}-V_{T0})V_{DS}-V_{DS}^2)$$

## Saturation region current equation

当施加的 $V_D$ 比较大时，一段区间内的 $V_G-V_{T0}<V_X$ 这时假设沟道长度 $L$ 的变化很小，那么无非是将上面式子的积分上界改成 $V_{G}-V_{T0}$, 得到的结果为

$$I_D=\frac{1}{2}\mu C_{ox}\frac{W}{L}(V_{GS}-V_{T0})^2$$

## Channel Length Modulation

如果考虑由于饱和临界点右侧带来的长度变化，由于右侧为耗尽区，就可以认为其电荷密度为 $qN_A$ 两端电势差为 $V_D-V_{dsat}$

$$\Delta L=\sqrt{\frac{2\varepsilon_{Si}(V_D-V_{dsat})}{qN_A}}$$

再利用根号的近似关系，得到考虑沟长调制效应的电流表达式

$$I_D=\frac{1}{2}\mu C_{ox}\frac{W}{L}(V_{GS}-V_{T0})^2(1+\lambda V_{DS})$$

## Limitation 

1. 我们认为耗尽区没有自由电荷，但是有电流
