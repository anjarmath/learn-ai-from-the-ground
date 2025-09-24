# 5.1 Differentiation of Univariate Functions
![[Pasted image 20250816131854.png]]
$$
\frac{\delta y}{\delta x}=\frac{f(x+\delta x)-f(x)}{\delta x}$$
Menyatakan kemiringan garis secan dari dua titik, yakni titik-titik antara $x_{0}$ dan $x_{0}+\delta x$.

> [!NOTE] Turunan (Derivative)
> Untuk $h>0$ turunan dari $f$ di $x$ terdefinisi sebagai limit
> $$
\frac{df}{dx}=f'(x):=\lim_{ h \to 0 }\frac{f(x+h)-f(x)}{h} $$
di mana $h=\delta x$,dan secan pada gambar menjadi tangen.

- Untuk suatu polinomial $f(x)=ax^n$ maka turunannya adalah $f'(x)=anx^{n-1}$
## 5.1.1 Deret Taylor
> [!NOTE] Polinomial Taylor
> Polinomial derajat $n$ dari $f:\mathbb{R}\to \mathbb{R}$ di $x_{0}$ didefinisikan sebagai
> $$
T_{n}(x):=\sum_{k=0}^n\frac{f^(k)(x_{0})}{k!}(x-x_{0})^k$$
di mana $f^(k)(x_{0})$ adalah turunan ke-$k$ dari $f$ di $x_{0}$ dan $\frac{f^(k)(x_{0})}{k!}$ adalah koefisien polinomial.

> [!NOTE] Deret Taylor
> Untuk suatu fungsi $f\in \mathcal{C}^\infty,\ f:\mathbb{R}\to \mathbb{R}$, baris taylor dari $f$ di $x_{0}$ didefinisikan sebagai:
> $$
T_{\infty}(x)=\sum_{k=0}^\infty\frac{f^(k)(x_{0})}{k!}(x-x_{0})^k$$
Untuk $x_{0}=0$ kita mendapatkan *deret mclaurin*. Jika $f(x)=T_{\infty}(x)$ maka $f$ disebut *analitik*.
## 5.1.2 Aturan Diferensiasi
- Product rule: $(f(x)g(x))'=f(x)'g(x)+g'(x)f(x)$
- Quotient rule: $\left( \frac{f(x)}{g(x)} \right)'=\frac{f'(x)g(x)-g'(x)f(x)}{g(x)^2}$
- Sum rule: $(f(x)+g(x))'=f'(x)+g'(x)$
- Chain rule: $(g(f(x)))'=(g\ \circ \ f)'(x)=g'(f(x))f'(x)$

# 5.2 Partial Differentiation and Gradients

> [!NOTE] Partial Differentiation
> Untuk suatu fungsi $f:\mathbb{R}^n\to \mathbb{R}, x\to f(x), x \in \mathbb{R}^n$ dari $n$ variabel $x_{1},\dots,x_{n}$, diferensiasi parsial didefinisikan sebagai:
> $$
\begin{align}
\frac{\delta f}{\delta x_{1}} & =\lim_{ h \to 0 } \frac{f(x_{1}+h,x_{2},\dots,x_{n})-f(x)}{h} \\
 & \vdots \\
\frac{\delta f}{\delta x_{n}} & =\lim_{ h \to 0 } \frac{f(x_{1},\dots,x_{n-1},x_{n}+h)-f(x)}{h} \end{align}$$
dan koleksikan dalam vektor baris $$ J= \nabla_{x}f=grad\ f=\frac{df}{dx}=\begin{bmatrix}
\frac{\delta f(x)}{\delta x_{1}} & \frac{\delta f(x)}{\delta x_{2}} & \dots & \frac{\delta f(x)}{\delta x_{n}} \end{bmatrix} \in \mathbb{R}^{1\times n}$$
Vektor baris ini disebut *gradien* dari $f$ atau ***Jacobian***.

