![[Pasted image 20250910153316.png]]
# 6.1 Construction of a Probability Space
## 6.1.1 Probabilitas dan Peubah Acak
Sebuah **ruang probabilitas** (_probability space_) adalah tripel ($\Omega, \mathcal{A}, P$), dengan:
1. **Sample space** $\Omega$: himpunan semua kemungkinan hasil dari suatu percobaan acak.
    - Contoh: pada pelemparan koin, $\Omega = \{\text{Head}, \text{Tail}\}$.
2. **Event space ($\mathcal{A}$)**  
    Disebut juga _ruang kejadian_. Sebuah subset $A \subseteq \Omega$ dikatakan elemen dari $\mathcal{A}$ apabila setelah percobaan dilakukan, kita dapat _mengamati_ apakah hasil $\omega \in \Omega$ tersebut termasuk ke dalam $A$ atau tidak.
    Dengan kata lain: suatu subset masuk ke event space hanya jika ia teramati/terdefinisi secara jelas dalam eksperimen.
    - Untuk distribusi diskret, $\mathcal{A}$ seringkali diambil sebagai **power set** dari $\Omega$, yaitu semua subset yang mungkin.
    - Untuk distribusi kontinu, $\mathcal{A}$ biasanya berupa himpunan Borel, karena tidak semua subset dari $\mathbb{R}$ bisa dijadikan event yang “terukur”.
3. **Probability measure (PP)**  
    Adalah fungsi yang memberikan probabilitas pada setiap event $A \in \mathcal{A}$, dengan sifat:
    - $P(A) \in [0,1]$ untuk semua $A \in \mathcal{A}$,
    - $P(\Omega) = 1$,
    - Jika $(A_i)_{i=1}^\infty$ adalah himpunan event yang saling lepas, maka
$$
\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty P(A_i)
$$

> [!NOTE] Contoh 1: Permainan Funfair dengan Koin
> **Eksperimen:**
> - Kita punya sebuah kantong berisi koin USA ($) dan koin UK (£).
> - Kita melakukan dua kali pengambilan koin **dengan pengembalian** (_with replacement_).
> - Probabilitas mengambil koin USA ($) dalam satu kali undian adalah $0.3$.
> - Probabilitas mengambil koin UK ($£$) adalah $0.7$.
> $$Ω={($,$),($,£),(£,$),(£,£)}$$
> Misal kita definisikan $X$ sebagai peubah acak yang menotasikan seberapa banyak munculnya $ pada percobaan, maka:$$
\begin{align}
X(($,$))=2\\
X(($,£))=1\\
X((£,$))=1\\
X((£,£))=0
\end{align}$$
Sehingga:$$
\begin{align}
P(X=2) & =P((\textdollar,\textdollar)) \\
 & =P(\textdollar).P(\textdollar) \\
 & =(0.3)(0.3) = 0.09 \\
P(X=1) & =P((\textdollar,£) \cup (£,\textdollar)) \\
 & = P((\textdollar,£))+P((£,\textdollar)) \\
 & =(0.3)(1-0.3)+(1-0.3)(0.3) = 0.42 \\
P(x=0) & =P((£,£)) \\
 & =(1-0.3)(1-0.3) = 0.49
\end{align}$$

---
# 6.2 Discrete and Continuous Probabilities
Jika _target space_ $T$ bersifat **diskret** (misalnya $\{0,1\}$, $\{1,2,3,4,5,6\}$), maka yang kita tanyakan adalah probabilitas bahwa variabel acak $X$ sama dengan suatu nilai tertentu:
$$
P(X = x), \quad x \in T
$$
Fungsi $p(x) = P(X = x)$ ini disebut **probability mass function (pmf)**.

