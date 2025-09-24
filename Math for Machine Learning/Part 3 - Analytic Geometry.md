![[Pasted image 20250729132222.png]]
# 3.1 Norms

> [!NOTE] Norms
 > Sebuah $Norms$ dalam ruang vektor $V$ adalah fungsi $$
\begin{align}
\lVert \cdot \rVert  : V \to \mathbb{R}, \\
x \mapsto \lVert x \rVert
\end{align} $$
Yang menetapkan panjang setiap vektor $x$ yakni $\lVert x \rVert\in \mathbb{R}$ sedemikian sehingga untuk semua $\lambda \in \mathbb{R}$ dan $x,y\in V$ terpenuhi:
> - *Absolutely homogeneus*, $\lVert \lambda x \rVert= \lvert \lambda \rvert\lVert x \rVert$
> - *Triangle inequality*, $\lVert x+y \rVert\leq \lVert x \rVert+\lVert y \rVert$
> - *Positive define*, $\lVert x \rVert\geq0$ dan $\lVert x \rVert=0\Leftrightarrow x=0$

Secara sederhana, **norm** adalah ukuran _“panjang”_ atau _“besar”_ dari sebuah vektor. Dalam geometri analitik, ini sama seperti panjang garis dari titik asal `(0,0,...,0)` ke titik akhir vektor.
Contoh norm yang populer adalah *manhattan norm* dan *euclidean norm*.
- Manhattan Norm:
$$
\lVert x \rVert:=\sum_{i=1}^n\lvert x_{i} \rvert 
$$
- Euclidean Norm:
$$
\lVert x \rVert=\sqrt{ \sum_{i=1}^nx_{i}^2 }=\sqrt{ x^Tx } 
$$
![[Pasted image 20250729135848.png]]
# 3.2 Inner Products
## 3.2.1 Dot Products
$$
x^Ty=\sum_{i=1}^nx_{i}y_{i}
$$
## 3.2.2 General Inner Products
> [!NOTE] Bilinear Mapping
> **Bilinear mapping** adalah fungsi $\Omega:V\times V\to \mathbb{R}$ yang:
> - Linear terhadap argumen pertama: $$
\Omega(\lambda x+\psi y,z)=\lambda\Omega(x,z)+\psi\Omega(y,z)$$
> - Linear terhadap argumen kedua:$$
\Omega(x,\lambda y+\psi z)=\lambda\Omega(x,y)+\psi \Omega(x,z)$$

Sederhananya, bilinear mapping adalah fungsi dari dua vektor yang menghasilkan skalar, dan bersifat linear terhadap masing-masing vektor.

> [!NOTE] Inner Products
> Inner Products adalah kasus bilinear mapping yang memenuhi:
> - *Simetris* $$
\forall x,y\in V:\Omega(x,y)=\Omega(y,x)$$
> - *Positif definit* $$
\forall x \in V:\Omega(x,x)\geq 0, \Omega(x,x)=0 \implies x=0$$
Dari sini, $\Omega(x,y)$ bisa ditulis sebagai $\left< x,y \right>$

Sederhananya: inner product mengukur seberapa sejajar dua vektor, hasilnya angka, dan bisa dipakai untuk menghitung sudut dan panjang.
## 3.2.3 Matrik Simetris, Positive Definit
### Contoh 1:
Ambil matrik:
$$
A_{1}=\begin{bmatrix}
9 & 6 \\
6 & 5
\end{bmatrix}\ \ A_{2}=\begin{bmatrix}
9 & 6 \\
6 & 3
\end{bmatrix}
$$
$A_{1}$ disebut positif definit karena di simetris($A_{1}=A_{1}^T$) dan
$$
\begin{align}
x^TA_{1}x & =\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}\begin{bmatrix}
9 & 6 \\
6 & 5
\end{bmatrix}\begin{bmatrix}
x_{1} & x_{2}
\end{bmatrix} \\
 & = 9x_{1}^2+12x_{1}x_{2}+5x_{2}^2 \\
 & = (3x_{1}+2x_{2})^2+x_{2}^2 > 0 
