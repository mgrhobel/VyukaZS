---
title: "jirkaSkype.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/jirkaSkype.txt"
date: 2010-03-21
type: TXT
---

[20.3.2010 20:14:19] Jiri Kiml: Tak uz jsi opravil preklepy ?
[20.3.2010 20:15:07] Josef Hobel: Dìlam porad na oprave tech vet, preklepy udelam az na konci.
[20.3.2010 20:23:08 | Upraveno 20:25:19] Josef Hobel: Napsal jsem spravne, ze argumetem proc nejsou vsechny texty ulozeny v RepoResourceBundle (kdyz ma ty vyhody, ze muze preklad pripojit k objektu), je ten ze vetsina textu k prekladu je prostej text, pro kterej neni potreba vytvaret v repository objekt?
[20.3.2010 20:25:54] Jiri Kiml: to co je v repo resource bundle je jsou preklady, ktere se nejak primo vazou k hodnotam atributu, tj. ruzna instance objektu muze mit jiny preklad
v message bundle muzes mit cokolit, takze treba texty pro nejake vypisy a tak
[20.3.2010 20:26:15] Jiri Kiml: ten text pro vypisy neni ruzny pro ruzne instance
[20.3.2010 20:27:00] Josef Hobel: aha, takze u tech RepoResourceBundle je dulezita ta zmena hodnot pro jiny instance jo?
[20.3.2010 20:31:37] Jiri Kiml: Rekneme treba JButton ma label a ty ho chces mit i18n.
Mas v repozitory 1000 JButtonu, ze ruznymi hodnotami label a jejich i18n variany.
Ted si predstav, ze chces prenest jen 30 techto buttonu k zakaznikovi. Kdyz je to reporesource bundle, tak je proste preneses, kdyby to byl message bundle, tak by jsi v nem mel preklady pro vsech 1000 buttonu, ale ty chces prenest jen 30.

V tom JButton budes mit treba hlasku typu "tlacitko bylo zmacknuto" a tu je naopak v dobre mit v message bundle, protoze je spolecna pro vsechny button.

Tj. co je spolecne pro "tridu", tj. vsechny instance -> message bundle (protoze kdyby to bylo reporesource bundle, tak by to zbytecne bralo pamet)
Co neni spolecne pro tridu, tj. je ruzne pro ruzne instance -> repo resource bundle
[20.3.2010 20:40:17] Josef Hobel: ok, to dava smysl. Jeste bych teda moh uvest do nevyhod repoResourceBundle ze muzou zabirat pamet.
[20.3.2010 20:41:09] Jiri Kiml: no ale to ti message bundle zabira taky, dokonce message bundle se ti i kvuli jednomu klici nacita cely do pameti
[20.3.2010 20:41:58] Jiri Kiml: repo resource bundle zabira zbytecne hodne pameti, jen pokud mas v ruznych instancich stejne hodnoty
[20.3.2010 20:46:12] Josef Hobel: Takze v tomhle pripade je lepsi pouzit messageBundle, kde se v jednom klici uvede preklad a ten se pak zavola v jednotlivych instancich
[20.3.2010 20:48:58] Jiri Kiml: repo resource bundle je proste vhodna pro ruzne hodnoty attributu, treba titulek

pokud by jsi mel treba attribut titul a k tomu tech 1000 instanci, tak je asi lepsi mit tituly v messge bundle, protoze titulu je rekneme jenom 10 (naopak ruznych titulku bude zrejme pro 1000 instanci 1000).
[20.3.2010 20:52:36] Josef Hobel: jo tomu myslim rozumim
[20.3.2010 21:01:22] Josef Hobel: jeste teda, da se kazda komenenta z MPA dohledat v repository? Je tam teda opravdu tech 1000 buttonu?
[20.3.2010 21:03:30] Jiri Kiml: no to samozrejme neni, v repozitory je jen to co tam das, resp. do repozitory ma smysl davat jen to co ma smysl aby nekdo v budoucnu customizoval/konfiguroval

