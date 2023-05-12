```
title: Markdown语法
description: Markdown语法介绍
date: 2023-05-12 20:30:00
updated: 2023-05-12 20:30:00
tags:
  - Markdown
  categories:
  - 技术栈
  swiper_index: 1 # 置顶权重
```



## 常用语法

> 字体

~~~markdown
<font face="STCAIYUN">我是华文彩云</font>
~~~

  <font face="STCAIYUN">我是华文彩云</font>

~~~markdown
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>
~~~

<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>



## 数学符合&公式

### 希腊字母表

|    符号    |   代码   |    符合    |   代码   |
| :--------: | :------: | :--------: | :------: |
|  $\alpha$  |  \alpha  |  $\Alpha$  |  \Alpha  |
|  $\beta$   |  \beta   |  $\Beta$   |  \Beta   |
|  $\gamma$  |  \gamma  |  $\Gamma$  |  \gamma  |
|  $\delta$  |  \delta  |  $\Delta$  |  \delta  |
| $\epsilon$ | \epsilon | $\Epsilon$ | \epsilon |
|  $\zeta$   |  \zeta   |  $\Zeta$   |  \Zeta   |
|   $\eta$   |   \eta   |   $\Eta$   |   \Eta   |
|  $\theta$  |  \theta  |  $\Theta$  |  \Theta  |
|  $\iota$   |  \iota   |  $\Iota$   |  \Iota   |
| $\lambda$  | \lambda  | $\Lambda$  | \Lambda  |
|   $\mu$    |   \mu    |   $\Mu$    |   \Mu    |
|   $\nu$    |   \nu    |   $\Nu$    |   \Nu    |
| $\omicron$ | \omicron | $\Omicron$ | \Omicron |
|   $\phi$   |   \phi   |   $\Phi$   |   \Phi   |
| $\upsilon$ | \upsilon | $\upsilon$ | \upsilon |
|  $\sigma$  |  \sigma  |  $\Sigma$  |  \Sigma  |
|   $\rho$   |   \rho   |   $\Rho$   |   \Rho   |
|   $\pi$    |   \pi    |   $\Pi$    |   \Pi    |



### 数学符号

|    描述    |           符号           |          代码          |
| :--------: | :----------------------: | :--------------------: |
|  行内公式  |            $$            |           $$           |
|    上标    |         $y=x^2$          |        y = x^2         |
|    下标    |          $O_2$           |          O_2           |
|    分式    |      $\frac {a}{b}$      |      \frac {a}{b}      |
|    根式    |       $\sqrt[a]b$        |       \sqrt[a]b        |
|   占位符   |         $\quad$          |         \quad          |
|    向量    |        $\vec{a}$         |        \vec{a}         |
| 无穷，极限 |     $\infty$，$\lim$     |      \infty，\lim      |
|   省略号   | $x_1^2 + \cdots + x_n^2$ | x_1^2 + \cdots + x_n^2 |

> 矩阵

~~~markdown
L_{n\times n} = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\ 
a_{21} & a_{22} & \cdots & a_{2n} \\ 
\vdots & \vdots &\ddots & \vdots\\
a_{n1} & a_{n2} & \cdots & a_{nn} \\ 
\end{bmatrix}
~~~

$L_{n\times n} = \begin{bmatrix}
a_{11} & a_{12} ewq & a_{1n} \\ 
a_{21} & a_{22} & \cdots & a_{2n} \\ 
\vdots & \vdots &\ddots & \vdots\\
a_{n1} & a_{n2} & \cdots & a_{nn} \\ 
\end{bmatrix}$

> 花括号

~~~markdown
$c(u)=\begin{cases} \sqrt\frac{1}{N}，u=0\\ \sqrt\frac{2}{N}， u\neq0\end{cases}$
~~~

$c(u)=\begin{cases} \sqrt\frac{1}{N}，u=0\\ \sqrt\frac{2}{N}， u\neq0\end{cases}$



### 数学符号补充

| $\geqslant$ | $\leqslant$ |
| :---------: | :---------: |
|  \leqslant  |  \leqslant  |