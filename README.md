# innst — vefstofa

Vefur innst: vandaðar vefsíður fyrir íslensk fyrirtæki.

Þetta eru drög. Vefurinn er ein kyrrstæð HTML-síða án byggingarskrefs, svo hægt er að hýsa hann beint á Netlify, GitHub Pages eða Cloudflare Pages.

## Skrár

- `index.html` — forsíðan
- `personuvernd.html` — persónuverndarstefna
- `skilmalar.html` — skilmálar fyrir áskrift, staðgreidda vefi, hýsingu og umsjón
- `takk.html` — síðan sem birtist eftir að fyrirspurn er send
- `assets/sidur.css` — sameiginlegt útlit fyrir undirsíðurnar
- `assets/letur/` — letrið (Manrope og Inter), hýst á vefnum sjálfum, aðeins latneskir og íslenskir stafir
- `og-image.png` — myndin sem birtist þegar vefnum er deilt á Facebook, LinkedIn o.fl.
- `robots.txt`, `sitemap.xml` — fyrir leitarvélar
- `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` — tákn fyrir vafra og síma
- `assets/verkefni/` — skjámyndir af verkefnum
- `assets/merki/` — merki innst í öllum útgáfum (SVG og PNG)

## Hafðu-samband formið

Formið notar [Netlify Forms](https://docs.netlify.com/forms/setup/). Það virkar þegar vefurinn er hýstur á Netlify:

1. Tengja gagnageymsluna við Netlify (Add new site → Import from Git).
2. Í Netlify: Forms → kveikja á „Form detection“ og birta vefinn aftur.
3. Forms → `samband` → Form notifications: bæta við tölvupósti svo fyrirspurnir berist á netfang.
4. Senda prófunarfyrirspurn og athuga að hún berist.

Ruslpóstsvörn: falinn reitur (`vefur-ruslpostur`) sem fólk sér ekki en vélmenni fylla út.

Uppruni: falinn reitur (`uppruni`) fyllist úr UTM-merkjum slóðarinnar, t.d. `facebook / prof1 / askrift`, eða úr vefnum sem vísaði á okkur. Án UTM-merkja og tilvísunar stendur `beint`. Notað til að bera saman auglýsingar í A/B-prófunum.

## Tímabundið falið

Fjórir hlutar eru í kóðanum en faldir með `hidden` þar til þeir eru tilbúnir:

- **Verkin** (`<section id="verkefni" hidden>`) og hlekkurinn „Verkin“ í valmyndinni
- **Vefverslun**, verðkortið með merkinu „Netverslun“
- **Smáforrit**, verðkortið með merkinu „Væntanlegt“
- **Hverjir eru á bak við innst**, teymishlutinn neðst í Kjarnanum

Til að birta hluta aftur: fjarlægja `hidden` af honum. Þegar Verkin koma aftur þarf líka að:

- númera hlutana aftur (`01 — Verð` verður `02 — Verð` o.s.frv.)
- setja „Vefverslun“ og „Smáforrit“ aftur í fellilistann í forminu þegar þau koma aftur
- bæta vefversluninni aftur við schema (`makesOffer`) og `priceRange`

## Eftir að klára

- Kennitala og heimilisfang eru falin með `<span hidden>` í fætinum á `index.html`, í `personuvernd.html` og `skilmalar.html`. Þegar fyrirtækið er skráð: fylla inn og fjarlægja `hidden`. Ef fyrirtækið skráir sig á VSK-skrá má bæta VSK-númerinu við á sömu staði.

- Fylla inn reiti í hornklofum, t.d. `[BÓKUNARHLEKKUR]`, `[SÍMANÚMER]`, `[KENNITALA]`, `[HEIMILISFANG]` (líka í `personuvernd.html` og `skilmalar.html`)
- Láta lögfræðing eða endurskoðanda lesa yfir `skilmalar.html` áður en fyrsti samningur er gerður
- Setja inn myndir af Axel og Ólafi
- Staðfesta lénið: allar slóðir í `index.html`, `sitemap.xml` og `robots.txt` gera ráð fyrir `https://innst.is/`