### Contoh 1
Untuk $f(x,y)=x^2y+xy^3 \in \mathbb{R}$, turunan parsialnya adalah:
$$
\begin{align}
\frac{\delta f}{\delta x} & = 2xy+y^3 \\
\frac{\delta f}{\delta y} & =x^2+3xy^2
\end{align}
$$
dan gradiennya adalah $J=\begin{bmatrix}2xy+y^3 & x^2+3xy^2\end{bmatrix}$
## 5.2.1 Partial Differentiation Rules
- Product Rule: $\frac{\delta}{\delta x}(f(x)g(x))=\frac{\delta f}{\delta x}g(x)+f(x)\frac{\delta g}{\delta x}$
- Sum Rule: $\frac{\delta}{\delta x}(f(x)+g(x))=\frac{\delta f}{\delta x}+\frac{\delta g}{\delta x}$
- Chain Rule: $\frac{\delta}{\delta x}(g\ \circ\ f)(x)=\frac{\delta}{\delta x}(g(f(x)))=\frac{\delta g}{\delta f} \frac{\delta f}{\delta x}$
### Contoh 2
Ambil $f(x_{1},x_{2})=x_{1}^2+2x_{2}$ , di mana $x_{1}=\sin t$ dan $x_{2}=\cos t$, maka
$$
\begin{align}
\frac{\delta f}{\delta t} & = \frac{\delta f}{\delta x_{1}} \frac{\delta x_{1}}{\delta t}+\frac{\delta f}{\delta x_{2}} \frac{\delta x_{2}}{\delta t} \\
 & =2\sin t \frac{\delta \sin t}{\delta t} +2 \delta \cos \frac{t}{\delta t} \\
 & = 2\sin t\cos t-2\sin t \\
 & = 2\sin t(\cos t-1)
\end{align}
$$
adalah turunan $t$ dari $f$.
# 5.3 Gradient of Vector-Valued Functions
Misal kita punya fungsi-fungsi $f_{1},f_{2},\dots,f_{m}$ di mana masing-masing fungsi menerima variabel $x=\begin{bmatrix}x_{1} & \dots & x_{n}\end{bmatrix}^T$. Kita bisa susun fungsi-fungsi tersebut menjadi:
$$
f=\begin{bmatrix}
f_{1}(x) \\
f_{2}(x) \\
\vdots \\
f_{m}(x)
\end{bmatrix}_{1\times m} \in \mathbb{R}^m
$$
yang mana bentuk $f$ ini disebut **vector-valued functions**. Gradien dari $f$ dijabarkan sebagai:
$$
\frac{df}{dx}=\begin{bmatrix}
\frac{\delta f_{1}}{\delta x_{1}} & \frac{\delta f_{1}}{\delta x_{2}} & \dots  & \frac{\delta f_{1}}{\delta x_{n}} \\
\frac{\delta f_{2}}{\delta x_{1}} & \frac{\delta f_{2}}{\delta x_{2}} & \dots  & \frac{\delta f_{2}}{\delta x_{n}} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\delta f_{m}}{\delta x_{1}} & \frac{\delta f_{m}}{\delta x_{2}} & \dots  & \frac{\delta f_{m}}{\delta x_{n}}
\end{bmatrix}_{m\times n}, J(i,j)=\frac{\delta f_{i}}{\delta x_{j}}
$$
### Contoh 3
Diberikan
$$
f(x)=Ax,\ f(x)\in \mathbb{R}^M,\ A\in \mathbb{R}^{M\times N},\ x \in \mathbb{R}^N
$$
Untuk menghitung $df/dx$ pertama kita tentukan dimensi turunannya yakni $M\times N$. Turunan parsial $f$ untuk setiap $x_{j}$ adalah:
$$
f_{i}(x)=\sum_{j=1}^na_{ij}x_{j}\implies \frac{\delta f_{i}}{\delta x_{j}}=A_{ij}
$$
$\therefore$ $df/dx$ tidak lain adalah $A$.
### Contoh 4 (Gradient of Least-Square Loss in Linear Model)
Untuk suatu model linear
$$
y=\Phi\theta \tag{1}
$$
di mana $\theta \in \mathbb{R}^D$ adalah suatu parameter vektor, $\Phi \in \mathbb{R}^{N\times D}$ sebuah input features, dan $y\in \mathbb{R}^N$ adalah observasi terkait. kita definisikan fungsi:
$$
\begin{align}
L(e)=\lVert e \rVert^2 \tag{2} \\
e(\theta)=y-\Phi\theta \tag{3} 
\end{align}
$$
fungsi $L$ disebut **Least-Square Loss**. Kita akan mencari $\frac{dL}{d\theta}$.
Pertama, kita cari dimensi turunannya, karena fungsi $L:R^D\mapsto R$ maka $\frac{dL}{d\theta} \in \mathbb{R}^{1\times D}$.
Dengan menerapkan chain rule didapat:
$$
\frac{dL}{d\theta}=\frac{dL}{de} \frac{de}{d\theta}
$$
dengan elemen ke-$d$ adalah:
$$
\frac{dL}{d\theta}[1,d]=\sum _{n=1}^N \frac{dL}{de}[n] \frac{de}{d\theta}[n,d]
$$
lalu
$$
\begin{align}
\lVert e \rVert=e^Te \implies \frac{dL}{de} & =2e^T, \text{dan} \\
\frac{de}{d\theta} & = -\Phi \\
\end{align}
$$
$\therefore \frac{dL}{d\theta}=-2e^T\Phi=-2(\underbrace{ y^T-\Phi^T\theta^T }_{ 1\times N })\underbrace{ \Phi }_{ N\times D } \in \mathbb{R}^{1\times D}$
# 5.4 Gradients of Matrices
Misalkan kita punya matriks $A\in \mathbb{R}^{m\times n},\ B\in \mathbb{R}^{p\times q}$, jika kita hendak menghitung $\delta A/\delta B$ maka setiap entri $A_{ij}$ diturunkan terhadap entri $B_{kl}$ sehingga kita dapatkan **Jacobian tensor 4D**:
$$
J_{ijkl}=\frac{\delta A_{ij}}{\delta B_{kl}},\ J\in \mathbb{R}^{m\times n\times p\times q}
$$
> fungsi yang memetakan objek $d$-dimensional ke objek $e$-dimensional, Jacobian-nya punya rank $d+e$.