ty treba z mitu nedavas do repozitory nic, actmonitor taky ne, ale treba expressny tam jsou, workarea, toolbar, navigation bar ............
[20.3.2010 21:03:47] Jiri Kiml: treba tvoje mit.properties by klidne v repozitory byt mohli
[20.3.2010 21:07:12] Josef Hobel: takze 1000 buttonu byl priklad, prakticky se teda do RepoReousceBundle nedostanou a je treba je davat do MessageBundlu
[20.3.2010 21:07:40] Josef Hobel: prakticky priklad je 1000 expressions
[20.3.2010 21:10:11] Jiri Kiml: kdyz budu chtit abych mel workareu, kde si bude customizer (ne programator) vybirat co doktor (uzivatel) uvidi, tak mu klidne do repozitory pripravim 1000 buttonu aby mel z ceho vybirat. Dokonce on (customizer) si bude moci v repo browseru udelat dalsi kdyz bude chtit a bude to fungovat.

kdyz mas mit toolkit a v nem tlacitko reload, tak je podle mne zbytecne to davat do repozitory, protoze to nikdo nikdy konfigurovat nebude
[20.3.2010 21:23:11] Josef Hobel: Pokud teda potrebuju 10 nebo i vic rùznych prekladu pro 1 objekt buttonu. Pak je dobry pouzit RepoResourceBundle. Pak mi staci vytvorit napr. tech 10 RepoResourceBundle a nemusim vytvaret znova cele objekty typu button. Je to tak?
[20.3.2010 21:25:02] Jiri Kiml: rozumis rozdilu mezi tridou a objektem (instanci) ?
[20.3.2010 21:25:58 | Upraveno 21:26:12] Josef Hobel: doufam, ze jo. Trida je jednou definova a je mozny z ni vytvorit nekolik instanci s ruznyma hodnotama atributu.
[20.3.2010 21:27:00] Jiri Kiml: jo, presne
takze repo resource bundle ma smysl tam, kde potrebujes internacionalizaci attributu instanci
[20.3.2010 21:27:22] Jiri Kiml: proste ta instance is nese sebout i tu internacionlizaci
[20.3.2010 21:27:25] Jiri Kiml: neco jako:
[20.3.2010 21:27:54] Jiri Kiml: class XXX {
   string neco;
   string necoI18N;
}
[20.3.2010 21:29:08] Josef Hobel: a do toho atributu necoI18N se nabije ta hodnota s RepoResourceBundle.
[20.3.2010 21:29:36] Josef Hobel: Kdyz je vice repoResourceBundle tak je mozny pouzit vic textu
[20.3.2010 21:30:25] Jiri Kiml: je to jenom priklad na predstavu, ve skutecnosti je ta repo resource bundle vnoreny objekt, ale zhruba je to tak tak. Te druhe tve vete nerozumim.
[20.3.2010 21:32:08] Josef Hobel: Kdyz chci mit preklad pro cestinu a anglictinu - tak musim vytvorit 2 repoResourceBundle. Ty pak obe muzu predavat te tride XXX.
[20.3.2010 21:33:01] Jiri Kiml: ne, je tam jeden vnoreny objekt (repo resource bundle) a ten muze mit v sobe vice jazyku
[20.3.2010 21:33:42] Jiri Kiml: class XXXX {
  string neco;
  repo resource bundel (neco jako Map<jazyk, preklad>();
}
[20.3.2010 21:40:56] Josef Hobel: takze mam jen jeden repoResourceBundle objekt, ktery obsahuje vsechny jazyky? Pak podle parametru jazyk muzu rict, jestli se pouzije cestina nebo anglictina nebo nemcina (defaultni)
[20.3.2010 21:41:39] Jiri Kiml: jo presne
[20.3.2010 21:42:06] Jiri Kiml: nejsem si jist, zda takoveto detaily popisovat do te diplomy, spise bych rekl, ze ne
[20.3.2010 21:43:11] Josef Hobel: Ja jsem ale vytvoril Repository editor tak, ze pro jeden jazyk existuje vzdycky jeden RepoResourceBundle objekt.
[20.3.2010 21:44:16] Jiri Kiml: ok, probereme to v pondeli, do diplomky to nepotrebujes
[20.3.2010 21:45:34] Josef Hobel: dobre, diky za cas