\end{align}
$$
Sebaliknya, $A_{2}$ simetris namun tidak positif definit sebab $x^TA_{2}x$ bisa $<0$ misalnya untuk $x=[2,-3]^T$.
# 3.3 Length & Distances
$$
\begin{align}
\lVert x \rVert &  = \sqrt{ \left< x,x \right>  }  \\
d(x,y) & :=\lVert x-y \rVert=\sqrt{ \left< x-y,x-y \right>  } 
\end{align}
$$
# 3.4 Angles & Orthogonality
Untuk $x,y\neq_{0}$
$$
\begin{align}
-1\leq \frac{\left< x,y \right>}{\lVert x \rVert\lVert y \rVert}\leq_{1} \\
\cos \mathcal{w}=\frac{\left< x,y \right>}{\lVert x \rVert\lVert y \rVert}
\end{align}
$$
### Contoh 3:
Untuk $x=[1\ 1]^T$ dan $y=[1\ 2]^T$ maka:
$$
\cos \mathcal{w}=\frac{\left< x,y \right>}{\lVert x \rVert\lVert y \rVert}=\frac{\left< x,y \right>}{\sqrt{ \left< x,x \right>\left< y,y \right>   }}=\frac{x^Ty}{\sqrt{ x^Txy^Ty }}=\frac{3}{\sqrt{ 10 }} 
$$

Dua vektor disebut *orthogonal* jika dan hanya jika $\left< x,y \right> =0$ dam ditulis $x\bot y$. Lebih lanjut, jika $\lVert x \rVert=\lVert y \rVert=1$ sehingga vektor adalah vektor unit maka disebut *orthonormal*.

Suatu matriks disebut *orthogonal* jika dan hanya jika kolom-kolomnya orthonormal sehingga,
$$
AA^T=I=A^TA \implies A^{-1}=A^T
$$
# 3.5 Orthonormal Basis
Ambil ruang vektor $V$ $n-$dimensi dengan basis $\{ b_{1},\dots,b_{n} \}$ dari $V$. Jika
$$
\begin{align}
\left< b_{i},b_{j} \right> & =0, \text{ untuk } x\neq y \tag{1}\\ 
\left< b_{i},b_{i} \right>  & =1  \tag{2}
\end{align}
$$
Untuk semua $i,j=1,\dots,n$. Basis disebut *orthogonal* jika $(1)$ terpenuhi, dan disebut *orthonormal* jika $(1)$ dan $(2)$ terpenuhi.
### Contoh 4:
Basis canonical/standar untuk ruang vektor Euclidean $R^n$ adalah basis *orthonormal* di mana inner product adalah dot product dari vektor. Misalnya pada $R^2$,
$$
b_{1}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}
1 \\
1
\end{bmatrix},\ b_{2}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}
1 \\
-1
\end{bmatrix}
$$
membentuk orthonormal basis sebab $b_{1}^Tb_{2}=0$ dan $\lVert b_{1} \rVert=\lVert b_{2} \rVert=1$.
# 3.6 Orthogonal Complement
*Orthogonal complement*, dari sebuah subruang $V \subseteq \mathbb{R}^n$ adalah himpunan semua vektor di $\mathbb{R}^n$ yang tegak lurus terhadap semua vektor di $V$.

Ditulis sebagai:
$V^\perp = \left\{ \mathbf{x} \in \mathbb{R}^n \,\middle|\, \langle \mathbf{x}, \mathbf{v} \rangle = 0 \text{ untuk semua } \mathbf{v} \in V \right\}$
# 3.7 Inner Products of Functions
Sama seperti kita bisa mengukur sudut dan panjang antara dua vektor, kita juga bisa mengukur sudut dan panjang antara dua fungsi. Artinya, fungsi bisa diperlakukan seperti vektor dalam ruang vektor.
Misal ada $2$ fungsi $f(x)$ dan $g(x)$ yang terdefinisi di $[a\ b]$, maka:
$$
\begin{align}
\left< f,g \right> & = \int_{a}^b f(x)g(x)\ dx  \\
\lVert f \rVert & = \sqrt{ \left< f,f \right>  } = \sqrt{ f(x)^2 } \\ 
\end{align}
$$
jika $\left< f,g \right> = 0$ maka dua fungsi disebut *orthogonal*.