Untuk mempermudah, perhatikan bahwa $\mathbb{R}^{m\times n}$ **isomorfik** dengan $\mathbb{R}^{mn}$.
Sehingga kita bisa reshape matriks menjadi matriks vektor dengan panjang $mn$, sebagai contoh:
$$
A=\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{bmatrix}_{2\times2} \to vec(A)=\begin{bmatrix}
a_{11} \\
a_{21} \\
a_{12} \\
a_{22}
\end{bmatrix}_{1\times4}
$$
maka Jacobian bisa ditulis sebagai:
$$
J=\frac{\delta vec(A)}{\delta vec(B)^T}\in \mathbb{R}^{mn\times pq}
$$
# 5.5 Useful Identities for Computing Gradients
![[Pasted image 20250825110325.png]]
# 5.6 Backpropagation and Automatic Differentiation
## 5.6.1 Gradients in Deep Network
Dalam jaringan syaraf dengan banyak lapisan $K$ sehingga $i=1,2,\dots,K$, kita punya fungsi
$$
f(x_{i-1})=\sigma(A_{i-1}x_{i-1}+b_{i-1})
$$
pada layer ke-$i$, dengan $x_{i-1}$ adalah output dari layer sebelumnya. Sebagai contoh jika kita punya input $x$ diuraikan berikut:
$$
\begin{align}
f_{0} & =x \\
f_{i} & = \sigma_{i}(A_{i-1}f_{i-1}+b_{i-1}),\ i=1,2,\dots,K
\end{align}
$$
di mana $\sigma$ adalah fungsi aktivasi, matriks $A$ adalah beban(*weight*), dan $b$ adalah bias. Dalam konteks optimasi, kita  ingin mencari $A_{j},B_{j},\ j=0,1,\dots,K$ sehingga *squared-loss*:
$$
L(\theta)=\lVert y-f_{K}(\theta,x) \rVert^2 
$$
adalah minimal di mana $\theta=\left\{ A_{0},B_{0},\dots,A_{K-1},B_{k-1} \right\}$.
Untuk mendapatkan gradien-gradien terhadap himpunan parameter $\theta$, kita membutuhkan turunan parsial dari $L$ terhadap parameter $\theta_{j}=\left\{ A_{j},b_{j} \right\}$ untuk setiap layer $j=0,1,\dots,K-1$ menggunakan chain rule.
## 5.6.2 Automatic Differentiation
Automatic differentiation adalah sebuah metode diferensiasi dengan:
- Memecah fungsi jadi _graph of operations_.
- Gunakan **chain rule** secara lokal di setiap node.
- Hasilkan gradien yang tepat (presisi floating point), dengan biaya seefisien evaluasi fungsi.
Jika kita punya alur data dari input $x$ ke output $y$ dengan melewati variabel $a$ dan $b$ maka untuk mendapatkan turunan $\frac{dy}{dx}$ kita memakai *chain rule* sebagai berikut:
$$
\frac{dy}{dx}=\frac{dy}{db} \frac{db}{da} \frac{da}{dx}
$$
Karena perkalian matriks bersifat asosiatif, maka pesamaan bisa diselesaikan dengan memilih dua cara:
$$
\begin{align}
\frac{dy}{dx}=\left( \frac{dy}{db} \frac{db}{da} \right)  \frac{da}{dx} \tag{1} \\
\frac{dy}{dx}=\frac{dy}{db} \left( \frac{db}{da} \frac{da}{dx} \right) \tag{2} 
\end{align}
$$
persamaan $(1)$ disebut *reverse mode* sebab gradien bergerak terbalik, sedangkan persamaan $(2)$ disebut *forward mode* sebab gradien bergerak bersama data dari kiri ke kanan dalam *graph of operation*.
Dalam konteks deep network, di mana dimensi input sering kali jauh lebih besar dari pada dimensi label, *reverse mode* secara komputasi jauh lebih efisien sehingga akan dipakai, *reverse mode* inilah yang disebut **back propagation***.
# 5.7 Higher-Order Derivatives
> [!NOTE] Hesian Matrix
> Hesian yang dinotasikan sebagai $\nabla_{x,y}^2f(x,y)$ adalah matriks yang menghimpun turunan kedua dari sebuah fungsi. Hesian menunjukan kelengkungan lokal dari sebuah fungsi di $(x,y)$.