Jika _target space_ $T$ bersifat **kontinu** (misalnya $\mathbb{R}$), maka lebih alami berbicara tentang probabilitas bahwa $X$ jatuh dalam suatu interval:
$$
P(a \leq X \leq b), \quad a < b
$$
Untuk memudahkan, konvensi yang umum dipakai adalah mendefinisikan **cumulative distribution function (cdf)**:
$$
F(x) = P(X \leq x)
$$
## 6.2.1 Discrete Probabilities

> [!NOTE] Contoh 2: Pelemparan Dadu
> Untuk variabel acak $X=\text{hasil lemparan dadu}$, dan $T=\{1,2,3,4,5,6\}$, maka:$$
p(x)=\frac{1}{6},\quad \forall x \in T$$

Dalam kasus multivariat, jika kita punya beberapa variabel acak diskret misal $\left( X_{1},X_{2},\dots,X_{n} \right)$, maka distribusi gabungan didefinisikan sebagai **joint pmf**:
$$
p(x_{1},x_{2},\dots,x_{n})=P(X_{1}=x_{1},X_{2}=x_{2},\dots,X_{n}=x_{n})
$$
dan memenuhi:
$$
\sum_{x_{1}}\dots \sum_{x_{n}}p(x_{1},\dots,x_{n})=1
$$
*Peluang marginal*: Peluang dari suatu variabel acak tanpa memperhatikan nilai variabel acak yang lain
*Peluang kondisional*: Peluang dari suatu variabel acak dengan memperhatikan nilai variabel acak yang lain sebagai syarat (misal $P(X|Y)$)
## 6.2.2 Continuous Probabilities

> [!NOTE] Fungsi Kepekatan Peluang/Probability Density Function (pdf)
> Suatu fungsi $f:\mathbb{R}^D \to R$ disebut $pdf$ jika memenuhi:
> 1. $\forall x \in \mathbb{R}^D: f(x)\geq 0$
> 2. integralnya ada dan $$
\int_{\mathbb{R}^D}f(x)dx=1$$

**Intuisi:** Dalam kasus diskret, integral digantikan dengan sum.
Peluang suatu variabel acak kontinu $X$  berada di interval $[a,b]$ diberikan oleh:
$$
\int_{a}^b f(x) dx
$$
yang artinya adalah luas daerah di bawah kurva di antara $a$ dan $b$. **Akibatnya**, untuk kasus kontinu nilai peluang di suatu titik $P(X=x)=0$ karena mengambil $a=b$.

> [!NOTE] Cumulative Distribution Function (CDF)
> fungsi *cdf* dari suatu variabel acak multivariat $X$ dengan $x \in \mathbb{R}^D$ diberikan sebagai: $$
F_{X}(x)=P(X_{1}\leq x_{1},\dots,X_{D}\leq x_{D})$$
di mana $X=\left[ X_{1},\dots,X_{D} \right]^T$ dan $x=\left[ x_{1},\dots,x_{D} \right]^T$. Juga bisa ditulis sebagai integral dari pdf: $$
F_{X}(x)=\int_{-\infty}^{x_{1}} \dots \int_{-\infty}^{x_{D} }f(z_{1},\dots,z_{D})dz_{1}\dots dz_{D}$$

Yang artinya adalah total area di bawah kurva dari $-\infty$ ke $x$.
# 6.3 Sum Rule, Product Rule, and Bayes’ Theorem
***Sum rule***: Jika kita punya dua variabel acak $Y$ dan $Y$, maka **probabilitas marjinal** dari $X$ bisa diperoleh dengan menjumlahkan (untuk diskrit) atau mengintegralkan (untuk kontinu) probabilitas gabungan
$$
p(x)= \begin{cases}
\sum_{y\in \mathcal{Y}} p(x,y), \quad \text{jika diskret} \\
\int_{\mathcal{Y}}p(x,y)dy, \quad \text{jika kontinu}
\end{cases}
$$
*intuisi*: Misal kita melempar koin dan dadu sekaligus, jika kita ingin menghitung total peluang dadu di angka $3$ maka kita jumlahkan peluang dadu di angka $3$ dengan kepala dan peluang dadu di angka $3$ dengan ekor.

