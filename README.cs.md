[English](README.md) · **Čeština**

# Bezplatné SMS připomínky pro iPhone

Automatické SMS připomínky z událostí v Apple Kalendáři pomocí Apple Zkratek — bez předplatného, bez účtu, bez cizí služby.

---

## O co jde

Spousta živnostníků i jednotlivců platí měsíční poplatek jen za to, aby mohli posílat zprávy typu „nezapomeňte, zítra máte objednáno“. Pokud už nosíte iPhone, dá se totéž zpravidla zvládnout aplikacemi, které v telefonu máte.

Tento projekt sdílí bezplatnou Apple Zkratku a návod psaný srozumitelně. Princip je jednoduchý: do události v kalendáři napíšete telefonní číslo příjemce a Zkratka — spuštěná automatizací, kterou si nastavíte ve vlastním iPhonu — mu pošle SMS připomínku.

Za projektem nestojí žádný server, žádná registrace, žádná analytická platforma a nic se neplatí. Je to postup, ne produkt.

---

## Nainstalovat zkratku

**➜ [Nainstalovat zkratku](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)**

Odkaz otevřete **na iPhonu**. Využívá oficiální mechanismus Applu pro sdílení Zkratek přes iCloud, takže se otevře přímo v aplikaci Zkratky a nabídne přidání.

