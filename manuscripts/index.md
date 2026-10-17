# 線形代数学入門

<!-- 線形代数学とは何かを説明する -->

## 数ベクトルと行列

<!--  ベクトルの起源と数学的に定式化された歴史について -->

### 数ベクトル

実数を $`n`$ 個並べた組を **数ベクトル** (*numerical vector*) といい,

```math
\bm{v} = (v_1,\ldots,v_n)
```

のように表し, 各 $`v_j`$ をベクトル $`\bm{v}`$ の $`j`$-成分という. 成分の数が等しいような 2 つのベクトル $`\bm{v} = (v_1,\ldots,v_n)`$, $`\bm{w} = (w_1,\ldots,w_n)`$ に対して, $`\bm{v}`$ と $`\bm{w}`$ の和 $`\bm{v}+\bm{w}`$ を次で定める.

```math
\bm{v}+\bm{w}\coloneqq(v_1+w_1,\ldots,v_n+w_n)
```

また, ベクトル $`\bm{v} = (v_1,\ldots,v_n)`$ の実数 $`c`$ に対して, $`\bm{v}`$ の $`c`$ 倍 $`c\bm{v}`$ を次で定める.

```math
c\bm{v}\coloneqq(cv_1,\ldots,cv_n)
```

特に, 成分がすべて $`0`$ からなるベクトルを **零ベクトル** (*zero vector*) といい、$`\bm{0}`$ と表す.

成分の数が等しいような 2 つのベクトル $`\bm{v} = (v_1,\ldots,v_n)`$, $`\bm{w} = (w_1,\ldots,w_n)`$ に対して, $`\bm{v}`$ と $`\bm{w}`$ の **内積** (*inner product*) $`\langle\bm{v},\bm{w}\rangle`$ を次で定める.

```math
\langle\bm{v},\bm{w}\rangle\coloneqq v_1w_1 + \cdots + v_nw_n
```

定義から, 以下の関係式が成り立つ.

```math
\langle\bm{u}+\bm{v},\bm{w}\rangle=\langle\bm{u},\bm{w}\rangle+\langle\bm{v},\bm{w}\rangle,\quad
\langle\bm{u},\bm{v}+\bm{w}\rangle=\langle\bm{u},\bm{v}\rangle+\langle\bm{u},\bm{w}\rangle,\\
\langle c\bm{v},\bm{w}\rangle=c\langle\bm{v},\bm{w}\rangle,\quad
\langle\bm{v},c\bm{w}\rangle=c\langle\bm{v},\bm{w}\rangle,\quad
\langle\bm{v},\bm{w}\rangle=\langle\bm{w},\bm{v}\rangle
```

特に, ベクトル $`\bm{v} = (v_1,\ldots,v_n)`$ の **ノルム** (*norm*) $`\|\bm{v}\|`$ を次で定める.

```math
\|\bm{v}\|\coloneqq\sqrt{\langle\bm{v},\bm{v}\rangle}={v_1}^2+\cdots+{v_n}^2
```

Theorem. **Cauchy–Schwarz の不等式**
:   $`|\langle\bm{v},\bm{w}\rangle|\le\|\bm{v}\|\|\bm{w}\|`$.
    特に, 等号成立条件は $`\bm{w}=c\bm{v}`$ なる実数 $`c`$ が存在するときに限る. 

Proof.
:   $`\bm{v}=\bm{0}`$ のときは両辺は $`0`$ となり明らかなため, 以後 $`\bm{v}\neq\bm{0}`$ とする.
    すべての実数 $`t`$ に対して $`\|t\bm{v}-\bm{w}\|\ge 0`$ であり, ノルムの定義から

    ```math
    \begin{align*}
    \|t\bm{v}-\bm{w}\|^2
    &{}=\langle t\bm{v}-\bm{w},t\bm{v}-\bm{w}\rangle\\
    &{}=t\langle\bm{v},t\bm{v}-\bm{w}\rangle-\langle\bm{w},t\bm{v}-\bm{w}\rangle\\
    &{}=t\left(t\langle\bm{v},\bm{v}\rangle-\langle\bm{v},\bm{w}\rangle\right)-\left(t\langle\bm{w},\bm{v}\rangle-\langle\bm{w},\bm{w}\rangle\right)\\
    &{}=t^2\|\bm{v}\|^2-2t\langle\bm{v},\bm{w}\rangle+\|\bm{w}\|^2\\
    &{}=\|\bm{v}\|^2\left(t-\frac{\langle\bm{v},\bm{w}\rangle}{\|\bm{v}\|^2}\right)^2+\frac{\|\bm{v}\|^2\|\bm{w}\|^2-\langle\bm{v},\bm{w}\rangle^2}{\|\bm{v}\|^2}
    \end{align*}
    ```

    となるため, $`\|\bm{v}\|^2\|\bm{w}\|^2-\langle\bm{v},\bm{w}\rangle^2\ge0`$ となり題意を得る.
    特に, $`|\langle\bm{v},\bm{w}\rangle|=\|\bm{v}\|\|\bm{w}\|`$ なら, 上記の式より

    ```math
    \|t\bm{v}-\bm{w}\|^2=\|\bm{v}\|^2\left(t-\frac{\langle\bm{v},\bm{w}\rangle}{\|\bm{v}\|^2}\right)^2
    ```

    を得る. ここで, $`t=\frac{\langle\bm{v},\bm{w}\rangle}{\|\bm{v}\|^2}`$ とすれば, $`\bm{w}=t\bm{v}`$ を得る.
    他方, ある実数 $`c`$ により $`\bm{w}=c\bm{v}`$ が成り立つと仮定すると, 

    ```math
    |\langle\bm{v},\bm{w}\rangle|
    =|\langle\bm{v},c\bm{v}\rangle|
    =|c\langle\bm{v},\bm{v}\rangle|
    =|c|\|\bm{v}\|^2
    ,\quad
    \|\bm{v}\|\|\bm{w}\|
    =\|\bm{v}\|\|c\bm{v}\|
    =|c|\|\bm{v}\|^2
    ```

    より, $`|\langle\bm{v},\bm{w}\rangle|=\|\bm{v}\|\|\bm{w}\|`$ となる.

Theorem. **三角不等式**
:   $`\|\bm{v}+\bm{w}\|\le\|\bm{v}\|+\|\bm{w}\|`$.
    特に, 等号成立条件は $`\bm{w}=c\bm{v}`$ なる実数 $`c`$ が存在するときに限る. 


## 線形空間と線形写像

## ベクトルの計量