***Product Rule***: 
$$
P(X,Y)=P(Y|X)P(X)
$$
*intuisi*: Misal kita punya 3 kelereng merah ($R$) dan 5 kelereng biru ($B$), jika kita ambil satu kelereng, lalu tanpa pengembalian kita ambil lagi 1 kelereng yang lain, berapa peluang $P(R,B)$. Pertama peluang terambil $R$ di pengambilan pertama adalah $P(R)=\frac{3}{8}$, lalu peluang terambil $B$ di pengambilan kedua adalah $P(B|R)=\frac{5}{7}$ sehingga $P(R,B)=P(R)\times P(B|R)=P(B|R)\times P(R)=\frac{5}{7}\times \frac{3}{8}=\frac{15}{56}$.

***Teorema Bayes***:
$$
\underbrace{ P(X|Y) }_{ posterior }=\frac{\overbrace{ P(Y|X) }^{ likelihood }\overbrace{ P(X) }^{ prior }}{\underbrace{ P(Y) }_{ evidence }}
$$
dengan
- $P(X)$: **prior** → keyakinan awal tentang $X$.
- $P(Y \mid X)$: **likelihood** → seberapa mungkin kita mengamati $Y$ jika $X$ benar.
- $P(X \mid Y)$: **posterior** → keyakinan baru tentang $X$ setelah melihat data $Y$.
- $P(Y)$: **evidence** → faktor normalisasi supaya hasilnya tetap jadi probabilitas valid.

### Contoh 3: Kantong Permen
Misalkan ada **dua kantong permen**:
- Kantong A: 70% merah 🍬, 30% hijau 🍬.
- Kantong B: 30% merah 🍬, 70% hijau 🍬.
Kita pilih satu kantong **secara acak** (probabilitas 50%-50%), lalu ambil **satu permen**.
Jika ternyata permennya **merah**. _Seberapa besar peluang kita memilih dari Kantong A?_
Definisikan:
- $H_{A}$: Peluang terpilih kantong $A$.
- $H_{B}$: Peluang terpilih kantong $B$.
- $E$: Peluang terambil permen merah.
Kita memiliki informasi awal yakni:
- Prior: $H_{A}=H_{B}=0.5$.
- Likelihood: $P(E \mid H_A) = 0.7, \quad P(E \mid H_B) = 0.3$.

Teorema Bayes:
$$
P(H_A \mid E) = \frac{P(E \mid H_A)\, P(H_A)}{P(E)}
$$
Dengan:
$$
\begin{align}
P(E) & = P(E \mid H_A) P(H_A) + P(E \mid H_B) P(H_B) \\
 & = (0.7)(0.5) + (0.3)(0.5) = 0.35 + 0.15 = 0.5
\end{align}
$$
Sehingga:
$P(H_A \mid E) = \frac{0.7 \times 0.5}{0.5} = 0.7$

Artinya, setelah melihat permen merah, peluang bahwa kantong yang dipilih adalah Kantong A naik dari 50% → 70%.
# 6.4 Summary Statistics and Independence
## 6.4.1 Means and Covariances

> [!NOTE] Mean
> Mean (Nilai ekspektasi) dari suatu variabel acak $X$ dengan $x \in \mathbb{R}^D$ adalah rerata dan didefinisikan sebagai: $$
E_{X}[x]=\begin{bmatrix}
E_{X_{1}}[x_{1}] \\
\vdots \\
E_{X_{D}}[x_{D}]\end{bmatrix} \in \mathbb{R}^D$$
di mana $$
E_{X_{d}}[x_{d}]=\begin{cases}
\int_{\mathcal{X}} x_{d}p(x_{d})dx_{d}, \text{jika kontinu} \\
\sum_{x_{i} \in \mathcal{X}} x_{i}p(x_{d}=x_{i}), \text{jika diskret}\end{cases}, \quad d=1,\dots,D$$

