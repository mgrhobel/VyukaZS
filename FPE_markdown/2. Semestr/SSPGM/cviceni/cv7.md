---
title: "cv7.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/cviceni/cv7.txt"
date: 2009-05-10
type: TXT
---

Cviceni SSPGM 7. tyden

1. Napiste a analyzujte program,
potomek po napr. 6 s cekani (sleep(6)) skonci,
rodic zustava v pause().

2. Analyzujte p31.c - ignorovani signalu
- pro argc = 1 neni vyslan signal SIG_IGN
- pro argc <> 1 je vyslan signal SIG_IGN

3. Analyzujte program p30.c - duvod pro zanik potomka
- signal pro zanik potomka nebude ignorovan
- signal pro zanik potomka bude ignorovan

Jak se zachova jadro v obou pripadech k procesum?

4. Napiste program na zachazeni se skupinou procesu
- forknete 8x rodicovsky proces
- lichym procesum (poradove cislo liche) nastavte novou skupinu procesu
- rodicovsky proces po 5 s posle signal SIGINT vsem procesum
puvodni skupiny odesilatele (kam patri i rodic).
Analyzujte procesy.

5. Co se stane, kdyz vysleme signal kill(-1,<signal>)
- odesilatel neni superuzivatel
- odesilatel je superuzivatel

