![[Pasted image 20250804102957.png]]
# 4.1 Determinant & Trace

> [!NOTE] Determinan
> Determinan dari matrik $A\in \mathbb{R}^{n\times n}$ adalah fungsi yang memetakan $A$ ke bilangan Real. Dinotasikan dengan $\det(A)$.

Invers dari matrik $2\times 2$ dapat ditulis sebagai:
$$
A^{-1} = \frac{1}{a_{11}a_{22}-a_{12}a_{21}}\begin{bmatrix}
a_{22} & -a_{12} \\
-a_{21} & a_{11}
\end{bmatrix}
$$
di mana
$$
\det(A) = \begin{vmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}
$$
**Teorema**. Untuk semua matriks persegi $A\in \mathbb{R}^{n\times n}$, maka $A$ mempunyai inverse jika dan hanya jika $\det(A)\neq 0$.

> [!NOTE] Upper Triangular & Lower Triangular
> Sebuah matriks disebut *upper triangular* jika semua nilai di bawah diagonal utama adalah $0$, dan sebuah matriks disebut *lower triangular* jika semua nilai di atas diagonal utama adalah $0$.

**Teorema**. misal $T$ adalah matrik triangular. Maka 
$$
\det(T)=\prod_{i=1}^nT_{ii}
$$
### Contoh 1
Untuk $A=\begin{bmatrix}1 & 2 & 3 \\ 0 & 5 & 6 \\ 0 & 0 & 9\end{bmatrix}$ maka $\det(A)=1(5)(9)=45$

**Teorema**. Ambil sebuah matrik $A\in R^{n\times n}$. Maka untuk semua $j=1,\dots,n$:
1. Ekspansi sepanjang kolom $j$:
$$
\det(A)=\sum_{k=1}^n(-1)^{k+j}a_{kj}\det(A_{k,j})
$$
2. Ekspansi sepanjang baris $j$:
$$
\det(A)=\sum_{k=1}^n(-1)^{k+j}a_{jk}\det(A_{j,k})
$$
Di sini, $A_{k,j}\in \mathbb{R}^{n-1\times n-1}$ adalah submatriks yang diperoleh jika kita menghapus baris $k$ dan kolom $j$.
---
Untuk $A\in \mathbb{R}^{n\times n}$, determinannya memenuhi sifat-sifat berikut:
1. $\det(AB)=\det(A)\det(B)$
2. $\det A=\det A ^\top$
3. $\det(A^{-1})=\frac{1}{\det(A)}$
4. Matriks-matriks yang sama memiliki determinan yang sama
5. Menambahkan kelipatan kolom/baris ke yang lainnya tidak mengubah determinan
6. Perkalian kolom/baris dengan skalar $\lambda \in \mathbb{R}$ menskala $\det(A)$ sebesar $\lambda$. $\det(\lambda A)=\lambda^n\det(A)$.
7. Menukar dua kolom/baris mengubah tanda determinan.

**Teorema**. Matriks persegi $A\in \mathbb{R}^{n\times n}$ memiliki $\det(A)\neq 0$ jika dan hanya jika $rk(A)=n$. Artinya, matriks $A$ invertible jika dan hanya jika dia full rank.

---
> [!NOTE] Trace
> Trace dari matriks $A\in \mathbb{R}^{n\times n}$ didefinisikan sebagai: $$
tr(A):=\sum_{i=1}^n a_{ii}$$, adalah jumlah dari elemen-elemen diagonal $A$.

Trace memenuhi sifat-sifat berikut:
1. $tr(A+B)=tr(A)+tr(B)$, untuk $A,B\in \mathbb{R}^{n\times n}$
2. $tr(\alpha A)=\alpha tr(A)$
3. $tr(I_{n})=n$
4. $tr(AB)=tr(BA)$, untuk $A\in \mathbb{R}^{n\times k}, B\in \mathbb{R}^{k\times n}$.


> [!NOTE] Caracteristic Polynomial
> For $\lambda \in \mathbb{R}$ dan matriks persegi $A\in \mathbb{R}$: $$
\begin{align}
p_{A}(\lambda) & :=\det(A-\lambda I) \\
 & = c_{0}+c_{1}\lambda+c_{2}\lambda^2+\dots+c_{n-1}\lambda^{n-1}+(-1)^n \lambda^n\end{align}$$
 $c_{0},\dots,c_{n-1}\in \mathbb{R}$ adalah *characteristic polynomial* dari $A$. Secara khusus, $$
