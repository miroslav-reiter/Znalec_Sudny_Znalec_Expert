## 📴 Základný postup pri forenznej analýze mobilného zariadenia

Pri digitálnej forenzike mobilného zariadenia je základným cieľom **zachovať pôvodný stav zariadenia, minimalizovať zmeny dát a zabezpečiť ich integritu**.

Konkrétny postup závisí najmä od:

- typu zariadenia,
- operačného systému,
- stavu zariadenia – zapnuté alebo vypnuté,
- stavu uzamknutia,
- použitého šifrovania,
- dostupnosti sieťového pripojenia,
- požiadaviek zadávateľa,
- procesného postavenia zariadenia,
- možností použitého forenzného nástroja.

### 📋 Základný workflow

```text
Prevzatie zariadenia
        ↓
Dokumentácia pôvodného stavu
        ↓
Ochrana pred vzdialenými zásahmi
        ↓
Výber vhodnej metódy akvizície
        ↓
Forenzná extrakcia dát
        ↓
Overenie a uchovanie extrakcie
        ↓
Analýza získaných dát
        ↓
Vyhodnotenie nálezov
        ↓
Dokumentácia a znalecký záver
```

### 1. 📷 Zdokumentovanie pôvodného stavu

Pred samotnou manipuláciou zdokumentujeme zariadenie.

Zaznamenáme napríklad:

- výrobcu a model zariadenia,
- sériové číslo a IMEI, ak sú dostupné,
- fyzický stav zariadenia,
- stav displeja,
- dátum a čas zobrazovaný zariadením,
- stav batérie,
- stav uzamknutia,
- vloženú SIM kartu,
- vloženú SD alebo microSD kartu,
- Wi-Fi, Bluetooth a mobilné pripojenie,
- spustené aplikácie alebo zobrazené notifikácie.

Podľa potreby vytvoríme aj fotografickú dokumentáciu.

---

### 2. 📡 Ochrana pred vzdialenou manipuláciou

Mobilné zariadenie môže komunikovať prostredníctvom:

- mobilnej siete,
- Wi-Fi,
- Bluetooth,
- NFC,
- cloudových služieb.

Existuje preto riziko:

- vzdialeného vymazania dát,
- synchronizácie nových dát,
- zmeny obsahu zariadenia,
- prijatia nových správ,
- automatických aktualizácií,
- vzdialeného uzamknutia.

Podľa konkrétneho prípadu môžeme použiť napríklad:

- **Airplane Mode / Režim Lietadlo**,
- izoláciu zariadenia od rádiovej komunikácie,
- Faraday bag alebo iné vhodné izolačné riešenie.

> ⚠️ **Pozor:** zapnutie režimu Lietadlo znamená interakciu so zariadením a môže zmeniť jeho stav. Každý takýto zásah preto dokumentujeme.

---

### 3. 💳 SIM karta a pamäťová karta

Podľa zvolenej metodiky môžeme samostatne skúmať:

- SIM kartu,
- SD kartu,
- microSD kartu,
- internú pamäť zariadenia.

SIM karta môže obsahovať napríklad:

- identifikačné údaje,
- údaje operátora,
- kontakty,
- SMS alebo ďalšie artefakty v závislosti od typu SIM a zariadenia.

Pamäťovú kartu môžeme analyzovať ako samostatný dátový nosič.

> ⚠️ **SIM alebo pamäťovú kartu nevyberáme automaticky v každom prípade.** Pred manipuláciou musíme zvážiť stav zariadenia, zvolenú metódu akvizície a riziko straty dostupných dát.

---

### 4. 🧑‍💻 Developer Mode a USB Debugging v Androide

Pri niektorých metódach akvizície Android zariadení môže forenzný nástroj vyžadovať:

- **Developer Options**,
- **USB Debugging / ADB**.

Vývojársky režim môžeme pri bežnom Android zariadení aktivovať opakovaným kliknutím na položku **Build Number / Číslo zostavy**.

Následne môžeme podľa potreby povoliť:

```text
Developer Options
        ↓
USB Debugging
        ↓
ADB komunikácia
        ↓
Forenzný nástroj
```

> ⚠️ **Dôležité:** zapnutie Developer Mode alebo USB Debugging mení stav skúmaného zariadenia. Preto nejde o univerzálny prvý krok forenznej analýzy. Použijeme ho iba vtedy, keď je tento zásah metodicky odôvodnený, prípustný a riadne zdokumentovaný.

---

### 5. 🔌 Pripojenie zariadenia k forenznej stanici

Zariadenie následne podľa zvolenej metódy pripojíme k pracovnej alebo forenznej stanici.