Misal kita punya data sebagai berikut:

|                 | probability | X       | Y       |
| --------------- | ----------- | ------- | ------- |
| State 1: Panas  | $0.5$       | Rp$9jt$ | Rp$8jt$ |
| State 2: Biasa  | $0.3$       | Rp$5jt$ | Rp$6jt$ |
| State 3: Dingin | $0.2$       | Rp$3jt$ | Rp$4jt$ |
(**Tabel 1**: pengaruh hawa cuaca terhadap penjualan produk $X$ dan $Y$)
Maka nilai harapan untuk $X$ dan $Y$ adalah
$$
\begin{align}
E[X] & = (0.5)(9jt)+(0.3)(5jt)+(0.2)(3jt) \\
 & = 6.6jt \\
E[Y] & = (0.5)(8jt)+(0.3)(6jt)+(0.2)(4jt) \\
 & = 6.6jt
\end{align}
$$
**Note:** kadangkala mean juga ditulis sebagai $\mu$.

> [!NOTE] Kovarians Univariat
> Kovarians untuk variabel acak univariat $X$ dan $Y$  adalah ekspektasi dari perkalian antara selisih (deviasi) nilai dengan ekspektasinya keduanya:$$
Cov_{X,Y}[x,y]=E_{X,Y}[(x-\mu_{x})(y-\mu_{y})]=E[XY]-E[X]E[Y]$$

**Note**: Kovarian antara suatu variabel dengan dirinya sendiri ($Cov[x,x]$) disebut *varians* ($V_{X}(x)$), dan akar dari varians disebut *standar deviasi* ($\sigma_{x}$).

> [!NOTE] Kovarians Multivariat
> untuk variabel acak multivariat $X$ dan $Y$ dengan $x \in \mathbb{R}^D$ dan $y \in \mathbb{R}^E$ maka: $$
Cov[x,y]=E[xy^T]-E[x]E[y]^T=Cov[y,x]^T \in \mathbb{R}^{D\times E}$$

> [!NOTE] Korelasi
> $$
corr[x,y]=\frac{Cov[x,y]}{\sigma_{x}\sigma_{y}} \in [-1,1]$$

Korelasi menunjukkan hubungan antara dua variabel, jika nilai korelasi mendekati $1$ maka kedua variabel mempunyai *korelasi positif* (jika $x$ meningkat $y$ meningkat dan sebaliknya), jika nilai korelasi mendekati $-1$ maka kedua variabel mempunyai *korelasi negatif* (jika $x$ meningkat $y$ menurun dan sebaliknya), jika korelasi bernilai $0$ maka kedua variabel tidak saling berhubungan.
## 6.4.2 Empirical Means and Covariances
Dalam praktik, kita jarang tahu data distribusi populasi/penuh, melainkan data sampel/empiris.
Dalam kasus ini, maka mean adalah:
$$
\bar{x}:=\frac{1}{N}\sum_{n=1}^Nx_{n}
$$
di mana $x_{n} \in \mathbb{R}^D$, dan korelasinya adalah:
$$
\Sigma:=\frac{1}{N}\sum _{n=1}^N(x_{n}-\bar{x})(x_{n}-\bar{x})^T \in \mathbb{R}^{D\times D}
$$
## 6.4.3 Three Expressions for the Variance
- $\mathrm{Var}[X] = \mathbb{E}[(X - \mathbb{E}[X])^2]$
- $\mathrm{Var}[X] = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$
- $\mathrm{Var}[X] = \mathrm{Cov}[X,X]$
## 6.4.4 Sums and Transformations of Random Variables
- $E[aX+b]=aE[X]+b$
- $Var[aX+b]=a^2Var[X]$
## 6.4.5 Statistical Independence
Dua variabel acak $X,Y$ disebut independen secara statistik jika dan hanya jika:
$$
p(x,y)=p(x)p(y)
$$
Jika $X,Y$ independen, maka:
- $p(y|x)=p(y)$
- $p(x|y)=p(x)$
- $V_{X,Y}[x+y]=V_{X}[x]+V_{Y}[y]$
- $Cov_{X,Y}[x,y]=0$
**Note**: poin terakhir tidak berlaku sebaliknya.
## 6.4.6 Inner Products of Random Variables
Kita tahu bahwa untuk dua variabel acak yang tidak berkorelasi maka:
$$
V[X+Y]=V[X]+V[Y]
$$
![[Pasted image 20250925141925.png]]
$$
\begin{align}
\left< X,Y \right> & :=Cov[x,y]  \\
\lVert X \rVert & =\sqrt{ Cov[x,x] }=\sqrt{ V[x] }=\sigma_{x}  \\
\cos \theta & =\frac{\left< X,Y \right>}{\lVert X \rVert \lVert Y \rVert  } = \frac{Cov[x,y]}{\sigma _{x}\sigma_{y}}
\end{align}
$$
# 6.5 Gaussian Distribution (Normal Distribution)

