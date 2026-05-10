---
title: "posloupnosti,rady.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/ØU1/posloupnosti,rady.pdf"
date: 2008-08-24
type: PDF (text-based)
---

PÍKLADY K 1.PP Z U1/2
II. Napi²te a dokaºte hypotézu o nejv¥t²ím spole£ném d¥liteli v²ech hodnot (pro v²echna n ∈ N)
daného výrazu:

I. Danou kone£nou posloupnost ur£ete vzorcem
pro n-tý £len (analyticky) a rekurentn¥:
1. {an }5n=1 = {0, 0, 3, 20, 115}

1. n5 − n

2. {bn }5n=1 = {3, 7, 13, 21, 31}

2. 42n−1 + 3n+1

3. {cn }5n=1 = {2, 8, 26, 80, 242}

3. 7 + 72 + 73 + · · · + 74n

4. {dn }5n=1 = {−2, 5, −17, 65, −257}

4. n7 + n8n + 12n
IV. Ur£ete sou£ty následujících °ad:

III. Posloupnosti dané rekurentn¥ vyjád°ete vzorcem pro n-tý £len (analyticky).
p
1. a1 = 1, an+1 = 2a2n + 1

1. 7 + 77 + 777 + · · · + 7| . .{z
. 777}
n

Pn

1
i=1 (3i−2)(3i+1)

an
2. a1 = 9, an+1 = 2(n+2)

2.

3. b1 = i, b2 = 1, bn+2 = bn+1 + bn

3
5
7
2n+1
3. 1.2.3
+ 2.3.4
+ 3.4.5
+ · · · + n(n+1)(n+2)

4. c1 = c2 = 2, cn+2 = cn+1 c2n
p
5. d1 = 1, d2 = 6, dn+2 = dn+1 dn

4. 1.3 + 2.5 + · · · + n(2n + 1)
¡¢
¡¢
¡
¢
5. 1 02 + 3 12 + · · · + (2n − 1) n−1
2

