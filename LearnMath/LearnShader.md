# **Learn Math**



### 泰勒展开式

$$
f(x)=f(x_0)+\frac{f^\prime(x_0)}{1!}(x-x_0)+\frac{f^{\prime\prime}(x_0)}{2!}(x-x_0)^2+\cdots+\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n+R_n(x) \\
R_n(x)=o((x-x_0)^n) \\
f(x)=\frac{f^\prime(0)}{1!}x+\frac{f^{\prime\prime}(0)}{2!}x^2+\cdots+\frac{f^{(n)}(0)}{n!}x^n+R_n(x) \\
R_n(x)=o(x^n)
$$



### Verlet算法

$$
ma=mx^{\prime\prime}(t)=F(x(t))=-\nabla{V(x(t))} \\
_{保守物理系统，牛顿第二定理}\\
V是势函数，保守系统，势函数只与坐标位置有关，即该函数为标量函数。对于一个物体，位移随时间变换的函数，记x(t)。\\
对于这个函数在t附近作泰勒展开得到t=t+\Delta{t} \\
x(t+\Delta{t})=x(t)+\frac{x^\prime(t)}{1!}\Delta{t}+\frac{x^{\prime\prime}(t)}{2!}\Delta{t}^2+\frac{x^{\prime\prime\prime}(t)}{3!}\Delta{t}^3+o(\Delta{t}^4) \\
x(t+\Delta{t})=x(t)+v(t)\Delta{t}+\frac{1}{2}a(t)\Delta{t}^2+\frac{1}{6}a^{\prime}(t)\Delta{t}^3+o(\Delta{t}^4) \\
对于t=t-\Delta{t}得到 \\
x(t-\Delta{t})=x(t)-\frac{x^\prime(t)}{1!}\Delta{t}+\frac{x^{\prime\prime}(t)}{2!}\Delta{t}^2-\frac{x^{\prime\prime\prime}(t)}{3!}\Delta{t}^3+o(\Delta{t}^4) \\
x(t-\Delta{t})=x(t)-v(t)\Delta{t}+\frac{1}{2}a(t)\Delta{t}^2-\frac{1}{6}a^{\prime}(t)\Delta{t}^3+o(\Delta{t}^4) \\
两式相加得到 \\
x(t+\Delta{t})+x(t-\Delta{t})=2x(t)+a(t)\Delta{t}^2+o(\Delta{t}^4) \\
x(t+\Delta{t})=2x(t)-x(t-\Delta{t})+a(t)\Delta{t}^2+o(\Delta{t}^4) \\
略去4阶小数 \\
x(t+\Delta{t})=2x(t)-x(t-\Delta{t})+a(t)\Delta{t}^2 \\
$$


























------

Md内联图片

- [datautl kaka]: 

