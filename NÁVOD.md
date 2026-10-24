# Góly – webová aplikace pro trenéry

Aplikace běží v prohlížeči na iPhonu, Androidu i počítači. Nepotřebuje Claude ani žádný účet.
Data si každý trenér ukládá do svého telefonu a ostatní je nevidí.

## Co je v balíčku

| Soubor nebo složka | K čemu slouží |
|---|---|
| `index.html` | celá aplikace |
| `sw.js` | umožní spouštění bez internetu |
| `manifest.webmanifest` | název a ikona aplikace na ploše telefonu |
| `icons/` | ikony aplikace |
| `fonts/` | písma (aplikace je nestahuje z internetu) |
| `NÁVOD.md` | tento návod (na web ho nahrávat nemusíte) |

Aplikace musí běžet na adrese začínající `https://`. Otevřená jen jako soubor z počítače
nebude fungovat spouštění bez internetu ani instalace na plochu.

---

## 1. Zveřejnění zdarma na GitHub Pages

Účet zakládáte jen vy. Trenéři dostanou obyčejný odkaz.

1. **Založte si účet** na [github.com](https://github.com) (tlačítko *Sign up*).
2. **Vytvořte repozitář:** vpravo nahoře klikněte na **+** → **New repository**.
   - *Repository name:* `goly`
   - nechte zvolené **Public**
   - klikněte na **Create repository**.
3. **Nahrajte soubory:** na stránce nového repozitáře klikněte na odkaz
   **uploading an existing file** (nebo **Add file → Upload files**).
   Do okna přetáhněte **obsah** rozbalené složky `goly-web`, tedy soubory `index.html`, `sw.js`,
   `manifest.webmanifest` a složky `icons` a `fonts`. Ne samotnou složku `goly-web`.
   Přetažení složek funguje v prohlížečích Chrome a Edge.
   Dole klikněte na **Commit changes**.
4. **Zapněte web:** v repozitáři otevřete **Settings → Pages**.
   V části *Build and deployment* zvolte *Source:* **Deploy from a branch**,
   *Branch:* **main** a složku **/ (root)**, pak **Save**.
5. Za 1–2 minuty se nahoře na stránce *Pages* objeví adresa ve tvaru
   `https://VASE-JMENO.github.io/goly/`. Tu pošlete trenérům.

> Bezplatné GitHub Pages vyžadují veřejný repozitář. Veřejný je ale jen kód aplikace,
> nikoli data trenérů. Ta zůstávají v jejich telefonech.

### Jiná možnost: Netlify

Na [app.netlify.com/drop](https://app.netlify.com/drop) si založte účet a do okna přetáhněte
celou složku `goly-web`. Netlify vytvoří adresu typu `https://nazev.netlify.app`
a v nastavení webu (*Site configuration → Change site name*) ji můžete přejmenovat.

---

## 2. Text pro trenéry (můžete ho přeposlat)

> **Aplikace Góly pro zápis zápasů:** `https://VASE-JMENO.github.io/goly/`
>
> **iPhone:** otevřete odkaz v **Safari** → tlačítko **Sdílet** (čtverec se šipkou) →
> **Přidat na plochu** → **Přidat**. Aplikaci pak spouštějte vždy **z ikony na ploše**.
>
> **Android:** otevřete odkaz v **Chrome** → menu **⋮** → **Nainstalovat aplikaci**
> (nebo **Přidat na plochu**).
>
> Po prvním otevření funguje aplikace i bez internetu. Data jsou uložená jen ve vašem
> telefonu, proto si občas udělejte zálohu: **Export a import → Exportovat data**
> a soubor si uložte (Soubory, Disk Google, e-mail). Při výměně telefonu zálohu
> v novém telefonu načtete přes **Importovat ze souboru**.

---

## 3. Důležité k datům

- **Každé zařízení má vlastní data.** Co zapíšete v telefonu, na počítači neuvidíte.
  Přenést je můžete exportem a importem zálohy.
- **iPhone: aplikace na ploše a Safari mají oddělená data.** Kdo nejdřív zkoušel aplikaci
  v Safari a pak si ji přidal na plochu, data v ní neuvidí. Stačí je v Safari exportovat
  a v aplikaci z plochy importovat. Nejjednodušší je přidat si aplikaci na plochu hned
  a používat jen ji.
- **Smazání dat webu v nastavení prohlížeče smaže i data aplikace.** Proto zálohy.
- **Záloha je stejná jako v aplikaci pro Android.** Data jde přenášet oběma směry.

---

## 4. Aktualizace aplikace

Když dostanete novou verzi, nahrajte nové soubory do repozitáře stejně jako poprvé
(**Add file → Upload files**). Stejně pojmenované soubory se přepíšou.
Trenérům se nová verze načte při dalším spuštění s připojením k internetu.

Pokud se v nové verzi mění i ikony nebo písma, v souboru `sw.js` zvyšte číslo verze
na řádku `const VERSION = 'goly-v1';` (například na `goly-v2`).

---

## 5. Omezení na iPhonu

- Safari neumí vibrovat. Konec poločasu poznáte podle oranžové časomíry a upozornění.
- Displej může během zápasu zhasnout. Doporučte trenérům prodloužit
  **Nastavení → Zobrazení a jas → Automatický zámek**. Časomíra se počítá z hodin
  telefonu, takže i se zhasnutým displejem běží správně.