Použiť môžeme napríklad:

- USB pripojenie,
- špecializovaný forenzný adaptér,
- proprietárne rozhranie,
- bezdrôtovú akvizíciu,
- cloudovú akvizíciu,
- špecializované hardvérové metódy.

Každý významný krok evidujeme.

---

## 🧪 Typy forenznej extrakcie mobilného zariadenia

Pri mobilnej forenzike môžeme použiť viacero úrovní akvizície.

Najčastejšie sa stretávame s:

1. **manuálnou akvizíciou,**
2. **logickou akvizíciou,**
3. **file system akvizíciou,**
4. **fyzickou alebo nízkoúrovňovou akvizíciou.**

---

## 👆 Manuálna akvizícia

Pri manuálnej akvizícii získavame informácie priamo prostredníctvom používateľského rozhrania zariadenia.

Môžeme napríklad:

- prezerať správy,
- kontakty,
- fotografie,
- históriu hovorov,
- nastavenia,
- aplikácie.

Výstup môžeme dokumentovať fotografiami alebo videozáznamom.

### Výhody

- jednoduchá realizácia,
- použiteľná aj pri zariadeniach s obmedzenými možnosťami extrakcie.

### Nevýhody

- veľmi obmedzený rozsah dát,
- vysoké riziko zmeny stavu zariadenia,
- náročnejšia reprodukovateľnosť,
- nezískavame kompletnú dátovú štruktúru.

---

## 📂 Logická akvizícia

**Logická akvizícia** získava údaje prostredníctvom rozhraní poskytovaných operačným systémom, aplikáciou alebo zariadením.

Typicky môžeme získať:

- kontakty,
- SMS a MMS,
- históriu hovorov,
- fotografie,
- videá,
- dokumenty,
- vybrané aplikačné dáta,
- používateľské súbory.

### Výhody

- relatívne rýchla,
- menej invazívna,
- často jednoduchšia na realizáciu,
- výsledná extrakcia môže mať menší objem dát.

### Nevýhody

- získame iba údaje dostupné prostredníctvom podporovaného rozhrania,
- nemusíme získať celý súborový systém,
- nemusíme získať systémové a chránené dáta,
- možnosti obnovy vymazaných dát sú často výrazne obmedzené.

> Logická akvizícia **automaticky neznamená, že nikdy nemôžeme získať zmazané údaje**. Výsledok závisí od aplikácie, databáz, záloh, cache, synchronizácie a ďalších artefaktov.

---

## 🗂️ File System akvizícia

**File System Extraction** poskytuje prístup k širšej štruktúre súborového systému zariadenia.

Môžeme získať napríklad:

- aplikačné databázy,
- konfiguračné súbory,
- systémové artefakty,
- používateľské dáta,
- cache,
- logy,
- metadata,
- vybrané chránené adresáre.

File System akvizícia poskytuje spravidla viac údajov ako jednoduchá logická extrakcia.

---

## 💾 Fyzická a nízkoúrovňová akvizícia

**Fyzická akvizícia** sa snaží získať čo najvernejšiu reprezentáciu dát uložených v pamäťovom priestore zariadenia.

Podľa zariadenia a použitej technológie môže ísť napríklad o:

- physical image,
- full file system,
- partition dump,
- bootloader-based acquisition,
- recovery-based acquisition,
- agent-based extraction,
- JTAG,
- ISP – In-System Programming,
- chip-off.

### Výhody

- potenciálne najväčší rozsah získaných dát,
- možnosť skúmať nižšie vrstvy úložiska,
- možnosť získania systémových artefaktov,
- pri niektorých zariadeniach možnosť analýzy zmazaných alebo nealokovaných dát.

### Nevýhody

- technicky náročnejšia,
- môže vyžadovať špecializovaný hardvér alebo exploit,
- môže byť invazívna,
- výsledky výrazne závisia od typu zariadenia a jeho zabezpečenia.

> ⚠️ Moderné telefóny používajú **šifrovanie, Secure Enclave/TEE, TRIM, garbage collection a ďalšie bezpečnostné mechanizmy**. Preto ani fyzická akvizícia automaticky neznamená, že dokážeme obnoviť zmazané dáta.

---

## 🔍 Logická verzus fyzická akvizícia

| Vlastnosť | Logická akvizícia | Fyzická / nízkoúrovňová akvizícia |
|---|---|---|
| Rýchlosť | spravidla vyššia | spravidla nižšia |
| Náročnosť | nižšia | vyššia |
| Rozsah dát | obmedzenejší | potenciálne širší |
| Súborový systém | čiastočný | môže byť rozsiahlejší |
| Systémové dáta | obmedzené | podľa metódy dostupnejšie |
| Zmazané dáta | obmedzené možnosti | niekedy dostupné |
| Potreba špecializovaných nástrojov | často áno | prakticky vždy |
| Riziko zásahu do zariadenia | nižšie | môže byť vyššie |