dalam konteks stabilitas training, **Hesian** memberikan informasi apakah titik yang ditemukan gradient descent itu minimum, maksimum, atau saddle.
### Contoh 5
Untuk $f(x)=x^2+y^2$ maka:
$$
\begin{align}
J & = \begin{bmatrix}
2x & 2y
\end{bmatrix} \\
H & =\begin{bmatrix}
2 & 0 \\
0 & 2
\end{bmatrix}
\end{align}
$$
- Jika determinan dari Hesian adalah positif maka titik tersebut adalah maksimum atau minimum
- Jika $h_{11}$ adalah positif maka dia adalah titik minimum, sedangkan jika dia negatif, dia adalah titik maksimum
dari $f(x)$ didapati visualisasi sebagai berikut:
![[Pasted image 20250825141924.png]]
# 5.8 Linearization and Multivariate Taylor Series

## 5.8.1 Linearization dalam Satu Variabel
Untuk fungsi $f: \mathbb{R} \to \mathbb{R}$, aproksimasi linear di sekitar titik $x_0 \in \mathbb{R}$ adalah:
$$f(x) \approx f(x_0) + f'(x_0)(x - x_0)$$
dengan $x \in \mathbb{R}$ variabel dan $x_{0} \in \mathbb{R}$ titik pusat aproksimasi, yaitu titik di mana kita “mendekatkan” fungsi.
## 5.8.2 Linearization dalam Banyak Variabel
Sekarang untuk fungsi $f: \mathbb{R}^n \to \mathbb{R}$, aproksimasi linear di sekitar $\mathbf{x}_0 \in \mathbb{R}^n$ adalah:
$$
f(\mathbf{x}) \approx f(\mathbf{x}_0) + \nabla f(\mathbf{x}_0)^\top (\mathbf{x} - \mathbf{x}_0)
$$
## 5.8.3 Multivariate Taylor Expansion (sampai orde 2)
Untuk fungsi skalar $f: \mathbb{R}^n \to \mathbb{R}$, ekspansi Taylor sampai orde dua di sekitar $\mathbf{x}_0$ adalah:
$$
f(\mathbf{x}) \approx f(\mathbf{x}_0) + \nabla f(\mathbf{x}_0)^\top (\mathbf{x} - \mathbf{x}_0) + \tfrac{1}{2} (\mathbf{x} - \mathbf{x}_0)^\top H(\mathbf{x}_0) (\mathbf{x} - \mathbf{x}_0)
$$
### Contoh 6
Ambil $f(x,y) = x^2 + xy + y^2$
- Input $\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}$, lalu ambil suatu $\mathbf{x}_0 = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$.
- $f(\mathbf{x}_0) = 0$.
- Gradien:
$$
\nabla f(x,y) = \begin{bmatrix} 2x + y \\ x + 2y \end{bmatrix}, \quad \nabla f(\mathbf{x}_0) = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
$$
- Hessian:
$$
H = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}
$$

Maka Taylor expansion di sekitar $(0,0)$:
$$
f(x,y) \approx 0 + 0 + \tfrac{1}{2} \begin{bmatrix} x & y \end{bmatrix} \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = x^2 + xy + y^2
$$
