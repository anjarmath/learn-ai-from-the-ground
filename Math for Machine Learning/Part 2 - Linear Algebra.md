> [!NOTE] Vektor
> Secara umum vektor adalah sebuah objek yang bisa saling ditambahkan dan bisa dikalikan dengan sebuah skalar sedemikiran sehingga menghasilkan objek lain yang sejenis

Jenis-jenis vektor diantaranya:
1. Vektor geometri ($\overrightarrow{x}, \overrightarrow{y}$ ).
2. Polinomial juga merupakan vektor, karena$$\forall y_1,y_2 \in P^n: y_1+y_2=y_3\implies y_3 \in P^n$$
		dan$$\forall y \in P^n, \forall x \in \mathbb{R} \Rightarrow x(y) \in P^n$$
3. Signal audio juga merupakan vektor.
4. Element $\mathbb{R}^n$ (tupel dari $n$ bilangan Real) juga merupakan vektor.

> satu hal yang besar dalam matematika adalah konsep "closure". Apa himpunan vektor yang bisa dihasilkan dari himpunan-himpunan yang lebih kecil dan menjumlahkannya satu sama lain dan menskalanya?

![[Pasted image 20250725125601.png#inve]]

# 2.1. Sistem Persamaan Linear
#### Contoh 1:

$$ \begin{align}
x_1+x_2+x_3  & = 3 \tag{1} \\
x_{1}-x_{2}+2x_{3} & =2 \tag{2} \\
2x_{1}+3x_{3} & =5 \tag{3} \\
\end{align}
$$
Meskipun terdapat $3$ persamaan, sesuai dengan jumlah variabel dalam sistem persamaan ini, bisa dilihat bahwa jika kita menjumlahkan $(1)$ dengan $(2)$ akan menghasilkan $(3)$ sehingga persamaan $(3)$ sebenarnya bersifat *redundant*. Dengan kondisi ini, maka persamaan ini akan terdapat banyak kemungkinan solusi yang memenuhi persamaan. Kita akan menganggap salah satu variabel sebagai variabel bebas asalkan $2$ variabel yang lain tetaplah memenuhi persamaan.

Dari persamaan $(3)$ didapat:
$$
2x_{1}=5-3x_{3}\implies x_{1}=\frac{5}{2}-\frac{3}{2}x_{3} \tag{4}
$$
Lalu dengan mengurangi $(1)$ dengan $(2)$ didapat:
$$
2x_{2}=1+x_{3} \implies x_{2}=\frac{1}{2}+\frac{1}{2}x_{3} \tag{5}
$$
Lalu berdasarkan $(4)$ dan $(5)$, dengan menganggap bahwa $x_{3}=a \in \mathbb{R}$ adalah variabel bebas. Kita dapatkan solusi persamaan yaitu:
$$
(\frac{5}{2}-\frac{3}{2}a, \frac{1}{2}+\frac{1}{2}a,a), a \in \mathbb{R}
$$

> [!NOTE] 
> Pada umumnya, untuk sistem persamaan linear dalam ruang bilangan real, kita dapati: **tidak ada**, **satu**, atau **tak hingga** solusi.
# 2.2 Matriks
Definisi:
Dengan $m,n \in \mathbb{N}$ sebuah matriks $A$ bernilai $(m,n)$ adalah $m \cdot n$-tupel dari elemen $a_{i,j}, i=1,\dots, m, j=1, \dots, n$, yang diurutkan berdasarkan skema rectangular yang mengandung $m$ baris dan $n$ kolom:
$$
A= \begin{bmatrix}
a_{11} & a_{12} & \dots &  a_{1n} \\
a_{21} & a_{22} & \dots &  a_{2n} \\
\vdots & \vdots &  & \vdots \\
a_{m1} & a_{m2}  &  \dots & a_{mn}
\end{bmatrix}, \ a_{ij} \in \mathbb{R}
$$
$\mathbb{R}^{m \times n}$ adalah himpunan semua *real-valued* matriks $(m,n)$ 

### Invers Matrik
Untuk sebuah matriks $A \in \mathbb{R}^{n \times n}$. Asumsikan ada sebuah matriks $B \in \mathbb{R}^{n \times n}$ yang memenuhi $A \cdot B = I_{n} = B \cdot A$. $B$ dinamakan invers dari matriks $A$ dan dinotasikan sebagai $A^{-1}$.

Jika sebuah matriks memiliki invers, maka matriks tersebut disebut *regular/inversible/nonsingular*, sebaliknya disebut *singular/noninversible*.
### Transpose Matrik
Untuk sebuah matriks $A \in \mathbb{R}^{m \times n}$. Matriks $B \in \mathbb{R}^{n \times m}$ di mana $b_{ij} = a_{ji}$ adalah transpose dari matriks $A$, dan dinotasikan sebagai $A ^\top$ .

---
# 2.2 Solusi Sistem Persamaan Linear
#### Contoh 2:
Temukan solusi untuk
$$
\begin{bmatrix}
1 & 0 & 8 & -4 \\
0 & 1 & 2 & 12
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{bmatrix}
=
\begin{bmatrix}
42 \\
8
\end{bmatrix}
$$
Karena jumlah variabel lebih banyak dari jumlah persamaan yang diberikan, kita bisa harapkan sejumlah tak hingga solusi.

Jika kita asumsikan $x_{3}=0$ dan $x_{4}=0$, maka dari persamaan $1$ dan persamaan $2$ didapat $x_{1}=42$ dan $x_{2}=48$, sehingga solusinya adalah $\begin{bmatrix}42 & 8 & 0 & 0\end{bmatrix} ^\top$, kita sebut ini adalah solusi khusus.

Untuk mencari solusi umum, kita bisa menambahkan solusi khusus dengan persamaan apapun yang memenuhi $Ax=0$, sebab hasilnya akan tetap memenuhi solusi khusus.
$$
\begin{bmatrix}
1 & 0 & 8 & -4 \\
0 & 1 & 2 & 12
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0
\end{bmatrix}
$$
Anggap $x_{3}=s$ dan $x_{4}=t$ variabel bebas.
- Dari persamaan $1$ didapat:$$
x_{1}=-8s+4t$$
- Dari persamaan $2$ didapat: $$
x_{2}= -2s-12t$$
Sehingga semua solusi yang memenuhi $Ax=0$ adalah:
$$
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{bmatrix} = s\begin{bmatrix}
-8 \\
-2 \\
1 \\
0
\end{bmatrix}+t\begin{bmatrix}
4 \\
-12 \\
0 \\
1
\end{bmatrix}, \ s,t \in \mathbb{R}
$$
Oleh karena itu solusi umum persamaan awal menjadi:
$$
\left\{ x \in \mathbb{R}^4 : x= \begin{bmatrix}
42 \\
8 \\
0 \\
0
\end{bmatrix} + s\begin{bmatrix}
-8 \\
-2 \\
1 \\
0
\end{bmatrix}+t\begin{bmatrix}
4 \\
-12 \\
0 \\
1
\end{bmatrix}, \ s,t \in \mathbb{R}\right\}
$$
---
#### Contoh 3:
Untuk $a \in \mathbb{R}$, cari semua solusi yang memenuhi:
$$
\begin{align}
-2x_{1}+4x_{2}-2x_{3}-x_{4}+4x_{5} & =-3 \tag{1} \\
4x_{1}-8x_{2}+3x_{3}-3x_{4}+x_{5} & =2 \tag{2} \\
x_{1}-2x_{2}+x_{3}-x_{4}+x_{5} & =0 \tag{3} \\
x_{1}-2x_{2} -3x_{4} +4x_{5} &= a \tag{4}
\end{align}
$$
Dalam bentuk augmented matriks $Ax=b$ adalah sebagai berikut
$$
\left[ \begin{array}{rrrrr|r}
-2 & 4 & -2 & -1 & 4 & -3 \\
4 & -8 & 3 & -3 & 1 & 2 \\
1 & -2 & 1 & -1 & 1 & 0 \\
1 & -2 & 0 & -3 & 4 & a
\end{array} \right] 
$$

> [!NOTE] Lakukan Operasi Baris Elementer(OBE) sebagai berikut:
> - Menukar $2$ baris
> - Perkalian suatu baris dengan skalar $\lambda \in \mathbb{R}\setminus\{0\}$
> - Menambahkan dengan kelipatan baris lain

Lakukan OBE hingga mendapati `eselon-baris` sebagai berikut:
$$
\left[ \begin{array}{rrrrr|r}
1 & -2 & 1 & -1 & 1 & 0 \\
0 & 0 & 1 & -1 & 3 & -2 \\
0 & 0 & 0 & 1 & -2 & 1 \\
0 & 0 & 0 & 0 & 0 & a+1
\end{array} \right] 
$$
> [!NOTE] Bentuk Eselon-Baris (REF)
>Bentuk di atas disebut bentuk $Eselon-Baris\ (REF)$. Sebuah augmented matriks dikatakan Eselon-Baris jika memenuhi syarat-syarat berikut:
> - Setiap baris non-nol dimulai dari pivot $\neq0$,dan posisi pivot di sebelah kanan dari pivot baris sebelumnya.
> - Baris nol (jika ada) diletakkan di bawah.
> - Semua elemen di bawah pivot = 0.

Sehingga sistem bisa diselesaikan jika $a=-1$, asumsikan $x_{2}=x_{5}=0$ maka didapat solusi khusus $\begin{bmatrix}2 & 0 & -1 & 1 & 0\end{bmatrix} ^\top$
Lalu dengan mengasumsikan $x_{2}=s,x_{5}=t, s,t \in \mathbb{R}$, akan didapatkan solusi umum:
$$
\left\{ x \in \mathbb{R}^5:x=\begin{bmatrix}
2 \\
0 \\
-1 \\
1 \\
0
\end{bmatrix}+s\begin{bmatrix}
2 \\
1 \\
0 \\
0 \\
0
\end{bmatrix}+t\begin{bmatrix}
2 \\
0 \\
-1 \\
2 \\
1
\end{bmatrix},\ s,t \in \mathbb{R} \right\} 
$$

> [!NOTE] Bentuk Eselon-Baris Tereduksi (RREF)
> Selain bentuk tersebut, terdapat juga lebih ringkasnya yakni bentuk $Eselon-Baris\ Tereduksi\ (RREF)$. Sebuah augmented matriks dikatakan Eselon-Baris Tereduksi jika memenuhi syarat-syarat berikut:
> - sudah berbentuk Eselon-Baris;
> - setiap pivot bernilai $1$; dan
> - setiap pivot adalah satu-satunya bilangan tak nol di kolom tersebut.

---
#### Minus 1 Trick
dalam mencari solusi **$Ax=0, A \in \mathbb{R}^{k\times n}, x \in \mathbb{R}$**, bisa memakai minus 1 trick, yakni membuat matrik $\tilde{A}, \tilde{A} \in \mathbb{R}^{n \times n}$, dengan menyelipkan sejumlah $n-k$ baris sedemikian sehingga setiap nilai diagonal augmented matrik $\tilde{A}$ adalah $-1$ atau $1$.
Misalnya matriks REF berikut:
$$
\begin{bmatrix}
1 & 3 & 0 & 0 & 3 \\
0 & 0 & 1 & 0 & 9 \\
0 & 0 & 0 & 1 & -4
\end{bmatrix}
$$
Dapat diubah menjadi:
$$
\begin{bmatrix}
1 & 3 & 0 & 0 & 3 \\
0 & -1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 9 \\
0 & 0 & 0 & 1 & -4 \\
0 & 0 & 0 & 0 & -1
\end{bmatrix}
$$
sehingga solusi $x$ untuk $Ax=0$ adalah:
$$
\left\{ x \in \mathbb{R}^5:x=s\begin{bmatrix}
3 \\
-1 \\
0 \\
0 \\
0
\end{bmatrix}+t\begin{bmatrix}
3 \\
0 \\
9 \\
-4 \\
-1
\end{bmatrix}, \ s,t \in \mathbb{R} \right\} 
$$


> [!NOTE] Mencari Inverse Matrik
> Kita juga bisa mencari inverse matrik menggunakan cara yang sama yakni Gaussian Elimination. Seperti contoh berikut:
> ![[Pasted image 20250726211552.png]]
> ![[Pasted image 20250726211615.png]]

# 2.4 Ruang Vektor
---
## 2.4.1 Group

> [!NOTE] Group
> Anggap suatu himpunan $\mathcal{G}$ dan operasi $\otimes:\mathcal{G}\times \mathcal{G}\to \mathcal{G}$ terdefinisi di $G$, maka $(\mathcal{G},\otimes)$ disebut $grup$ jika memenuhi syarat-syarat berikut:
> 1. $Closure$, $\forall x,y \in \mathcal{G}:x\otimes y \in \mathcal{G}$;
> 2. $Asosiatif$, $\forall x,y,z \in \mathcal{G}: (x\otimes y)\otimes z=x\otimes(y\otimes z)$;
> 3. $Elemen \ Netral$, $\forall x \in \mathcal{G}\ \exists e \in \mathcal{G}: x\otimes e=x$ dan $e\otimes x=x$; dan
> 4. $Elemen\ Invers$, $\forall x \in \mathcal{G}\ \exists y \in \mathcal{G}:x\otimes y=y\otimes x=e$ dengan $e$ adalah elemen netral. Kita bisa tulis $x ^{-1}$ untuk menunjukkan invers dari $x$.
> 
> Selanjutnya,
> Jika suatu grup $G=(\mathcal{G},\otimes)$ terpenuhi $\forall x,y \in \mathcal{G}:x\otimes y=y\otimes x$ (bersifat komutatif) maka group ini bisa disebut $Grup\ Abelian$.

> [!NOTE] General Linear Group
> Himpunan matriks reguler (invertible) $A \in R^{n\times n}$ adalah grup terhadap operasi perkalian matriks dan disebut $General\ Linear\ Group$ $GL(n,\mathbb{R})$. Namun sebab perkalian matriks tidak bersifat komutatif, maka ini bukan grup abelian.
## 2.4.2 Ruang Vektor

> [!NOTE] Ruang Vektor
> Sebuah ruang vektor $V=(\mathcal{V},+,\cdot)$ adalah himpunan vektor $\mathcal{V}$ dengan dua operasi berikut: $$\begin{align}+ & :\mathcal{V}+\mathcal{V}\to \mathcal{V} \\
\cdot & :\mathbb{R}\cdot \mathcal{V}\to \mathcal{V}\end{align}$$
>Di mana:
>1. $(\mathcal{V},+)$ adalah grup abelian.
>2. Sifat distributif:
>	1. $\forall \lambda \in \mathbb{R},x,y\in \mathcal{V}:\lambda(x+y)=\lambda x+\lambda y$
>	2. $\forall\lambda,\psi \in \mathbb{R},x \in \mathcal{V}:(\lambda+\psi)x=\lambda x+\psi x$
>3. Asosiatif (outer opperation): $\forall \lambda,\psi \in \mathbb{R},x \in \mathcal{V}:\lambda \cdot(\psi \cdot x)=(\lambda \psi)\cdot x$
>4. Elemen netral terhadap operasi luar, $\forall x \in \mathcal{V}:1\cdot x=x$
## 2.4.3 Subruang Vektor

> [!NOTE] Subruang Vektor
> Misal $V=(\mathcal{V},+,\cdot)$ adalah ruang vektor, dan $\mathcal{U\subseteq \mathcal{V}, \mathcal{U}\neq \emptyset}$. Maka $U=(\mathcal{U,+,\cdot})$ adalah subruang vektor dari $V$ (atau subruang linear) jika $U$ adalah ruang vektor dengan operasi $+$ dan $\cdot$ terbatas pada $\mathcal{U}\times \mathcal{U}$ dan $\mathbb{R}\times \mathcal{U}$, dinotasikan sebagai $U\subseteq V$.

Subruang vektor adalah ide kunci dari machine learning, misalnya pada *dimensionality reduction*.
# 2.5 Linear Independency

> [!NOTE] Kombinasi Linear
> Ambil suatu ruang vektor $V$ dan sejumlah terbatas vektor $x_{1},\dots,x_{k}\in V$. Maka, setiap $v\in V$ dalam bentuk:$$
> v=\lambda_{1}x_{1},\dots,\lambda_{k}x_{k}=\sum_{i=1}^k\lambda_{i}x_{i},\ \lambda_{1},\dots,\lambda _k\in \mathbb{R}$$
> , adalah $Kombinasi\ Linear$ dari $x_{1},\dots,x_{k}$.

> [!NOTE] Linear (In)dependence
> Ambil suatu ruang vektor $V$ dan sejumlah terbatas vektor $x_{1},\dots,x_{k}\in V$. Jika ada kombinasi linear non-trivial sedemikian sehingga $\sum_{i=1}^k\lambda_{i}x_{i}$ dengan setidaknya ada satu $\lambda_{i}\neq 0$, vektor $x_{1},\dots,x_{k}$ disebut $linearly\ dependent$. Sebaliknya jika hanya terdapat kombinasi trivial, $\lambda_{1},\dots,\lambda_{k}=0$, vektor $x_{1},\dots,x_{k}$ disebut $linearly\ independent$

Linear independent adalah konsep terpenting dalam aljabar linear. Sederhananya, himpunan dari vektor-vektor yang linearly independent mengandung vektor-vektor yang tidak *redundant*, artinya jika kita menghapus salah satu vektor kita akan kehilangan informasi penting.
Jika kita membentuk matriks baris elementer hingga kita dapatkan bentuk eselon-baris, maka semua vektor linearly independent jika dan hanya jika semua kolom adalah kolom pivot. Contoh:
![[Pasted image 20250728112925.png]]
# 2.6 Basis dan Rank
## 2.6.1 Generating Set & Basis
> [!NOTE] Generating Set & Span
> Ambil suatu ruang vektor $V=(\mathcal{V},+,\cdot)$ dan himpunan vektor $\mathcal{A}=\{ x_{1},\dots,x_{k} \}\in V$. Jika untuk setiap $v\in \mathcal{V}$ dapat diekspresikan dalam kombinasi linear dari $x_{1},\dots,x_{k}$, maka $\mathcal{A}$ disebut $generating\ set$ dari $V$. Himpunan dari semua kombinasi linear dari $\mathcal{A}$ disebut $span$ dari $\mathcal{A}$ ditulis $span[\mathcal{A}]$. 

> [!NOTE] Minimal & Basis
> Ambil suatu ruang vektor $V=(\mathcal{V},+,\cdot)$ dan $\mathcal{A}\subseteq \mathcal{V}$, generating set $\mathcal{A}$ dari $\mathcal{V}$ disebut $minimal$ jika tidak ada $\tilde{\mathcal{A}}\subsetneq \mathcal{A}$ yang me-span $\mathcal{V}$. Setiap linearly independent generating set dari $\mathcal{V}$ adalah minimal dan disebut $basis$ dari $\mathcal{V}$. 

Misalnya, basis standar atau disebut $cannonical$ dari $\mathbb{R}^3$ adalah:
$$
\mathcal{B}=\left\{ \begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix},\begin{bmatrix}
0 \\
1 \\
0
\end{bmatrix},\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix} \right\} 
$$
## 2.6.2 Rank
Jumlah dari kolom yang linearly independent dari matrix $A\in \mathbb{R}^{m\times n}$ sama dengan jumlah baris yang linearly independent, dan jumlah ini disebut dengan $rank$ dan dinotasikan sebagai $rk(A)$.
Misalnya, $rk(\begin{bmatrix}1 & 0 & 1 \\ 0 & 1 & 1 \\ 0 & 0 & 0\end{bmatrix})=2$.