\begin{align}
c_{0} & =\det(A) \\
c_{n-1} & =(-1)^n-1tr(A)\end{align}$$

# 4.2 Eigenvalues & Eigenvectors

> [!NOTE] Eigenvalues & Eigenvectors
> Bayangkan matriks **A** sebagai mesin transformasi (rotasi, skala, geser, dll).
> Biasanya, ketika kita masukkan sebuah vektor **x**, arah vektor itu akan berubah.
> **Namun**: ada beberapa arah spesial yang **tidak berubah arah**, hanya panjangnya yang berubah.
> - **Eigenvector** → arah yang tetap
> - **Eigenvalue** → faktor perubahan panjangnya
## 4.2.1 Persamaan Dasar
$$
A \mathbf{v} = \lambda \mathbf{v}
$$
- **v** = eigenvector (tidak nol)
- **λ** = eigenvalue (skalar)
- Artinya: ketika **v** dilewatkan ke **A**, hasilnya hanya skala dari **v** itu sendiri.
## 4.2.2 Cara Mencari Eigenvalues & Eigenvectors

1. Mulai dari persamaan:
   $$
   A \mathbf{v} = \lambda \mathbf{v}
   $$

2. Pindahkan semua ke satu sisi:
   $$
   (A - \lambda I)\mathbf{v} = 0
   $$

3. Syarat solusi non-trivial:
   $$
   \det(A - \lambda I) = 0
   $$
   → ini disebut **persamaan karakteristik**

4. Selesaikan polinomial karakteristik untuk menemukan **λ**

5. Substitusikan λ ke $(A - \lambda I)\mathbf{v} = 0$ untuk menemukan **v**

---

###  Contoh 2

Misal $A = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}$:
1. **Bentuk $A - \lambda I$**:
   $$
   \begin{bmatrix} 4 - \lambda & 2 \\ 1 & 3 - \lambda \end{bmatrix}
   $$
2. $\det (A)= 0$:
   $$
\begin{align}
(4-\lambda)(3-\lambda) - (2)(1) &  = 0 \\
\lambda^2 - 7\lambda + 10  & = 0 \\
(\lambda - 5)(\lambda - 2) &  = 0
\end{align}
   $$
    Jadi eigenvalues λ₁ = 5, λ₂ = 2
3. **Eigenvector untuk λ₁ = 5**:
   - $(A - 5I) = \begin{bmatrix} -1 & 2 \\ 1 & -2 \end{bmatrix}$
   - Persamaan: $-x + 2y = 0 \Rightarrow x = 2y$
   - Pilih $y = 1 \Rightarrow x = 2$
   - Eigenvector: **v₁** = [2, 1]

4. **Eigenvector untuk λ₂ = 2**:
   - $(A - 2I) = \begin{bmatrix} 2 & 2 \\ 1 & 1 \end{bmatrix}$
   - Persamaan: $2x + 2y = 0 \Rightarrow x = -y$
   - Pilih $y = 1 \Rightarrow x = -1$
   - Eigenvector: **v₂** = [-1, 1]

---

## 4.2.3 Hubungan dengan Determinant & Trace
- **Trace**: $\text{tr}(A) = \sum \lambda_i$  
  → 4 + 3 = 7 ✅ sama dengan 5 + 2
- **Determinant**: $\det(A) = \prod \lambda_i$  
  → 10 ✅ sama dengan 5 × 2

---
## 4.2.4 Eigenspace
**Definisi**:  
Untuk setiap eigenvalue $\lambda$, eigenspace adalah himpunan semua eigenvectors yang berhubungan dengan $\lambda$, ditambah vektor nol. Secara formal:
$$
E_\lambda = \{ \mathbf{v} \in \mathbb{R}^n \ |\ (A - \lambda I)\mathbf{v} = 0 \}
$$
Eigenspace adalah **ruang vektor** karena:

- Jika $\mathbf{u}$ dan $\mathbf{v}$ ada di $E_\lambda$​, maka $u+v \in E_{\lambda}$​.
    
- Jika $\mathbf{v}$ ada di $E_\lambda$ dan $c$ adalah skalar, maka $c\mathbf{v}$ juga ada di $E_\lambda$​.
    

