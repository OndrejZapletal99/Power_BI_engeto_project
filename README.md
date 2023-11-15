# Engeto projekt PowerBI - Základní ekonomické a demografické ukazatele jednotek NUTS 1, NUTS 2 a NUTS 3 v ČR

- *Závěrečný projekt Engeto datové analýzy*
- **PowerBi** a **Excel**
- *DISCORD*: "ondrej_zapletal"
---


 # Obsah
- [Engeto projekt PowerBI - Základní ekonomické a demografické ukazatele jednotek NUTS 1, NUTS 2 a NUTS 3 v ČR](#engeto-projekt-powerbi---základní-ekonomické-a-demografické-ukazatele-jednotek-nuts-1-nuts-2-a-nuts-3-v-čr)
- [Obsah](#obsah)
  - [1. Zadání projektu](#1-zadání-projektu)
    - [1.1 Kritéria](#11-kritéria)
  - [2. Zdrojová data](#2-zdrojová-data)
    - [2.1 Hierarchie NUTS pro ČR](#21-hierarchie-nuts-pro-čr)
    - [2.2 Demografické ukazatele jednotlivých krajů](#22-demografické-ukazatele-jednotlivých-krajů)
    - [2.3 Ekonomické ukazatele jednotlivých krajů](#23-ekonomické-ukazatele-jednotlivých-krajů)
    - [2.4 Tabulka se sledovanými roky](#24-tabulka-se-sledovanými-roky)
  - [3. PowerBI](#3-powerbi)
    - [3.1 Změna datových typů a nastení formátu hodnot](#31-změna-datových-typů-a-nastení-formátu-hodnot)
    - [3.2 Vytvoření hierarchie pro NUTS](#32-vytvoření-hierarchie-pro-nuts)
    - [3.3 Relační model](#33-relační-model)
		
  
## 1. Zadání projektu
Tentokrát nebudeš odpovídat na otázky, ale je zcela na tvém výběru, které ukazatele jsou pro tebe nejzajímavější.
Můžeš se tedy samozřejmě inspirovat otázkami z prvního projektu, hlavně je ale musíš vhodným způsobem graficky zobrazit v Power BI reportu.

Tvým úkolem tedy je vizualizovat tebou zvolený dataset podle níže zadaných kritérií.

### 1.1 Kritéria
- Rozsah 2-3 stránky
- Minimálně 5 různých typů vizuálů
- Filtrování pomocí slicerů
- Využití bookmarks/page navigation
- Propojení více datových zdrojů, ať už v Power Query, nebo v Power BI
- Použití datové hierarchie o alespoň dvou úrovních
- Vytvoření alespoň 1 measure (metrika/míra) a 1 kalkulovaného sloupce
- Grafická úprava použitých vizuálů a vizuálně přívětivý výsledný report
## 2. Zdrojová data
### 2.1 Hierarchie NUTS pro ČR
Z pohledu rozdělení NUTS je celá Česká republika kategorizována jako NUTS1. NUTS2 jsou jednotlivé regiony soudržnosti a NUTS3 jsou jednotlivé kraje české republiky.Tato hierarchie je dostupná na [**webu**](https://portal.uur.cz/spravni-usporadani-cr-organy-uzemniho-planovani/nuts.asp). Z tohoto webu byla importována data do excelu a následně uložena do formátu CSV v souboru [NUTS_hierarchie](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/NUTS_hierarchie.csv).
>Tento textový soubor byl importován do PowerBI a byla nutná ruční úprava v PowerQUery, ke byl nastaven první řádek jako zálhaví.
### 2.2 Demografické ukazatele jednotlivých krajů
Na [**webu**](https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fwww.czso.cz%2Fstaticke%2Fgapminder%2Fporovnani_kraju_vse%2FXLS%2Fukazatele_kraje_demogr.xlsx&wdOrigin=BROWSELINK) Českého statistického úřadu jsou veřejně dustupná data o demografii jednotlivých krajů České republiky. Z veřejne dostupného excel soubouru byla vyextrahována data ohledně počtu obyvatel a přirozeném přistutu v ČR mezi roky 2000 a 2022. Tato data byla uložena ve dvou CSV souborech, a to [Kraj_obyvatelsto](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/Kraj_obyvatelstvo.csv) a [Kraj_prirustek](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/Kraj_prirustek.csv).
- **Obyvatelstvo** - stavová veličina počtu obyvatel v daném roce k 31.12
- **Přirozebý přírůstek(úbytek)** - přírůstek(úbytek) počtu obyvatel na 1000 obyvatel středního stavu.
>Tyto textové soubor byly importovány do PowerBI a byla nutná ruční úprava v PowerQUery, ke byl nastaven první řádek jako zálhaví a také byly jednotlivé sloupce transponovány na řádky, abychom vytvořili "dlouhá" a ne "široká" data.
### 2.3 Ekonomické ukazatele jednotlivých krajů
Na [**webu**](https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fwww.czso.cz%2Fstaticke%2Fgapminder%2Fporovnani_kraju_vse%2FXLS%2Fukazatele_kraje_ekon.xlsx&wdOrigin=BROWSELINK) Českého statistického úřadu jsou veřejně dustupná data o ekonomickýcg ukazatelích jednotlivých krajů České republiky. Z veřejne dostupného excel soubouru byla vyextrahována data ohledně HDP a čistého disponibilního důchodu domácností v ČR mezi roky 2000 a 2021. Tato data byla uložena ve dvou CSV souborech, a to [Kraj_hdp](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/Kraj_HDP.csv) a [Kraj_cddd](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/Kraj_cddd.csv).
- **HDP na jednoho obyvatele** - regionální HDP na 1 obyvatele (Kč, běžné ceny)
- **Čistý disponibilní důchod domácností na 1 obyvatele(CDDD)** - Čistý disponibilní důchod domácností na 1 obyvatele (Kč, běžné ceny)
>Tyto textové soubor byly importovány do PowerBI a byla nutná ruční úprava v PowerQUery, ke byl nastaven první řádek jako zálhaví a také byly jednotlivé sloupce transponovány na řádky, abychom vytvořili "dlouhá" a ne "široká" data.
### 2.4 Tabulka se sledovanými roky
Pro lepší práci s daty a byla vytvořena tabulka pro sledované roky v rozmezí od roku 2000 do roku 2021. Tato tabulka byla uloženena jako CSV soubor [Rok](https://github.com/OndrejZapletal99/Power_BI_engeto_project/blob/main/Rok.csv).
>Tento textový soubor byl importován do PowerBI a byla nutná ruční úprava v PowerQUery, ke byl nastaven první řádek jako zálhaví a takové změněný datový typ na *text*.
## 3. PowerBI
### 3.1 Změna datových typů a nastení formátu hodnot
1. Změna HDP na 1ob. na formát měny v KČ a také nastaveno nevytváření souhrnu
2. Změna CDDD na 1ob. na formát měny v KČ a také nastaveno nevytváření souhrnu
3. Počet obyvatel nastaveno jako celé číslo a také nastaveno nevytváření souhrnu
4. Přírůstek obyvatel nastaveno jako desetiiné číslo a také nastaveno nevytváření souhrnu
### 3.2 Vytvoření hierarchie pro NUTS
Pomocí PowerBI možnosti vytvoření hierarchií byla vytvořena nová hierarchie v posloupnosti NUTS1>NUTS2>NUTS3
### 3.3 Relační model
Jako poslední úprava dat byl vytvořen relační model mezi tabulkami.
![Relační model]()