> [!NOTE] Distribusi Gaussian Univariat
> Suatu variabel acak kontinu $X \in \mathbb{R}$ dikatakan mengikuti *distribusi Gaussian* dengan mean $\mu$ dan varians $\sigma^2$ dinotasikan $X \sim \mathcal{N}(\mu,\sigma^2)$ jika pdf-nya berbentuk: $$
p(x)=\frac{1}{\sqrt{ 2\pi \sigma^2 }}\exp \left( - \frac{(x-\mu)^2}{2\sigma^2} \right) $$

> [!NOTE] Distribusi Gaussian Multivariat
> Untuk vektor acak $\mathbf{x} \in \mathbb{R}^D$, distribusi gaussian didefiniskan dengan mean vektor $\mu$ dan matriks kovarians $\Sigma$ dinotasikan $x \sim \mathcal{N(\mu,\Sigma)}$ jika pdf-nya: $$
p(x)=\left( 2\pi \right)^{-\frac{D}{2}}|\Sigma|^{-\frac{1}{2}}\exp-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu)$$

Grafik dari distribusi gaussian membentuk lonceng dengan sebaran data simetris terhadap $\mu$.
![[Pasted image 20250925174903.png]]
## 6.5.1 Marginal dan Kondisional dari Gaussian juga Gaussian
Misal $X$ dan $Y$ dalah variabel acak multivariat, kita dapat menulis gaussian dalam bentuk sebagai berikut:
$$
p(x,y)=\mathcal{N}\left( \begin{bmatrix}
\mu_{x} \\
\mu_{y}
\end{bmatrix}, \begin{bmatrix}
\Sigma_{xx} & \Sigma_{xy} \\
\Sigma_{yx}  & \Sigma_{yy}
\end{bmatrix} \right)
$$
distribusi kondisional $p(x|y)$ juga gaussian, dengan:
$$
\begin{align}
p(x|y) & =\mathcal{N}\left( \mu_{x|y},\Sigma_{x|y} \right),\ \text{dengan:} \\
\mu_{x|y} & =\mu_{x}+\Sigma_{xy}\Sigma_{yy}^{-1}(y-\mu_{y}) \\
\Sigma_{x|y} & = \Sigma_{xx}+\Sigma_{xy}\Sigma_{yy}^{-1}\Sigma_{yx}
\end{align}
$$
dan distribusi marginal $p(x)$ diberikan:
$$
p(x)=\int p(x,y)dy=\mathcal{N}(x|\mu_{x},\Sigma_{xx})
$$
### Contoh 4: Marginal & Kondisional Gaussian
Untuk suatu distribusi Gaussian bivariate

$$p(\mathbf{x}) = \mathcal{N}\Big(\begin{bmatrix}0 \\ 2\end{bmatrix},\; \begin{bmatrix}0.3 & -1 \\ -1 & 5\end{bmatrix}\Big),\qquad \mathbf{x} = \begin{bmatrix}x_1 \\ x_2\end{bmatrix}$$.