**Contoh dari matriks di atas**:
- Untuk $\lambda_1 = 5$, eigenspace $E_5$​ dibentuk oleh semua kelipatan dari $\begin{bmatrix} 2 \\ 1 \end{bmatrix}$.
- Untuk $\lambda_2 = 2$, eigenspace $E_2$ dibentuk oleh semua kelipatan dari $\begin{bmatrix} -1 \\ 1 \end{bmatrix}$.
## 4.2.5  Aplikasi di Machine Learning
- **PCA (Principal Component Analysis)** → memilih eigenvectors dari matriks kovarians untuk menemukan arah data terbesar.
- **Markov Chains** → steady state = eigenvector dengan λ = 1
- **Graph Analysis** → centrality dihitung dari eigenvectors
- **Differential Equations** → solusi sistem linier berbasis eigen-decomposition

# 4.3 Cholesky Decomposition
Cholesky Decomposition adalah teknik memecah matriks **simetris** dan **positif definit** menjadi hasil perkalian matriks segitiga bawah dan transpose-nya.
$$A = L \cdot L ^\top$$
di mana:
- $L$= matriks segitiga bawah (lower triangular) dengan elemen diagonal positif.
- $L ^\top$ = transpose dari $L$ (segitiga atas).
## 4.3.1 Syarat Cholesky Decomposition
Agar bisa dilakukan, matriks $A$ harus:
1. **Simetris** → $A = A ^\top$
2. **Positif definit** → untuk semua vektor tak nol $x$,
$$
\mathbf{x} ^\top  A \mathbf{x} > 0
$$
    atau semua **eigenvalues**-nya positif.    
## 4.3.2 Rumus Elemen $L$
Untuk $A\in \mathbb{R}^{n\times n}$:
1. Elemen diagonal:
$$
L_{ii} = \sqrt{A_{ii} - \sum_{k=1}^{i-1} L_{ik}^2}
$$
2. Elemen di bawah diagonal:
$$
L_{ji} = \frac{A_{ji} - \sum_{k=1}^{i-1} L_{ik} L_{jk}}{L_{ii}}, \quad \text{untuk } j > i
$$
## 4.3.3 Aplikasi di Machine Learning & Data Science
- **Optimisasi**: Solusi cepat untuk sistem persamaan $A\mathbf{x} = \mathbf{b}$ ketika $A$ adalah matriks kovarians (positif definit).
- **Gaussian Processes**: Invers kovarians untuk prediksi.
- **Monte Carlo Simulation**: Membuat korelasi antar variabel acak.
- **Kalman Filter**: Perhitungan kovarians dalam pelacakan objek.
# 4.4 Eigendecomposition & DIaglonalization

> [!NOTE] Diagonalizable
> Suatu matriks persegi $A\in \mathbb{R}^{n\times n}$ dikatakan $diagonalizable$ jika ia mirip dengan matriks diagonal, artinya ada matriks inversibel $P\in \mathbb{R}^{n\times n}$ sehingga $D=P^{-1}AP$

**Teorema**. Eigendecomposition menyatakan bahwa setiap matriks persegi $A\in \mathbb{R}^{n\times n}$ dapat dipecah menjadi
$$
A=PDP^{-1}
$$
Di mana $P\in \mathbb{R}^{n\times n}$ dan $D$ adalah matriks diagonal yang nilai setiap diagonalnya adalah *eigenvalues* dari A, jika dan hanya jika *eigenvektor* dari $A$ membentuk basis $R^n$.

**Teorema**. Matriks simetris selalu bisa didagonalisasikan.

# 4.5 Singular Value Decomposition (SVD)
Sebuah matriks rectangular dapat merubah suatu vektor ke dimensi yang lain. Sebuah matriks berukuran $m\times n$ bisa merubah vektor berdimensi $n$ ke vektor berdimensi $m$.
### Contoh 3
matriks $R=\begin{bmatrix}1 & 0 &  0 \\ 0 & 1 & 0\end{bmatrix}$ bisa merubah vektor $v=\begin{bmatrix}2 \\ 3 \\ 4\end{bmatrix}$ sebagai berikut:
$$
\begin{align}
Rv & =v' \\
\begin{bmatrix}1 & 0 &  0 \\ 0 & 1 & 0\end{bmatrix}\begin{bmatrix}2 \\ 3 \\ 4\end{bmatrix} & = \begin{bmatrix}
2 \\
3
\end{bmatrix}
\end{align}
$$
$v$ berdimensi $3$ sedangkan $v'$ berdimensi $2$.
Lalu matriks $U=\begin{bmatrix}1 & 0 \\ 0 & 1 \\ 1 & 1\end{bmatrix}$ bisa merubah $w=\begin{bmatrix}2 \\ 3\end{bmatrix}$ sebagai berikut:
$$
\begin{align}
Uw & =w' \\
\begin{bmatrix}1 & 0 \\ 0 & 1 \\ 1 & 1\end{bmatrix}\begin{bmatrix}2 \\ 3\end{bmatrix} & = \begin{bmatrix}
2 \\
3 \\
5
\end{bmatrix}
\end{align}
$$
$w$ berdimensi $2$ sedangkan $w'$ berdimensi $3$.