> Instalace zkratky **sama o sobě nezajistí** její pravidelné spouštění. Načasování je samostatný krok, který si nastavujete sami — viz [Nastavení osobní automatizace](#5-nastavení-osobní-automatizace).

---

## Jak to funguje

```
Událost v kalendáři  →  telefonní číslo v poznámce  →  Zkratka  →  SMS připomínka
```

Podrobněji:

```
   Váš kalendář
        │   nadcházející událost, která obsahuje telefonní číslo
        ▼
   Osobní automatizace  ──── spustí se ve zvolený čas ────▶   Zkratka
                                                                 │
                                                                 ▼
                                                     Zprávy odešlou SMS
```

Postup je navržený tak, aby:

1. prošel relevantní nadcházející události v Kalendáři,
2. přečetl telefonní číslo uložené v informacích o události (pole **Poznámky**),
3. přeskočil každou událost, která použitelné telefonní číslo neobsahuje,
4. odeslal SMS připomínku na nalezená čísla,
5. byl automaticky spouštěn osobní automatizací v aplikaci Zkratky.

Vše probíhá v iPhonu, prostřednictvím aplikací od Applu.

---

## Dvě části, které potřebujete

Tady se nejčastěji chybuje, takže to řekněme naplno. Jsou to **dvě samostatné věci** a potřebujete obě:

| | Co to je | Odkud se to bere |
|---|---|---|
| **Zkratka** | Sled kroků, který najde události, přečte telefonní čísla a odešle zprávy. | Nainstaluje se z [odkazu na iCloud](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78) výše. |
| **Osobní automatizace** | Spouštěč, který Zkratku spustí ve zvolený čas, například každý den v 18:00. | Vytvoříte si ji **vy**, ve **svém** iPhonu, v aplikaci Zkratky. Ve sdíleném odkazu obsažená není a ani být nemůže. |

Apple neumožňuje, aby sdílená Zkratka s sebou nesla automatizaci, takže automatizaci je vždy nutné vytvořit přímo v každém zařízení.

---

## Co je potřeba

- iPhone s aplikací **Zkratky** (je součástí iOS).
- Aplikace **Kalendář** s kalendářem, který chcete používat, viditelným pro iOS. Kalendáře synchronizované do iOS (iCloud, Google, Exchange a podobné) fungují, pokud se zobrazují v aplikaci Kalendář.
- Možnost odesílat **SMS** z telefonu — aktivní tarif a funkční aplikaci Zprávy.
- Oprávnění pro Zkratky přistupovat ke **Kalendáři** a **odesílat zprávy**. iOS se na každé zeptá, až je Zkratka poprvé potřebuje.

Minimální verze iOS zde záměrně není uvedena, protože přesné požadavky Zkratky nebyly ověřeny. Pokud váš iPhone dokáže otevřít odkaz na iCloud a Zkratku přidat, je vše v pořádku. Některé názvy v aplikaci Zkratky se mezi verzemi iOS liší — následující kroky proto popisují, co hledat, ne konkrétní obrazovku.

---

## Nastavení krok za krokem

### 1. Instalace zkratky

1. Otevřete **[tento odkaz](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)** na iPhonu (klepněte na něj ve Zprávách, Poznámkách, Safari nebo kdekoli ho máte).
2. Otevře se aplikace **Zkratky** a zobrazí náhled zkratky.
3. Náhled si můžete projít a pak klepnout na **Přidat zkratku** (některé verze iOS zobrazí **Nastavit zkratku** a nejprve položí jednu či dvě otázky — odpovězte a pokračujte).
4. Zkratka se objeví na panelu **Zkratky** v aplikaci.

Pokud se po klepnutí na odkaz nic nestane, otevřete ho v **Safari**, ne ve vestavěném prohlížeči jiné aplikace.

### 2. Podívejte se, co zkratka skutečně dělá

Než se na ni spolehnete, otevřete si ji a přečtěte. V aplikaci Zkratky klepněte u zkratky na **⋯** (nebo podržte prst → **Upravit**) a uvidíte všechny kroky.

Dvě minuty to stojí za to, protože jednotlivé akce zkratky jsou závazná odpověď na otázky jako:

- **do kterých kalendářů** se dívá,
- **jaké časové okno** považuje za „nadcházející“ (například dnešek, nebo zítřek),
- **kde v události** hledá telefonní číslo,
- **jaký text** zpráva obsahuje.

Cokoli z toho můžete změnit. Ve svém telefonu máte vlastní kopii.

> Přesné vnitřní nastavení sdílené zkratky zde popsáno není, protože se ho při psaní tohoto návodu nepodařilo nezávisle ověřit. Spolehlivou odpověď získáte přečtením zkratky ve vlastním zařízení.

### 3. Jedno ruční spuštění

Klepnutím na zkratku v aplikaci Zkratky ji spustíte ručně.

- iOS si vyžádá oprávnění k přístupu ke **Kalendáři** a k **odesílání zpráv**. Obojí povolte, jinak postup fungovat nemůže.
- Testujte s událostí, která míří na **vaše druhé číslo nebo na známého, který o testu ví** — ne na skutečného zákazníka.

Ruční spuštění je nejrychlejší způsob, jak zjistit, zda máte události v kalendáři zapsané tak, jak to zkratka očekává.

### 4. Příprava událostí v kalendáři

Telefonní číslo příjemce patří **dovnitř události**, do pole **Poznámky** (v aplikaci Kalendář: otevřete událost → **Upravit** → pole **Poznámky** dole).

Vytvoření události:

1. Otevřete **Kalendář** a přidejte událost jako obvykle — název, datum, čas.
2. Klepněte na **Upravit** a sjeďte k poli **Poznámky**.
3. Napište telefonní číslo příjemce.
4. Klepněte na **Přidat** / **Hotovo**.

Názorný příklad:

```
Název:     Stříhání — Jana
Kdy:       Zítra, 14:00
Poznámky:  +420123456789
```

Praktické rady:

- Číslo pište pokud možno v **plném mezinárodním tvaru** (`+` a předvolba země, bez mezer). Tento tvar se pro SMS chová nejpředvídatelněji a nevzniká pochybnost, do které země číslo patří.
- Poznámky zpočátku nechte jednoduché. Chcete-li mít v poli i další text, otestujte tuto kombinaci dřív, než se na ni spolehnete.
- Události **bez** použitelného telefonního čísla se přeskakují — ve stejném kalendáři tak můžete mít i běžné soukromé události.

> Závazná a zaručená podoba telefonního čísla zde záměrně uvedena není: závisí na tom, jak zkratka zpracovává pole Poznámky, což nebylo ověřeno. Otevřete si zkratku (krok 2) a podívejte se, jak přesně číslo získává, a svůj vlastní formát si potvrďte zkušebním spuštěním (krok 3).

### 5. Nastavení osobní automatizace

Díky ní se zkratka spouští sama. Vytváříte si ji sami; není součástí sdílené zkratky.

1. Otevřete **Zkratky** → panel **Automatizace**.
2. Klepněte na **+** (vpravo nahoře). Na některých verzích iOS nejprve zvolíte **Vytvořit osobní automatizaci**.
3. Zvolte **Denní doba**.
4. Vyberte čas, kdy mají připomínky odcházet — například **18:00**, tedy večer předem — a nastavte opakování **Denně**.
5. Klepněte na **Další**.
6. Přidejte akci **Spustit zkratku**, klepněte na název zkratky a vyberte nainstalovanou zkratku pro připomínky.
7. Klepněte na **Další** / **Hotovo**.
8. Než skončíte, **najděte nastavení potvrzování**. Podle verze iOS jde buď o přepínač **Zeptat se před spuštěním** (pro odesílání bez zásahu ho **vypněte**), nebo o volbu mezi **Spustit ihned** a **Spustit po potvrzení** (zvolte **Spustit ihned**). Názvy i umístění se mezi verzemi iOS liší; pokud takovou volbu u této automatizace nevidíte, může se automatizace ohlásit oznámením, na které je nutné klepnout.
9. Ověřte, že je automatizace na panelu Automatizace **zapnutá**.

Čas volte s rozmyslem: automatizace spuštěná v 8:00 pošle připomínky k tomu, co zkratka v 8:00 považuje za „nadcházející“. Čas automatizace sladěte s časovým oknem, které zkratka používá (krok 2).

---

## Soukromí

- Tento projekt **neprovozuje žádný server**. Nemá žádný backend, systém účtů, databázi, analytiku ani platformu pro předplatné.
- Zkratka se šíří přes **oficiální mechanismus Applu pro sdílení Zkratek přes iCloud**. Její stažení je požadavek na servery Applu a řídí se podmínkami a zásadami ochrany soukromí společnosti Apple.
- Kroky celého postupu — čtení událostí v kalendáři a odesílání zpráv — provádějí **aplikace ve vašem iPhonu** na základě oprávnění, která udělíte. Tento repozitář nepřidává žádný vlastní sběr dat.
- Odeslání SMS z podstaty věci prochází vaším **mobilním operátorem**, který se zprávou nakládá jako s každou jinou.
- Pokud si zkratku upravíte a přidáte do ní akce komunikující s dalšími službami, je to mimo rámec toho, co je zde popsáno.

Přesněji řečeno: neposkytuje se žádná absolutní záruka soukromí ohledně služeb Applu, sítě vašeho operátora, poskytovatele synchronizace kalendáře ani vašich vlastních úprav zkratky. Tvrzení je úzké a ověřitelné — tento projekt nemá vlastní službu, která by cokoli sbírala.

---

## Kolik to stojí

- Zkratka i tento návod jsou **zdarma**.
- **Žádné předplatné** a nic k zaplacení.
- **Běžné poplatky vašeho operátora ale platí dál.** Podle tarifu může každá SMS něco stát, čerpat se z limitu zpráv, nebo být zahrnutá v paušálu. Zprávy na zahraniční čísla bývají zpoplatněny jinak. Než začnete posílat větší množství, ověřte si svůj tarif.

---

## Omezení a co je dobré vědět

- **Závisí to na mobilní službě.** Bez signálu nebo bez možnosti odeslat SMS připomínka nedorazí. Zprávy odeslané jako iMessage místo SMS závisí na zařízení a datovém připojení příjemce.
- **Oprávnění v iOS musí být udělena** a musí zůstat udělena. Odepřený přístup ke Kalendáři nebo ke Zprávám postup tiše zastaví.
- **Chování automatizací se mezi verzemi iOS liší.** Názvy nastavení i to, zda automatizace může běžet bez potvrzení, se v jednotlivých verzích iOS měnily.
- **Telefon musí být zapnutý** a v naplánovaný čas běžně funkční. Vypnutý telefon nebo přerušená automatizace znamenají, že ten den zprávy neodejdou.
- **Za zprávy odpovídáte vy.** Posoudit, zda je připomínka vhodná, očekávaná a v souladu s předpisy, je na vás, ne na zkratce.
- **Není to SMS brána.** Jde o osobní postup využívající aplikaci Zprávy. Není určený pro hromadné rozesílání, marketingové kampaně ani velké objemy a operátoři mohou neobvyklé chování při odesílání vyhodnotit jako zneužití.
- **Nic zde není zaručeno.** Vyzkoušejte si to a chvíli to sledujte, než se na to spolehnete v něčem důležitém.

---

## Řešení potíží

**Zkratka nenajde žádné události v kalendáři**
- Zkontrolujte, že je používaný kalendář zapnutý v aplikaci Kalendář (**Kalendáře** dole v měsíčním zobrazení).
- Ověřte, že se zkratka dívá do kalendáře a časového okna, které očekáváte — otevřete ji a přečtěte si akce (krok 2).
- Ověřte, že událost do daného okna opravdu spadá. Automatizace spuštěná v 18:00 pro „zítřejší“ události neuvidí událost o pár hodin později týž večer.
- Zkontrolujte oprávnění ke Kalendáři: **Nastavení → Soukromí a zabezpečení → Kalendáře → Zkratky**.

**V události se nenajde telefonní číslo**
- Číslo musí být v samotné události, nejčastěji v poli **Poznámky** — ne v samostatné poznámce, v kontaktu ani v názvu události, pokud zkratka nečte i je.
- Zkuste prostý mezinárodní tvar: `+420123456789`, bez mezer, závorek a pomlček.
- Odeberte z Poznámek další text a zkuste to znovu; pokud to pak funguje, text postupně vracejte a hledejte, co vadí.

**Zpráva se neodešle**
- Spusťte zkratku ručně. Ruční spuštění zobrazí chyby na obrazovce, které u automatického běhu vidět nejsou.
- Ověřte, že na dané číslo dokážete poslat běžnou zprávu z aplikace **Zprávy**. Co nezvládnou Zprávy, nezvládne ani zkratka.
- iOS si při prvním pokusu vyžádá oprávnění k odesílání zpráv; pokud jste ho odmítli, povolte ho v **Nastavení → Soukromí a zabezpečení**, případně zkratku smažte a nainstalujte znovu, aby se iOS zeptal znovu.
- Některé verze iOS vyžadují potvrzení, než se zpráva z automatizace odešle. Pokud na vás čeká oznámení, je to ono.

**Automatizace se nespustí**
- Otevřete **Zkratky → Automatizace** a zkontrolujte, že je v seznamu a zapnutá.
- Zkontrolujte nastavení potvrzování popsané v kroku 5 — automatizace čekající na potvrzení vypadá jako automatizace, která se nespustila.
- Ověřte, zda se neobjevilo oznámení, které bylo odmítnuto.
- Režim nízké spotřeby, režimy Soustředění i vypnutý telefon mohou ovlivnit, zda se věci stanou včas.

**Oprávnění vypadají špatně**
- **Nastavení → Soukromí a zabezpečení → Kalendáře** a ověřte, že jsou Zkratky povolené.
- **Nastavení → Zkratky** kvůli přepínačům samotné aplikace.
- Po přeinstalaci zkratky si iOS o oprávnění při dalším spuštění řekne znovu.

---

## Odpovědné používání

Připomínky posílejte jen lidem, kteří od vás zprávu čekají — vlastním klientům, pacientům, zákazníkům nebo známým — a jen k účelu, kvůli kterému vám číslo dali. Uveďte ve zprávě, kdo jste, žádost o ukončení zasílání respektujte okamžitě a držte objem nízký a lidský.

Pravidla pro zasílání zpráv, marketing a nakládání s osobními údaji se liší stát od státu (v EU se uplatní GDPR a národní úprava elektronických komunikací). Použití tohoto postupu vás jich nezbavuje. Pokud píšete v profesním kontextu, ujistěte se, která pravidla se na vás vztahují.

---

## O projektu

Nezávislý komunitní projekt, sdílený zdarma, aby lidé nemuseli platit pravidelný poplatek za připomínku, kterou zvládne odeslat jejich vlastní telefon.

Není nijak spojen se společností Apple Inc., není jí schválen ani podporován. Apple, iPhone, iCloud, Kalendář, Zkratky a Zprávy jsou ochranné známky společnosti Apple Inc. registrované v USA a dalších zemích. Ostatní názvy jsou ochrannými známkami příslušných vlastníků.

## Licence

Obsah tohoto repozitáře — dokumentace a návody — je uvolněn pod [licencí MIT](LICENSE).

Tato licence se vztahuje **pouze na obsah tohoto repozitáře**. Nevztahuje se na Apple Zkratku uloženou na serverech iCloud, na aplikaci Zkratky ani na jakýkoli jiný software či službu společnosti Apple a nečiní si na ně žádný nárok; ty se řídí vlastními podmínkami.
