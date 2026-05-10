---
title: "RS1p_9.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_9.pdf"
date: 2008-08-24
type: PDF (text-based)
---

5 Ekvivalentní realizace přenosové funkce
b0
α realizace)
F ( p) = n
n −1
+ K + a1 ⋅ p + a0

p + an−1 ⋅ p

Definujeme:
x1 ( t ) = y ( t )
x2 ( t ) = y′ ( t )
M
xk ( t ) = y ( k −1) ( t )
M
xn ( t ) = y ( n −1) ( t )

x&1 ( t ) = x2 ( t )

⇒

y ( t ) = x1 ( t )

x&2 ( t ) = x3 ( t )
M
x&n −1 ( t ) = xn ( t )
x&n ( t ) = − a0 x1 ( t ) − a1 x2 ( t ) − K − an−1 xn ( t ) + b0u ( t )
 x&1 ( t )   0
&
 
 x2 ( t )   0
 M = M

 
 M   0
 x& ( t )   − a
 n   0

1
0
M
0
−a1

0
1
M
0
− a2

L
0   x1 ( t )   0 


L
0   x2 ( t )   0 
O
M   M  +  M  u (t )
  

L
1   M  0
L − an −1   xn ( t )  b0 

 x1 ( t ) 


x2 ( t ) 

y ( t ) = [1 0 0 L 0]
+ 0 ⋅ u (t )
 M 


 xn ( t ) 
β realizace)
F( p ) =

b0

p + a n −1 ⋅ p
n

n −1

+ K + a1 ⋅ p + a 0

předpokládejme, že známe kořeny charakteristického polynomu.
λ1 , λ 2 , K , λ n
reálné různé.

1

F( p ) =

Y( p )
U ( p)

=

n
b0
b
1
= n 0
= b0 ⋅ ∑
P( p )
i =1 p − λ i
∑ ( p − λi )

součin koř. činitelů

i =1

Označíme-li
F1( p ) =
F2( p ) =

ε1( p )
ε 2( p )

ε 2( p )
ε 3( p )

=

1
p − λ1

=

1
p − λ2

M

Fn−1( p ) =

(A)

ε n −1( p )
ε n( p )

Fn( p ) =

ε n( p)
n( p )

=

1
p − λ n −1

=

b0
p − λn

ε1( p ) = y ( p )
Můžeme chápat F( p ) jako přenosovou funkci systému, který je sériovým spojením
n-objektů charakterizovaných přenosovými funkcemi Fk ( p ) ; k=1,2,...,n.
F( p ) =
Zpětnou D − transformací (A):
pε1( p ) − λ1ε1( p ) = ε 2

Y( p )
U ( p)

n

= ∑ Fk ( p )
k =1

ε&1 (t ) = λ1ε1 (t ) + ε 2 (t )
ε&2 (t ) = λ2ε 2 (t ) + ε 3 (t )

M
ε&n −1 (t ) = λn −1ε n −1 (t ) + ε n (t )
ε&n (t ) = λnε n (t ) + b0u (t )
y (t ) = ε1 (t )
 • 
 ε1 ( t )   λ 1 0 L 0   ε ( t )   0 
1
 •   1



λ2 1 L 0   ε 2 ( t )   0 
 ε 2 (t )  
 M  = L L L L L  ⋅  M  +  M  u (t )

 
  
 
 •   0 0 L λn −1 1  ε n −1 ( t )   0 
ε n −1 ( t )  
  
 
 •   0 0 L 0 λn   ε n ( t )  bo 
 ε n ( t ) 

2

 ε 1 (t ) 
 ε (t ) 
 2 
y (t ) = [1 0 L 0 0] ⋅  M  + 0 ⋅ u (t )


ε n −1 (t )
 ε n (t ) 
Pokud λi nebudou reálné různé, např. pokud bude některé komplexní, bude struktura
„složitější“.
γ realizace)
b0
Y(p)
b0
F( p) = n
=
=
n −1
p + a n −1p +...+ a1p + a 0 U(p) P( p)

Předpokládejme, že známe kořeny charakteristického polynomu λ1, λ2, … λn – reálné různé
Přenosovou funkci lze rozložit na parciální zlomky

∑

F( p) =

b0
Y ( p)
=
= b0
U( p) P ( p)

i=n

∑
n

n

ri
=
p − λi

Fi ( p)

i= n

kde r i je reziduum funkce F(p), které odpovídá i-tému systému pólu λi
ri =
(vynechá se (λi - λi))

1
( λi − λ1 )(λi − λ2 )...(λi − λi − 1 )(λi − λi + 1 )...(λi − λn )

F(p) lze chápat jako jako paralelní spojení n-objektů popsaných přenosovými funkcemi
ri
⇒µ i.
p − λi
F1 ( p) =

r1
µ1 ( p)
= b0
u( p)
p − λ1

F2 ( p) =

r2
µ 2 ( p)
= b0
u( p)
p − λ2
M

Fn −1 ( p) =
Fn ( p) =

rn −1
µ n −1 ( p)
= b0
u( p)
p − λn −1

rn
µ n ( p)
= b0
u ( p)
p − λn

Realizace:
α)

3

xn

xn −1

xn − 2

an −1

an − 2

an−3

b0

x4

x3

x2

x1 = y

a2

a1

a0

β)
u (t )

ε n −1

ε n (t )

b0

λn −1

λn

ε1 = y

ε2

λ2

y

λ1

γ)
µ1

r1
λ1

µ2

r2

y (t )

λ2
u (t )
b0
µn

rn
λn

5.1 Obecné úvahy k ekvivalenci
Zavedeme jiný vektor stavu x(t ) , (předpokládejme, že existuje regulární matice T taková, že)
x(t ) = ε (t ) = T −1 x(t ) ⇒ x(t ) = T x(t )

4

y

•

x = Ax + Bu
y = Cx + Du

x = T x(t )

T x = AT x + Bu

/⋅ T −1

y = CT x + Du
x = T −1 AT x + T −1 Bu  A = T −1 AT

y = CT x + Du
 B = T −1 B

x = A x + Bu
 C = CT
 D=D
y = C x + Du


5

