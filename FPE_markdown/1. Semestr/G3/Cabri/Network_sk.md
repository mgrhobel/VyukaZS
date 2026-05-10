---
title: "Network_sk.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/G3/Cabri/Network_sk.pdf"
date: 2009-01-18
type: PDF (text-based)
---

Postup siet’ovej inštalácie

Cabri II Plus 1.3 pre Windows

Úvod:
Inštalácia Cabri II Plus (Verzia 1.3 alebo vyššia) vyžaduje nasledovné:
- Cabri II Plus inštalátor:
- Umiestnený na CD-ROM ak bol softvér zakúpený v krabicovej verzii.
- Stiahnuť z web stránky Cabrilog (www.cabri.com) alebo od autorizovaného distribútora.
- Správne sériové číslo s licenciou – získané:
- Oboje s CD-ROM ak bol softvér zakúpený v krabicovej verzii.
- Alebo, z web stránky Cabrilog (www.cabri.com) alebo od autorizovaného distribútora ak bol
softvér zakúpený on-line.

Popis:
Sieť: Skupina prepojených počítačov schopných prenosu súborov medzi sebou a zdieľania
aplikačného softvéru. Najbežnejšie sú v súčasnosti siete, používajúce protokol TCP/IP.

Server: Zvláštny počítač pripojený v sieti a poskytujúci ostatným počítačom v sieti súbory,
aplikácie a d’alšie služby

Klient: Počítač pripojený v sieti a schopný zasielat’ požiadavky na server ohl’adom súborov,
spustiť aplikácie nainštalované na servery alebo požiadať o spustenie inej služby.

Pracovné princípy:
Token (oprávnenie), poskytovaný token serverom je používaný na autorizáciu spustenia
Cabri II Plus na klientovi pripojenom v sieti. Použitím tejto metódy každý počítač
pripojený v sieti spustí aplikáciu podl’a špeciﬁkácie individuálnej licencie. Keď je aplikácia
zatvorená na klientovi, token sa vráti späť token serveru a potom je k dispozícii pre d’alšieho
klienta.

1

Všeobecné informácie
Pre inštaláciu Cabri II Plus pre sieťové operácie postupujte podľa nasledovných pokynov:

1 - Inštalácia servera:
Program musí byť nainštalovaný na server v Klient/Server móde (Pozri stranu 3).

2 - Inštalácia klienta:
2.1 - Buď: Inštalujte program ako klienta (Pozri stranu 3).
2.2 - Alebo: Počítač bude spúšťať program priamo zo servera (Pozri stranu 3).

Príklad licencie pre max. 10 užívateľov

Počet možných klientov schopných spustiť Cabri II Plus je neobmedzený, ale skutočný počet,
súčasne pripojených klientov závisí na vašej licencii.
Počet dostupných tokenov (oprávnení) predstavuje maximálny počet súčasne pripojených
užívateľov autorizovaných príslušnou licenciou. Napríklad užívateľská licencia 2-10 zabezpečí
súčasné pripojenie desiatich (oprávnení) tokenov, čiže desať súčasných užívateľov.

2

1 - Inštalácia server:
Server je počítač určený ako token server. Môže to byť počítač typu server alebo pracovná stanica
pripojená do siete.
- Inštalujte Cabri II Plus v Klient/Server móde (Vyberte Network
a Client and Server Installation počas inštalácie).
- Zaregistrujte a aktivujte softvér (Pozri Návod na registráciu a aktiváciu
a softvéru).
- Ak je Cabri II Plus spustený na klientskej pracovnej stanice bez
inštalácie na každom počítači, uistite sa, že je inštalačný priečinok
viditeľný v sieti (zdieľaný) (Pozri § 2.2).
Poznámka: Firewall nainštalovaný na token servery môže zabrániť klientským počítačom pripojiť sa k
serveru. V tomto prípade, kontaktujte správcu siete, alebo postupujte podľa informácií v dodatku tejto
príručky alebo na www.cabri.com, stránka FAQ. Tiež môžete poslať e-mail tímu podpory Cabrilog na
adresu support@cabri.com.

2 - Inštalácia klient:
2.1 - Spustenie na klientskom počítači:
- Inštalujte Cabri II Plus v Klient/Server móde (Vyberte Network
a Client and Server Installation počas inštalácie).
- Vyžadovaná IP adresa servera môže byť vyplnená neskôr, keď používate
softvér po prvý raz.
- Registrácia alebo aktivácia nie je vyžadovaná.
- Táto inštalácia môže byť použitá ako vzor a prenesená na iných klientov
správcom systémov pomocou špeciálneho softvéru.
- Eventuálne môže byť tento inštalačný postup zopakovaný na každom
klientovi.
Poznámka: V prípade, že je na servery nainštalovaný ﬁrewall, klientský počítač nebude schopný
pripojiť sa k serveru.

2.2 – Spustenie priamo zo servera:
- V tomto prípade NIE JE Cabri II Plus nainštalované na
klientskej pracovnej stanici.
- Registrácia alebo aktivácia nie je vyžadovaná.
- Pracovná stanica môže mať spustené Cabri II Plus priamo zo
servera tak dlho, pokiaľ je inštalačný priečinok prístupný klientovi po
sieti.
Na ploche klientského počítača je možné vytvoriť zástupcu na spustenie aplikácie.

3

DODATOK
Ako použit’ CabKeyServer službu, keď je ﬁrewall nainštalovaný na servery?
Nasledovné informácie platia iba pre operačný systém Windows:
Služba CabKeyServer používa portmapper (UDP port #111) a komunikačný port, ktorý je štandardne
nastavený TCP port #889.
TCP port #889 použitý inou aplikáciou môže spôsobovať konﬂikty. V tomto prípade služba
CabKeyServer CabKeyServer automaticky skúša d’alší vyšší TCP port (890). Ak je aj tento použitý inou
aplikáciou, skúša v vzostupnom poradí porty, pokiaľ nevyhľadá volný TCP port.
Správca siete môže nastaviť TCP port iný ako 889. Aby ste uložili toto nastavenie, je potrebné
zameniť hodnotu 889 žiadaným číslom TCP portu v súbore CabKeyServer.ini , ktorý môžete nájsť
v priečinku \Windows\System32 na systémovom disku.
Tato zmena sa prejaví až po reštartovaní služby CabKeyServer(pozri Služby v Nástrojoch pre správu v
Ovládacích paneloch) alebo po reštarte počítača.
Ak súbor CabKeyServer.ini chýba, alebo neobsahuje žiadnu hodnotu, bude pridelené ľubovol’né
volné číslo portu medzi 600 až 1023 ako komunikačný port.
Aby ste zistili, aký komunikačný port používa služba CabKeyServer, môžete použiť program
rpcinfo ktorý môžete nájsť v inštalačnom priečinku (štandardne C:\Program Files\Cabri II
Plus 1.3). V príkazovom riadku sa premiestnite do inštalačného priečinka a zadajte nasledovný
príkaz: rpcinfo.exe –p
Firewall nainštalovaný na servery, môže zabrániť klientským počítačom pristupovať k službe
CabKeyServer. V tomto prípade UDP port #111 bude otvorený tiež ako komunikačný port používaný
CabKeyServer (štandardne TCP port #889). Ak nie je na servery nainštalovaný žiadny ﬁrewall, tieto
porty sú už otvorené.

4