---

## 🧰 Príklady forenzných nástrojov

Pri mobilnej forenzike môžeme použiť napríklad:

- **Cellebrite UFED**
- **Cellebrite Physical Analyzer**
- **Magnet AXIOM**
- **MOBILedit Forensic**
- **Oxygen Forensic Detective**

Konkrétne možnosti extrakcie sa líšia podľa:

```text
Výrobca
   +
Model zariadenia
   +
Verzia Android / iOS
   +
Bezpečnostné záplaty
   +
Stav zariadenia
   +
Typ uzamknutia
   +
Šifrovanie
   +
Verzia forenzného nástroja
```

---

## 🔐 Integrita získaných dát

Po získaní dát musíme zabezpečiť ich ďalšie uchovanie.

Podľa typu extrakcie môžeme:

1. uložiť pôvodný forenzný export,
2. vytvoriť pracovnú kópiu,
3. vypočítať hash hodnoty,
4. zaznamenať použitý nástroj a jeho verziu,
5. zaznamenať dátum a čas akvizície,
6. zdokumentovať použitú metódu,
7. uchovať logy z forenzného nástroja.

Príklady hash algoritmov:

```text
SHA-256
SHA-512
```

Hash môžeme používať na preukázanie, že analyzovaný súbor alebo forenzný obraz sa od okamihu jeho získania nezmenil.

---

## 🔎 Čo môžeme vo forenznej extrakcii analyzovať

Podľa znaleckého zadania môžeme skúmať napríklad:

- SMS, MMS a chatové správy,
- e-mailovú komunikáciu,
- históriu hovorov,
- kontakty,
- fotografie,
- videá,
- dokumenty,
- GPS a lokalizačné údaje,
- históriu webového prehliadača,
- sociálne siete,
- aplikačné databázy,
- cloudové artefakty,
- používateľské účty,
- systémové logy,
- metadata,
- časové údaje,
- zmazané alebo čiastočne obnoviteľné dáta.

Pri analýze vždy vychádzame z **rozsahu zadania a položených znaleckých otázok**.

---

## ⚖️ Analýza obsahu vo vzťahu k znaleckému zadaniu

Po vytvorení extrakcie môžeme analyzovať údaje relevantné pre konkrétny prípad.

Môžeme napríklad skúmať:

```text
Komunikácia
Fotografie a videá
Dokumenty
Lokalizačné údaje
História používania aplikácií
Časové údaje
Digitálne stopy
Vymazané dáta
```

Ak predmet zadania súvisí s vyšetrovaním trestnej činnosti, môžeme vyhľadávať obsah alebo artefakty relevantné pre položené otázky, napríklad údaje súvisiace so:

- zbraňami,
- omamnými a psychotropnými látkami,
- finančnými transakciami,
- komunikáciou medzi konkrétnymi osobami,
- lokalizáciou zariadenia,
- fotografiami alebo videami,
- ďalšími skutočnosťami vymedzenými zadávateľom.

> Znalec nemá bezdôvodne prehľadávať celý obsah zariadenia. Rozsah analýzy musí zodpovedať zadaniu, znaleckým otázkam a právnemu rámcu konkrétneho prípadu.

---

## 🧬 Zjednodušený model mobilnej forenziky

```text
MOBILNÉ ZARIADENIE
        ↓
ZAISTENIE A DOKUMENTÁCIA
        ↓
OCHRANA PRED ZMENOU DÁT
        ↓
FORENZNÁ AKVIZÍCIA
        ↓
LOGICKÁ / FILE SYSTEM / FYZICKÁ
        ↓
OVERENIE INTEGRITY
        ↓
FORENZNÁ ANALÝZA
        ↓
DIGITÁLNE ARTEFAKTY
        ↓
ODBORNÁ INTERPRETÁCIA
        ↓
ZNALECKÝ ZÁVER
```

## ⚠️ Najdôležitejšie pravidlo

**Pri digitálnej forenzike sa snažíme získať maximum relevantných informácií pri minimálnej zmene pôvodných dát.**

Každý zásah do zariadenia musí byť:

- odborne odôvodnený,
- primeraný,
- zdokumentovaný,
- reprodukovateľný alebo vysvetliteľný,
- súčasťou zachovanej auditnej a dôkaznej stopy.