Výsledky:
I. kone£ná posloupnost
1. {an }5n=1 = {n! − n}, nap°. a1 = 0, an = n!n − 1 + an−1 ; 2. {bn }5n=1 = {n2 + n + 1}, nap°. b1 = 3, bn =
bn−1 + 2n; 3. {cn }5n=1 = { 12 (3n−1 + 1)}, nap°. c1 = 1, cn+1 = 3cn − 1; 4. {dn }5n=1 = {(−1)n (4n−1 + 1)},
nap°. d1 = −2, dn+1 = 3.(−4)n−1 − dn
II. nejv¥t²í spole£ný d¥litel
1. D = 30; 2. D = 13; 3. D = 2800; 4. D = 7
III. analytické vyjád°ení posloupnosti dané rekurentn¥
h
i ³ √ ´n
√
√ n
5
1+ 5
9
1−i
1
∞
∞
1. {an }∞
+
n=1 = { 2 − 1}; 2. {an }n=1 = { 2n−2 (n+1)! }; 3. {bn }n=1 = { 2 − 10 (1 − 3i)
2
h
i ³ √ ´n
√
n+1
1 n
1
1 n−2
5
1− 5
1−i
]
]
3 [2 +(−1)
3 [2+(− 2 )
}; 4. {cn }∞
}; 5. {dn }∞
};
n=1 = {2
n=1 = {6
2 + 10 (1 − 3i)
2
IV. sou£et
£ °adyn
¤
1/2
3/2
n
5
1
1. s = 79 10
9 (10 − 1) − n ; 2. s = 3n+1 ; 3. s = 4 − n+1 − n+2 ; 4. s = 6 n(n + 1)(4n + 5);
n
5. s = 12 (n − 1)(n − 2)(3n + 1)

P°íklady vybrány z:
• Hecht, T.  Sklenáriková, Z.: Metódy rie²enia matematických úloh, SPN Bratislava 1992.
• Herman, J.  Ku£era, R.  im²a, J.: Metody °e²ení matematických úloh I., SPN Praha 1990.
• Larson, L. C.: Metódy rie²enia matematických problémov, Alfa Bratislava 1990.
• Odvárko, O. a kol.: Metody °e²ení matematických úloh, SPN Praha 1990.
• Polák, J.: St°edo²kolská matematika v úlohách II, Prometheus Praha 1999.

mernesto@kmt.zcu.cz

Za upozorn¥ní na chyby p°edem d¥kuji.

1

EENÍ
I.
(1) {an }5n=1 = {0, 0, 3, 20, 115}

hypotéza:

a1 = 0
a2 = 0
a3 = 3 = 3.1 = 3(2 − 1)
a4 = 20 = 4.5 = 4(6 − 1) = 4(2.3 − 1)

{an }5n=1 = {n[(n − 1)! − 1]} = {n! − n}

⇒
ov¥°ení:

a1 = 1! − 1 = 0 X
a2 = 2! − 2 = 0 X
..
.
a5 = 5! − 5 = 5(24 − 1) = 115 X

a5 = 115 = 5.23 = 5(24 − 1) =
= 5(6.4 − 1) = 5(2.3.4 − 1)

analytické vyjád°ení (vzorec pro n-tý £len)

{an }5n=1 = {n! − n}
rekurentní vyjád°ení:
an+1 − an = (n + 1)! − (n + 1) − n! + n = n!n − 1

⇒ a1 = 0, an+1 = an + n!n − 1

(2) {bn }5n=1 = {3, 7, 13, 21, 31}
analytické vyjád°ení:

b1 = 3
b2 = 7 = 3 + 4 = b1 + 2.2
b3 = 13 = 7 + 6 = b2 + 2.3
b4 = 21 = 13 + 8 = b3 + 2.4
b5 = 31 = 21 + 10 = b4 + 2.5

b1 = 3
b2 = b1 + 2.2
b3 = b2 + 2.3
..
.

bn = bn−1 + 2.n

⇓
rekurentní vyjád°ení:

bn +

b1 = 3, bn+1 = bn + 2n

n−1
X
i=1

bi =

n−1
X

bi + 1 + 2[1 + 2 + 3 + · · · + n]

i=1

n
bn = 1 + 2 (n + 1)
2
b n = n2 + n + 1

{bn }5n=1 = {n2 + n + 1}

(3) {cn }5n=1 = {2, 8, 26, 80, 242}

c1 = 2
c2 = 8 = 9 − 1
c3 = 26 = 27 − 1
c4 = 80 = 81 − 1

analytické vyjád°ení:

⇒

{cn }5n=1 = 3n − 1

c5 = 242 = 243 − 1
rekurentní vyjád°ení:
cn+1 − cn = 3n+1 − 1 − 3n + 1 = 2.3n

⇒

c1 = 2, cn+1 = 2.3n + cn

2

(4) {dn }5n=1 = {−2, 5, −17, 65, −257}

d1 = −2
analytické vyjád°ení:

d2 = 5 = 22 + 1
⇒

4

d3 = −17 = −2 − 1
6

{dn }5n=1 = (−1)n 22·(n−1) +(−1)n = (−1)n (4n−1 + 1)

d4 = 65 = 2 + 1
d5 = −257 = −28 − 1
rekurentní vyjád°ení:
dn+1 +dn = (−1)n+1 (4n +1)+(−1)n (4n−1 +1) = (−1)n 4n−1 (−4+3) ⇒ d1 = −2, dn+1 = (−1)n−1 4n−1 .3 − dn

II.
(1) f (n) = n5 − n
1
0

n
f (n)

2
30

3
240

hypotéza: D = 30
d·kaz: ∀n ∈ N D|f (n)
5

zbývá dokázat: ∀n ∈ N

4

2

2

f (n) = n − n = n(n − 1) = n(n − 1)(n + 1) =
= (n − 1)n(n + 1)(n2 + 1)
Poslední sou£in obsahuje 3 po sob¥ jdoucí £ísla, a
tedy 3|f (n). Mezi nimi jsou 2 po sob¥ jdoucí £ísla,
proto 2|f (n), a tak 6|f (n).

5|f (n)

MI:
1. n = 1 f (1) = 1 − 1 = 0, 5|f (1) X
2. n = k f (k) = k 5 − k IP : 5|f (k)
3. n = k+1 f (k+1) = (k+1)5 −(k+1) 5|? f (k+1)

f (k + 1) = (k + 1)5 − (k + 1) = k 5 + 1 − k − 1 + 5k 4 +
IP

10k 3 + 10k 2 + 5k = k 5 − k + 5A = 5B + 5A
⇒ 5|[(k + 1)5 − (k + 1)]

Nejv¥t²ím spole£ným d¥litelem v²ech hodnot f (n), n ∈ N, je 30.
(2) f (n) = 42n−1 + 3n+1

n
f (n)

1
13

2
91

3
1150

f (k + 1) = 42k+1 + 3k+2 = 42 .42k−1 + 3.3k+1 =

hypotéza: D = 13
d·kaz: ∀n ∈ N D|f (n)

= 42 (42k−1 + 3k+1 ) − 42 .3k+1 + 3.3k+1

MI:
1. n = 1 f (1) = 4 + 9 = 13, 13|f (1) X
2. n = k f (k) = 42k−1 + 3k+1 IP : 13|f (k)
3. n = k + 1 f (k + 1) = 42k+1 + 3k+2 13|? f (k + 1)

IP

= 16.13A − 3k+1 (16 − 3)

= 16.13A − 3k+1 .13
⇒ 13|[42k+1 + 3k+2 ]

Nejv¥t²ím spole£ným d¥litelem v²ech hodnot f (n), n ∈ N, je 13.

3

(3) f (n) = 7 + 72 + 73 + · · · + 74n

n
f (n)

1
2.2800

2
2800.2402

f (k + 1) = 7 + 72 + · · · + 74(k+1) =

hypotéza: D = 2800
d·kaz: ∀n ∈ N D|f (n)

= 7 + 72 + · · · + 74k + 74k+1 + 74k+2 + 74k+3 + 74k+4 =

MI:
1. n = 1 f (1) = 7 + 72 + 73 + 74 = 2800
2800|f (1) X
2. n = k f (k) = 7 + 72 + · · · + 74k
IP: 2800|f (k)
3. n = k + 1
f (k + 1) = 7 + 72 + · · · + 74(k+1)
13|? f (k + 1)

IP

= 2800A + 74k+1 + 74k+2 + 74k+3 + 74k+4 =

= 2800A + 74k (7 + 72 + 73 + 74 ) = 2800A + 74k 2800
⇒ 2800|[7 + 72 + · · · + 74(k+1) ]

Nejv¥t²ím spole£ným d¥litelem v²ech hodnot f (n), n ∈ N, je 2800.
(4) f (n) = n7 + n.8n + 12n

n
f (n)

1
21

2
280

3
3759

hypotéza: D = 7
d·kaz: ∀n ∈ N D|f (n)

f (k + 1) = (k + 1)7 + (k + 1).8k+1 + 12(k + 1)

MI:
1. n = 1 f (1) = 1 + 8 + 12 = 21, 7|f (1) X
2. n = k f (k) = k 7 + k.8k + 12k
IP : 7|f (k)
3. n = k + 1
f (k + 1) = (k + 1)7 + (k + 1).8k+1 + 12(k + 1)
7|? f (k + 1)

= k 7 + 1 + 7k 6 + 21k 5 + 35k 4 + 35k 3 + 21k 2 + 7k+
+ k.8k 8 + 8k+1 + 12k + 12
= k 7 + k.8k + 12k + 1 + 7A + 7.8k + 8k+1 + 12
IP

= 7B + 7A + 8k+1 + 13

7|? 8k+1 + 13

MI:
1. k = 1 f (1) = 82 + 13 = 77, 7|f (1) X
2. k = b f (b) = 8b+1 + 13 IP : 7|f (b)
3. k = b + 1 f (b + 1) = 8b+2 + 13 7|? f (b + 1)
IP

f (b + 1) = 8b+2 + 13 = 8b+1 (1 + 7) + 13 = 7A + 7.8b+1

⇒ 7|[8b+2 + 13]
⇒ 7|[(k + 1)7 + (k + 1).8k+1 + 12(k + 1)]

Nejv¥t²ím spole£ným d¥litelem v²ech hodnot f (n), n ∈ N, je 7.

4

III.
(1) a1 = 1, an+1 =

p

2a2n + 1
√ n
hypotéza: {an }∞
n=1 = { 2 − 1}
d·kaz:
MI:
1. n = 1 a1 = 21 − 1√= 1, a1 = 1 X
2. n = k IP : ak = 2k − 1
? √
3. n = k + 1 ak+1 = 2k+1 − 1
p
√
IP p
ak+1 = 2a2k + 1 = 2.(2k − 1) + 1 = 2k+1 − 1

a1 = 1
p
√
√
a2 = 2.1 + 1 = 3 = 22 − 1
p
√
√
a3 = 2.3 + 1 = 7 = 23 − 1
p
√
√
a4 = 2.7 + 1 = 15 = 24 − 1
p
√
√
a5 = 2.15 + 1 = 31 = 25 − 1
..
.

√
n
{an }∞
n=1 = { 2 − 1}

an
(2) a1 = 9, an+1 = 2(n+2)

a1 = 9
91
a2 =
23
91 1
a3 =
2 3 2.4
9 1 1
a4 =
2 2.3.4 2.5
91 1
a5 =
4 5! 2.6
..
.

1
9
hypotéza: {an }∞
n=1 = { 2n−2 (n+1)! }
d·kaz:
MI:
9 1
1. n = 1 a1 = 2−1
2! = 9, a1 = 9 X
9
1
2. n = k IP : ak = 2k−2
(k+1)!
?

1
9
ak+1 = 2k−1
(k+2)!

3. n = k + 1

ak+1 =

ak
1
1
9
1
IP 9
= k−2
= k−1
2(k + 2)
2
(k + 1)! 2(k + 2)
2
(k + 2)!

½
{an }∞
n=1 =

9

1
n−2
2
(n + 1)!

¾

(3) b1 = i, b2 = 1, bn+2 = bn+1 + bn
P°edpokládejme, ºe rekurentnímu p°edpisu bn+2 = bn+1 +bn vyhovuje geometrická posloupnost s kvocientem q . Potom

q n+2 = q n+1 + q n
q2 = q + 1
1
2

q1,2 = (1 ±
(
{bn } =

λ1

Ã

√

5)

Ã
√ !n
√ !n )
1+ 5
1− 5
+ λ2
2
2

√
√
√
λ1 12 (1 +
5) + λ2 12 (1 −√ 5) = i |.2(1 − 5)
√
λ1 14 (1 + 5)2 + λ2 14 (1 − 5)2 = 1
|.4
√ 2
√
λ1√
(−4) + λ2 (1 − √5) = 2i(1 − 5) |.(−1) + ←λ1 (1 + 5)2 + λ2 (1 − 5)2 = 4

5

√
λ1 (10 + 2 5)
λ1
λ1
√
λ2 ( 5 − 1)

("
{bn }∞
n=1 =

√
= 4 − 2i(1
− 5)
√
√
5) 5− 5
√
√
= 2−i(1−
5+ 5
5− 5
=

λ2

=
..
.
=

λ2

=

√
5
1−i
2 − 10 (1 − 3i)
√
√
2−i(1− 5)
√
(1 + 5) − 2i
5+ 5
√
√
√
3+ 5−2i( 5+2) 5− 5
√
√
5+√ 5
5− 5
5
1−i
2 + 10 (1 − 3i)

#Ã
#Ã
√
√
√ !n "
√ !n )
5
1+ 5
1−i
5
1− 5
1−i
−
(1 − 3i)
+
+
(1 − 3i)
2
10
2
2
10
2

(4) c1 = c2 = 2, cn+2 = cn+1 c2n

c1 = 1
c2 = 2

γn
∞
Patrn¥ platí, ºe {cn }∞
n=1 = {2 }, kde {γn }n=1 je posloupnost

γ1 = 1

c3 = 2.22 = 23

γ2 = 1
γ3 = 3
γ4 = 5 = γ3 + 2
γ5 = 11 = γ4 + 6 = γ4 + 2γ3
γ6 = 21 = γ5 + 10 = γ5 + 2γ4
..
.

c4 = 23 .22 = 25
c5 = 25 .26 = 211
c6 = 211 .210 = 221
..
.

γn
hypotéza: {cn }∞
n=1 = {2 }, kde γ1 = γ2 = 1 a γn = γn−1 + 2γn−2
d·kaz:
MI:
1. c1 = 2γ1 = 21 = 2 X
c2 = 2γ2 = 21 = 2 X
2. IP: ck = 2γk
?
IP
3. ck+1 = 2γk+1
ck+1 = ck .c2k−1 = 2γk .(2γk−1 )2 = 2γk +2γk−1 = 2γk+1

Nyní je pot°eba ur£it posloupnost {γn }∞
n=1 analyticky:

q n+2 = q n+1 + q n

2λ1 − λ2 = 1
4λ1 + λ2 = 1
λ1 = 13
λ2 = − 13

2

q =q+2
q1,2 = −1; 2
n
n
{γn }∞
n=1 = {λ1 2 + λ2 (−1) }

1 n
n+1
{γn }∞
)}
n=1 = { (2 + (−1)
3
o
n 1 n
n+1
)
3 (2 +(−1)
{cn }∞
n=1 = 2

6

(5) d1 = 1, d2 = 6, dn+2 =

p

dn+1 dn

d1 = 1
d2 = 6
√
1
d3 = 1.6 = 6 2
q
√
1 1
3
d4 = 6 6 = 6(1+ 2 ) 2 = 6 4
r q
√
√
1
3 1
5
d5 =
6 6 6 = 6( 2 + 4 ) 2 = 6 8
s
r q
q
√
√
√
3
5 1
11
6 6
6 6 6 = 6( 4 + 8 ) 2 = 6 16
d6 =

Z n¥kolika prvních £len· dané posloupnosti je z°ejmé, ºe
δn
∞
∞
2n−2 }
{dn }∞
n=1 = {6
n=1 , kde {δn }n=1 je posloupnost, pro kterou
platí

δ1 = 0
δ2 = 1 = 2δ1 + 1
δ3 = 1 = 2δ2 − 1
δ4 = 3 = 2δ3 + 1
δ5 = 5 = 2δ4 − 1
δ6 = 11 = 2δ5 + 1
..
.
δn = 2δn−1 + (−1)n

..
.

δ1 = 0
1
2
1
| 2
2
1
| 3
2

δ2 = 2δ1 + 1

|

δ3 = 2δ2 − 1
δ4 = 2δ3 + 1
..
.

δn = 2δn−1 + (−1)n
δ1 +

1
| n−1
2

δ2
δ3
δn−1
δn
δ2
δ3
δn−1
1 1 1
(−1)n
+
+ · · · + n−2 + n−1 = δ1 +
+
+ · · · + n−2 + − + + · · · + n−1
2
4
2
2
2
4
2
2 ¶4 8
2
µ
(−1)n
1 1 1
n−1
− + + · · · + n−1
δn = 2
2 4 8
2
δn = 2n−1
δn

2n−2 } = {6
hypotéza: {dn }∞
n=1 = {6

2n−1 +(−1)n
3.2n−2

1 1 − (− 21 )n−1
2n−1 + (−1)n
=
1
2 1 − (− 2 )
3
1

(−1)n−2

} = {6 3 (2+ 2n−2

)

1

1 n−2

} = {6 3 [2+(− 2 )

1
1 n−2
]
3 [2+(− 2 )

]

}

d·kaz: ∀n ∈ N dn = 6
MI:
1. n = 1 d1 = 60 = 1, d1 = 1 X
1
n = 2 d2 = 6 3 [2+2] = 6, d2 = 6 X
1
1 k−2
2. n = k IP : dk = 6 3 [2+(− 2 ) ]
1 k−1
1
?
3. n = k + 1 dk+1 = 6 3 [2+(− 2 ) ]
i 21
h
p
1 k−2
1
1 k−3
1 1
1 k−2
1 k−3
1 1
1 k−3
1
IP 1
dk+1 = dk dk−1 = 6 3 [2+(− 2 ) ] .6 3 [2+(− 2 ) ] = 6 2 { 3 [2+(− 2 ) +2+(− 2 ) ]} = 6 2 3 [4+(− 2 ) (− 2 +1)] =
1

1 k−3 1
4]

= 6 3 [2+(− 2 )

1

1 k−1

= 6 3 [2+(− 2 )

]
1

1 n−2

3 [2+(− 2 )
{dn }∞
n=1 = {6

7

]

}

IV.
(1) 7 + 77 + 777 + · · · + 7
. 777}
| . .{z
n

s = 7 + (70 + 7) + (700 + 70 + 7) + (7 000 + 700 + 70 + 7) + · · · + (7.10n + · · · + 70 + 7) =
= (7 + 70 + 700 + 7 000 · · · + 7.10n ) + (7 + 70 + 700 + · · · + 7.10n−1 ) + (7 + 70 + · · · + 7.10n−2 )+
+ (7 + · · · + 7.10n−3 ) + · · · + (7 + 70) + 7 =
10n−1 − 1
10n−2 − 1
10n−3 − 1
102 − 1
10 − 1
10n − 1
+7
+7
+7
+ ··· + 7
+7
=
10 − 1
10 − 1
10 − 1
10 − 1
10 − 1
10 − 1
= 79 [10n + 10n−1 + 10n−2 + · · · + 102 + 10 − (1 + · · · + 1)] =
| {z }
n
·
¸
7
10n − 1
=
10
−n
9
9

=7

(2)

Pn

1
i=1 (3i−2)(3i+1)

s1 =

1
4

n
3n + 1
n
d·kaz: ∀n ∈ N sn =
3n + 1
MI:
1
1
1. n = 1 s1 = 3+1
= 14 , s1 = 1.4
= 41
k
2. n = k IP : sk = 3k+1
hypotéza: s = sn =

1
2
=
4.7
7
1
3
s3 = s2 +
=
7.10
10
1
4
s4 = s3 +
=
10.13
13
..
.
s2 = s1 +

X

?

k+1
sk+1 = 3(k+1)+1

3. n = k + 1

k
1
1
1
IP
=
+
=
[3(k + 1) − 2][3(k + 1) + 1]
3k + 1 (3k + 1)(3k + 4)
3k + 1
1 3k 2 + 3k + k + 1
1 (k + 1)(3k + 1)
k+1
=
=
=
3k + 1
3k + 4
3k + 1
3k + 4
3k + 4

sk+1 = sk +

s=

µ
k+

1
3k + 4

¶

n
3n + 1

2n+1
3
5
7
(3) s = 1.2.3
+ 2.3.4
+ 3.4.5
+ · · · + n(n+1)(n+2)

Rozklad na parciální zlomky:

2n + 1
A
B
C
= +
+
n(n + 1)(n + 2)
n
n+1 n+2
2n + 1 = A(n2 + 3n + 2) + B(n2 + 2n) + C(n2 + n)
A+B+C =0
3A + 2B + C = 2

⇒

2A = 1

⇒

2A + B = 2
1
A=
2

⇒

B = 1, C = −

3
2

¸ ·
¸
·
¸ ·
¸
1/2 1 (−3/2)
1/2
1
(−3/2)
1/2
1
(−3/2)
1/2 1 (−3/2)
+ +
+
+ +
+ ··· +
+ +
+
+
+
=
1
2
3
2
3
4
n−1 n
n+1
n
n+1
n+2
1/2 1 1/2 (−3/2)
1
(−3/2)
5
1/2
3/2
=
+ +
+
+
+
= −
−
1
2
2
n+1
n+1
n+2
4 n+1 n+2
·

s=

8

(4) 1.3 + 2.5 + · · · + n(2n + 1)

ai = i(2i + 1) = 2i(i + 1) − i
Pn
• S1 = i=1 2i(i + 1)
Pn
• S2 = i=1 (−i)

⇒ °adu lze zapsat jako sou£et dvou °ad:

S1 = 2[1(1 + 1) + 2(2 + 1) + 3(3 + 1) + · · · + n(n + 1)] = 2[1.2 + 2.3 + · · · + n(n + 1)] =
·µ ¶ µ ¶
µ
¶¸
µ
¶
2
3
n+1
n+2
+
+ ··· +
=4
=4
2
2
2
3
1
S2 = −1 − 2 − 3 − · · · − n = − n(n + 1)
2
s = S1 + S2 = 4

(n + 2)(n + 1)n(n − 1)! n
n(n + 1)
n
− (n + 1) =
[4(n + 2) − 3] = (n + 1)(4n + 5)
6(n − 1)!
2
6
6

¡ ¢
¡
¢
¡ ¢
(5) 1 02 + 3 12 + · · · + (2n − 1) n−1
2
¡ ¢
¡ ¢ ¡i−1¢
ai = (2i − 1) i−1
= 2i i−1
− 2
2
2
Pn ¡i−1¢
• S1 = 2 i=1 i 2
¡ ¢
Pn
• S2 = i=1 − i−1
2
S1 = 2

¶
µ
¶
n µ
n
n µ ¶
X
X
X
i−1
i(i − 1)!
i
n+1
i
=2
= 3!
= 3!
2
2!(i − 3)!
3
4
i=1
i=1
i=1

S2 = −

¶
n µ
X
i−1
i=1

s = S1 +S2 = 3!

⇒ °adu lze zapsat jako sou£et dvou °ad:

2

µ ¶
n
=−
3

µ
¶ µ ¶
n+1
n
3!
1
n
−
= (n+1)n(n−1)(n−2)− n(n−1)(n−2) =
(n − 1)(n − 2)(3n + 1)
4
3
4!
3!
12

9

