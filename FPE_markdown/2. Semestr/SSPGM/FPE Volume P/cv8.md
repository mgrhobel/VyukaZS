---
title: "cv8.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/cv8.txt"
date: 2006-10-03
type: TXT
---

1. Dokonceni predchazejiciho

2. Napiste program pro soubeh zachytavani signalu SIGUSR1, SIGUSR2
   mezi procesy Rodic (master), potomek (slave).
 
Scenar viz obrcv8.gif

obsluha signalu SIGUSR1:
void master ()
{signal(SIGUSR1,master)}

obsluha signalu SIGUSR2:
void slave()
{signal(SIGUSR2,slave); kill(mpid,SIGUSR1)}
mpid - cislo procesu master

 - Analyzujte synchronizaci procesu pri zmene nastaveni priority
   procesu master a urcete kriticke misto preruseni synchronizace.

3. Napiste program, kde budete snizovat ukazatel DS (datovy segment)
   a zjistete, kdy dojde k poruseni segmentu (Segmentation fault),
   resp. k vyslani signalu SIGSEGV.
   Na tento stav reagujte napr. vypisem nastaleho stavu, obsluhou
   SIGSEGV.
   Urcete velikost stranky v alokovane pameti OP a vysvetlete viz
   tez bod c. 5 mechanismus strankovani na zadost

4. Napiste program na zjisteni obsahu nove alokovane casti DS.

   - alokujte (zvetsete DS)
   - zvetsenou oblast zaplnte predem urcenymi znaky
   - disalokujte danou oblast
   - opetne ji alokujte
   - vypiste obsah alokovane casti DS

5. Analyzujte program p34.c a zduvodnete vypisovane pocty pruchodu
   pro ruzne zadavana (argv[1]) zvetseni DS (posun)
   -
   a) hodnoty posunu zadavejte < nez velikost stranky OP
   b) hodnoty posunu zadavejte = velikost stranky OP
   c) hodnoty posunu zadavejte > velikost stranky OP
 
  - pro pripady a) b) c)
    - 1. zadavejte hodnoty v nasobcich <2 na n>
    - 2. mimo nasobky <2 na n>
  
  Na prikladu vysvetlete mechanismus strankovani na zadost,
  prepinani stranek, pocty korektnich (do poruseni segmentace)
  zapisu do postupne alokovaneho DS (posun).
  Vysledky odevzdejte v pisemne forme pro pripady:
  a1, a2, b, c1, c2. Znazornete graficky, co se deje
  v adresovem prostoru procesu. 