---
Jika kita ambil sembarang matriks $A\in \mathbb{R}^{m\times n}$ dan mengalikannya dengan $A ^\top$ maka akan menghasilkan matriks persegi yang simetris:
- $AA ^\top \in \mathbb{R}^{m\times m}$, disebut $(S_{L})$ memiliki $m$ buah eigenvector tegak lurus, disebut sebagai $Left\ Singular\ Vector$.
- $A ^\top A\in \mathbb{R}^{n\times n}$, disebut $(S_{R})$ memiliki $n$ buah eigenvector tegak lurus, disebut sebagai $Right\ Singular\ Vector$.

**Teorema**. SVD menyatakan bahwa sebarang matriks $A\in \mathbb{R}^{m\times n}$ dapat dipecah menjadi perkalian matriks
$$
A=U\Sigma V ^\top 
$$
Dimana:
- $U$: Matriks ortogonal berukuran $m\times m$. Kolom-kolomnya adalah Left singular vector.
- $\Sigma$: Matriks diagonal berukuran $m\times n$. Nilai-nilai pada diagonalnya disebut **Nilai Singular (Singular Values)**.
- $V ^\top$: Transpose dari matriks ortogonal $V$ yang berukuran $n\times n$. Kolom-kolomnya adalah Right Singular Vectors.
### Contoh 4
cari dekomposisi dari $A=\begin{bmatrix}3 & 0 \\ 4 & 5\end{bmatrix}$

**Langkah 1: Cari Matriks $V$ dan Nilai Singular ($\Sigma$)**
Kita akan menggunakan matriks simetris $A ^\top A$ untuk menemukan $V$ dan $\Sigma$.
$$
\begin{align}
A ^\top  A  & = \begin{bmatrix} 3 & 4 \\ 0 & 5 \end{bmatrix} \begin{bmatrix} 3 & 0 \\ 4 & 5 \end{bmatrix} = \begin{bmatrix} 9+16 & 0+20 \\ 0+20 & 0+25 \end{bmatrix} = \begin{bmatrix} 25 & 20 \\ 20 & 25 \end{bmatrix}
\end{align}
$$

Sekarang, cari _eigenvalue_ ($\lambda$) dan _eigenvector_ dari $A ^\top A$.
- Eigenvalue dari $A ^\top A$ adalah $\lambda_{1}=45$ dan $\lambda_{2}=5$.
- Nilai Singular ($\sigma$): Adalah akar kuadrat dari eigenvalue. Kita urutkan dari yang terbesar.
    - $\sigma_1=\sqrt{45}=3\sqrt5$
    - $\sigma_2=\sqrt5$
- Diperoleh $\Sigma=\begin{bmatrix}\sigma_{1} & 0 \\ 0 & \sigma_{2}\end{bmatrix}=\begin{bmatrix}3\sqrt{ 5 } & 0 \\ 0 & \sqrt{ 5 }\end{bmatrix}$
- **Vektor Singular Kanan ($V$)**: Adalah eigenvector dari $A ^\top A$ yang sudah dinormalisasi.
    - Untuk $\lambda_{1}=\sqrt{ 45 }$, eigenvectornya adalah $v_1=\begin{bmatrix} \frac{1}{\sqrt2}  \\   \frac{1}{\sqrt2} \end{bmatrix}$
    - Untuk $\lambda_{2}=\sqrt{ 5 }$, eigenvectornya adalah $v_2=\begin{bmatrix} -\frac{1}{\sqrt2}  \\   \frac{1}{\sqrt2} \end{bmatrix}$
    - Diperoleh:
$$
\begin{align}
V & =\begin{bmatrix} \frac{1}{\sqrt2} & -\frac{1}{\sqrt2} \\ \frac{1}{\sqrt2} & \frac{1}{\sqrt2} \end{bmatrix} \\
V ^\top  & = \begin{bmatrix} \frac{1}{\sqrt2} & \frac{1}{\sqrt2} \\ -\frac{1}{\sqrt2} & \frac{1}{\sqrt2} \end{bmatrix}
\end{align}
$$

**Langkah 2: Cari Matriks U**
$$
\begin{align}
u_i & =\frac{1}{\sigma_i}Av_i \\
u_{1} & = \frac{1}{3\sqrt{ 5 }}\begin{bmatrix}
3 & 0 \\
4 & 5
\end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt2}  \\   \frac{1}{\sqrt2} \end{bmatrix}= \begin{bmatrix}
\frac{1}{\sqrt{ 10 }} \\
\frac{3}{\sqrt{ 10 }}
\end{bmatrix} \\
u_{2} & = \frac{1}{\sqrt{ 5 }}\begin{bmatrix}
3 & 0 \\
4 & 5
\end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt2}  \\   -\frac{1}{\sqrt2} \end{bmatrix}= \begin{bmatrix}
-\frac{3}{\sqrt{ 10 }} \\
\frac{1}{\sqrt{ 10 }}
\end{bmatrix}
\end{align}
$$
diperoleh
$$
U=\begin{bmatrix}
\frac{1}{\sqrt{ 10 }} & -\frac{3}{\sqrt{ 10 }} \\
\frac{3}{\sqrt{ 10 }} & \frac{1}{\sqrt{ 10 }}
\end{bmatrix}
$$
$$
\therefore A=\begin{bmatrix}
\frac{1}{\sqrt{ 10 }} & -\frac{3}{\sqrt{ 10 }} \\
\frac{3}{\sqrt{ 10 }} & \frac{1}{\sqrt{ 10 }}
\end{bmatrix}\begin{bmatrix}3\sqrt{ 5 } & 0 \\ 0 & \sqrt{ 5 }\end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt2} & \frac{1}{\sqrt2} \\ -\frac{1}{\sqrt2} & \frac{1}{\sqrt2} \end{bmatrix}
$$
### Aplikasi SVD
- **Kompresi Gambar (Aproksimasi Peringkat Rendah)**: Sebuah gambar dapat direpresentasikan sebagai matriks piksel. Nilai singular yang besar di matriks Σ menunjukkan komponen "paling penting" dari gambar. Dengan hanya menyimpan beberapa nilai singular terbesar (dan vektor U, V yang bersesuaian) dan mengabaikan yang kecil, kita bisa merekonstruksi gambar yang sangat mirip dengan aslinya tetapi dengan ukuran file yang jauh lebih kecil.
- **Principal Component Analysis (PCA)**: SVD adalah mesin utama di balik PCA, sebuah teknik untuk mengurangi dimensi data dengan tetap mempertahankan informasi sebanyak mungkin.
- **Sistem Rekomendasi**: Digunakan untuk memprediksi preferensi pengguna (misalnya, di Netflix atau Spotify) dengan menemukan pola tersembunyi dalam data interaksi pengguna-item.
- **Menghilangkan Noise**: Dalam data sinyal atau gambar, komponen dengan nilai singular kecil sering kali berhubungan dengan _noise_. Dengan menghilangkannya, kita bisa "membersihkan" data tersebut.
# 4.6 Matrix Approximation
Melalui konsep SVD, suatu matriks $A\in \mathbb{R}^{m\times n}$ dengan rank $r$ bisa ditulis sebagai penjumlahan matriks-matriks rank-1 $A_{i}$ sehingga:
$$
A= \sum_{i=1}^r\sigma_{i}u_{i}v_{i} ^\top = \sum_{i=1}^r\sigma_{i}A_{i}
$$
Lalu kita bisa menyederhanakan penjumlahan ini dengan tidak menyertakan keseluruhan $i=1,\dots,r$. Kita ambil suatu nilai $k<r$ untuk mendapatkan *rank-k approximation*:
$$
\hat{A}(k)=\sum_{i=1}^k\sigma_{i}u_{i}v_{i} ^\top = \sum_{i=1}^k\sigma_{i}A_{i}
$$
Contoh penerapan *matrix approximation* pada citra:
![[Pasted image 20250814194308.png]]
# 4.7 Matrix Phylogeny
![[Pasted image 20250814194344.png]]
