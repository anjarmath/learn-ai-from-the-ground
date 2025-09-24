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
### Contoh 1: Permainan Funfair dengan Koin
**Eksperimen:**
- Kita punya sebuah kantong berisi koin USA ($) dan koin UK (£).
- Kita melakukan dua kali pengambilan koin **dengan pengembalian** (_with replacement_).
- Probabilitas mengambil koin USA ($) dalam satu kali undian adalah $0.3$.
- Probabilitas mengambil koin UK ($£$) adalah $0.7$.
$$
Ω={($,$),($,£),(£,$),(£,£)}
$$
Misal kita definisikan $X$ sebagai peubah acak yang menotasikan seberapa banyak munculnya $ pada percobaan, maka:
$$
\begin{align}
X(($,$))=2\\
X(($,£))=1\\
X((£,$))=1\\
X((£,£))=0
\end{align}
$$
Sehingga:
$$
\begin{align}
P(X=2) & =P((\textdollar,\textdollar)) \\
 & =P(\textdollar).P(\textdollar) \\
 & =(0.3)(0.3) = 0.09 \\
P(X=1) & =P((\textdollar,£) \cup (£,\textdollar)) \\
 & = P((\textdollar,£))+P((£,\textdollar)) \\
 & =(0.3)(1-0.3)+(1-0.3)(0.3) = 0.42 \\
P(x=0) & =P((£,£)) \\
 & =(1-0.3)(1-0.3) = 0.49
\end{align}
$$
# 6.2 Discrete and Continuous Probabilities
# 6.3 Sum Rule, Product Rule, and Bayes’ Theorem
# 6.4 Summary Statistics and Independence
# 6.5 Gaussian Distribution
# 6.6 Conjugacy and the Exponential Family
# 6.7 Change of Variables/Inverse Transform