Akan dihitung:
**(a)** Distribusi kondisional $p(x_1\mid x_2=-1)$.  
**(b)** Distribusi marginal $p(x_1)$.

Partisi mean dan kovarians sesuai variabel:

$$\boldsymbol{\mu} = \begin{bmatrix}\mu_1 \\ \mu_2\end{bmatrix} = \begin{bmatrix}0 \\ 2\end{bmatrix},\qquad
\Sigma = \begin{bmatrix}\Sigma_{11} & \Sigma_{12} \\ \Sigma_{21} & \Sigma_{22}\end{bmatrix} = \begin{bmatrix}0.3 & -1 \\ -1 & 5\end{bmatrix}.$$
dengan $|\Sigma| = 0.3\cdot5 - (-1)^2 = 1.5 - 1 = 0.5 > 0$

**(a) Kondisional: $p(x_1\mid x_2 = -1)$**
Kita masukkan $b = -1$.
- Hitung $\Sigma_{22}^{-1} = 1 / 5 = 0.2.$
- Mean kondisional:
$$\mu_{1|2} = 0 + (-1) \cdot 0.2 \cdot (-1 - 2) = (-0.2) \cdot (-3) = 0.6.$$
- Varians kondisional:
$$\Sigma_{1|2} = 0.3 - (-1) \cdot 0.2 \cdot (-1) = 0.3 - 0.2 = 0.1.$$
Sehingga
$$\boxed{\;p(x_1\mid x_2=-1) = \mathcal{N}(x_1\mid 0.6,\;0.1)\;}$$
**Interpretasi singkat:** mengetahui $x_2=-1$ menggeser mean dari 0 menjadi 0.6 dan mengecilkan varians dari 0.3 menjadi 0.1 — yaitu ketidakpastian mengenai $x_1$ berkurang dan pusat tebakan bergeser sesuai korelasi negatif di kovarians.

**(b) Marginal: $p(x_1)$**
Untuk marginal cukup ambil komponen mean dan varians yang sesuai:
$$\boxed{\;p(x_1) = \mathcal{N}(x_1\mid 0,\;0.3)\;}$$
**Catatan:** varians marginal (0.3) lebih besar daripada varians kondisional (0.1) — ini sesuai: informasi tambahan tentang $x_2$ menurunkan ketidakpastian terhadap $x_1$.
# 6.6 Conjugacy and the Exponential Family
## 6.6.1 Conjugacy
Dalam Bayesian inference:
$$
  p(\theta | \mathcal{D}) \propto p(\mathcal{D} | \theta) \, p(\theta).
  $$

Jika prior $p(\theta)$ dan likelihood $p(\mathcal{D}|\theta)$ dipilih dengan tepat, maka posterior $p(\theta|\mathcal{D})$ berada dalam keluarga distribusi yang sama dengan prior. Disebut conjugate prior.

Contohnya jika kita mempunyai distribusi dengan Likelihood: $X \sim \text{Bernoulli}(\theta)$, Prior: $\theta \sim \text{Beta}(\alpha, \beta)$.  Maka Posterior tetap Beta dengan parameter diperbarui:
$$
  \theta | \mathcal{D} \sim \text{Beta}\!\big(\alpha + \text{jumlah sukses}, \; \beta + \text{jumlah gagal}\big).
  $$
*Intuisi*: conjugacy membuat update distribusi seperti menambahkan catatan baru ke parameter prior.
## 6.6.2 Sufficient Statistics

> [!NOTE] Sufficient Statistics
> Fungsi dari data $T(\mathcal{D})$ disebut *sufficient statistic* untuk parameter $\theta$ jika: $$
  p(\mathcal{D} | \theta) = g(\mathcal{D}) \, h(T(\mathcal{D}), \theta),$$
  sehingga semua informasi tentang $\theta$ dalam data dapat diringkas hanya melalui $T(\mathcal{D})$.

