---
title: "bundles.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/cs zdroje/bundles.txt"
date: 2010-01-31
type: TXT
---

Internacionalizované balíky (bundles)

Už víme, co je to internacionalizace, teï co je to balík: Bundle je složka s pøesnì definovanou strukturou, která se z hlediska uživatele chová jako soubor. Ve Finderu se tedy implicitnì nezobrazuje její obsah, je tøeba zvolit z kontextové nabídky Show Package Contents. (Package je nadøazený pojem, znamená pouze složku, která se chová jako soubor. V èeštinì nelze odlišit, dále èeské „balík“ používám pro bundle.)

Souèasné karbonové i kakaové (používající API Cocoa a Carbon) aplikace jsou právì balíky. Balíky jsou i služby, frameworks a jiné typy softwaru, i je tedy lze stejným zpùsobem lokalizovat. My se ale budeme vìnovat pøedevším aplikacím. Jejich struktura vypadá následovnì:

struktura bundle

Veškerý obsah balíku je v jeho podsložce Contents. V její nejvyšší úrovni jsou to informaèní soubory Info.plist, PkgInfo a version.plist; dále jsou tu složky pojmenované podle platformy (v našem pøípadì obvykle „MacOS“), jež obsahují vlastní spustitelné soubory, ty nás ovšem také nezajímají, jsou totiž na lokalizaci nezávislé; a koneènì je tu složka Resources.

Složka Resources obsahuje, jak název napovídá, prostøedky, a nemusí to nutnì být karbonové prostøedky známé ze starého Mac OS (ty, které bývaly v oddìlené èásti souboru). Soubory umístìné pøímo v Resources (napø. MyApp.rsrc) jsou prostøedky nezávislé na lokalizaci, napøíklad ikony. Lokalizované soubory jsou v podsložkách s pøíponou .lproj, které jsou pojmenované buï anglickým jménem jazyka (napø. English, French nebo German, lze to obvykle jen u západoevropských jazykù a japonštiny) nebo dvojpísmenné kódy ISO 639 ve formátu jazyk nebo jazyk_zemì. V pøípadì èeštiny je to cs (nikoli cz!), kód zemì se používat nemusí, obdobnì je to u slovenštiny jednoduché sk. Soubory, které budeme lokalizovat jsou obvykle jednoho z následujících typù: