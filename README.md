# innst — vefstofa

Vefur innst: vandaðar vefsíður fyrir íslensk fyrirtæki.

Þetta eru drög. Vefurinn er ein kyrrstæð HTML-síða án byggingarskrefs, svo hægt er að hýsa hann beint á Netlify, GitHub Pages eða Cloudflare Pages.

## Skrár

- `index.html` — forsíðan
- `personuvernd.html` — persónuverndarstefna
- `takk.html` — síðan sem birtist eftir að fyrirspurn er send
- `assets/sidur.css` — sameiginlegt útlit fyrir undirsíðurnar
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

## Eftir að klára

- Fylla inn reiti í hornklofum, t.d. `[TÍMAGJALD]`, `[BÓKUNARHLEKKUR]`, `[SÍMANÚMER]`, `[KENNITALA]`, `[HEIMILISFANG]` og vsk (líka í `personuvernd.html`)
- Setja inn myndir af Axel og Ólafi
- Staðfesta lénið: allar slóðir í `index.html`, `sitemap.xml` og `robots.txt` gera ráð fyrir `https://innst.is/`
- Hýsa letrið á vefnum sjálfum og fjarlægja þá málsgreinina um Google Fonts í `personuvernd.html`