Contoh pada distribusi normal dengan varian diketahui maka sufficient statisticnya adalah rata-rata data.  Lalu pada distribusi Bernoulli maka sufficient statisticnya jumlah sukses.
## 6.6.3 Exponential Family
Banyak distribusi populer bisa ditulis dalam bentuk *Exponential Family*:
$$
p(x|\theta) = h(x) \exp\!\Big( \eta(\theta)^{\top} T(x) - A(\eta(\theta)) \Big),
$$

dengan:
- $h(x)$: base measure  
- $T(x)$: sufficient statistics  
- $\eta(\theta)$: natural parameter  
- $A(\eta)$: log-partition function (normalizer)
# 6.7 Change of Variables / Inverse Transform

## 6.7.1 Distribution Function Technique
Teknik distribution function bertumpu pada sifat cumulative distribution function (CDF). Misalkan $X$ adalah variabel acak dengan distribusi yang diketahui, dan kita definisikan variabel acak baru $Y = g(X)$ dengan $g$ fungsi monoton. Distribusi $Y$ dapat diperoleh dengan mendefinisikan CDF dari $Y$ sebagai
$$
F_Y(y) = P(Y \leq y) = P(g(X) \leq y).
$$
Dari bentuk ini, fungsi densitas probabilitas (pdf) $f_Y(y)$ diperoleh dengan diferensiasi terhadap $y$:
$$
f_Y(y) = \frac{d}{dy}F_Y(y).
$$

### Contoh 5: Distribution Function Technique
Misalkan $X \sim U(0,1)$ dengan pdf $f_X(x) = 1$ untuk $0 \leq x \leq 1$. Definisikan $Y = X^2$. Untuk memperoleh distribusi $Y$, kita gunakan teknik distribution function. Pertama kita hitung CDF:
$$
F_Y(y) = P(Y \leq y) = P(X^2 \leq y) = P(X \leq \sqrt{y}).
$$
Karena $X$ seragam pada $(0,1)$, maka $F_Y(y) = \sqrt{y}$ untuk $0 \leq y \leq 1$. Diferensiasi terhadap $y$ menghasilkan pdf:
$$
f_Y(y) = \frac{d}{dy}F_Y(y) = \frac{1}{2\sqrt{y}}, \quad 0 \leq y \leq 1.
$$

## 6.7.2 Change of Variables
Pendekatan kedua adalah melalui transformasi langsung pada pdf menggunakan aturan change of variables. Misalkan $Y = g(X)$ dengan $g$ invertibel dan terdiferensialkan. Maka pdf dari $Y$ adalah
$$
f_Y(y) = f_X(g^{-1}(y)) \cdot \left| \frac{d}{dy}g^{-1}(y) \right|.
$$
Untuk kasus multivariat $\mathbf{Y} = g(\mathbf{X})$, hasilnya menjadi
$$
f_{\mathbf{Y}}(\mathbf{y}) = f_{\mathbf{X}}(g^{-1}(\mathbf{y})) \cdot \left| \det J_{g^{-1}}(\mathbf{y}) \right|,
$$
dengan $J_{g^{-1}}$ adalah Jacobian dari fungsi invers $g^{-1}$.

### Contoh 6: Change of Variables
Misalkan $X \sim U(0,1)$ dengan pdf $f_X(x) = 1$ untuk $0 \leq x \leq 1$. Definisikan $Y = -\ln(X)$. Karena $X = e^{-Y}$, kita dapatkan
$$
\frac{d}{dy}x = \frac{d}{dy}e^{-y} = -e^{-y}.
$$
Maka pdf dari $Y$ adalah
$$
f_Y(y) = f_X(e^{-y}) \cdot | -e^{-y} | = 1 \cdot e^{-y} = e^{-y}, \quad y \geq 0.
$$
Dengan demikian, $Y$ berdistribusi eksponensial dengan parameter 1.
