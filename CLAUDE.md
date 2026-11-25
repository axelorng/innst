# innst — samhengi fyrir Claude

innst er íslensk vefstofa bræðranna **Axels Arnar Gíslasonar** (vefhönnun og markaðsmál, axel@innst.is) og **Ólafs Rafns Gíslasonar** (forritun, olafur@innst.is). Vefurinn innst.is selur vandaða, sérforritaða vefi á föstu verði.

Þessi skrá er fyrir Claude Code. Tæknilegar upplýsingar um skrár, formið og það sem er falið eru í `README.md`: lestu hana líka.

## Vinnureglur

- **Tungumál:** allt efni á vefnum og í markaðsefni er á íslensku. Vandaðu málfarið og beygingar. Svaraðu Axel á því tungumáli sem hann skrifar á.
- **Git:** búa til grein → PR → **sameina aðeins þegar Axel biður um það** (squash merge). Aldrei force-push eða endurskrifa `main`.
- **Lykilorð og greiðslur:** Claude slær aldrei inn lykilorð eða greiðsluupplýsingar. Axel skráir sig sjálfur inn.
- **Markaðsefni** (færslur, auglýsingar, textar): stutt og hnitmiðað. Á að grípa athygli á fyrstu 0,46 sekúndunum, sama tíma og vefurinn er að opnast. Engir langir textar.
- **Orðalag:** forðast „hleðst“ og „hlaðast“ um hraða vefsins, því það minnir á rafbíla. Nota „opnast“ í staðinn.
- Ekki nefna Axel og Ólaf með nafni í auglýsingum eða færslum.
- PDF-skjöl eru aðeins uppfærð þegar Axel biður sérstaklega um það.

## Vefurinn

- Kyrrstæð HTML-síða án byggingarskrefs. Letrið er hýst á vefnum sjálfum í `assets/letur/` (Manrope og Inter).
- **Slagorð:** „Vandað inn að kjarna.“
- **Litir:**
  - dökkblár `#08111D`
  - ljós `#EEF3F7`
  - rauður kjarni `#C8361B`
  - grár texti `#CDD7E2`
- **Sýnileg verð** (án vsk, greitt einu sinni):
  - Lendingarsíða 59.990 kr.
  - Fyrirtækjavefur 109.990 kr. (allt að 5 síður)
  - Sérlausn á tilboði
  - Sýnileiki 19.990 kr. (Google-fyrirtækjasíða, Search Console, titlar)
  - Breytingar eftir afhendingu 14.990 kr./klst.
- **Falið þar til greiðslusíða er komin:** áskrift (12.990 / 18.990 kr. á mánuði), hýsing (3.990 kr. á mánuði), Umsjón og Vöxtur. Nánar í `README.md`.
- **Kennitala og VSK** eru ekki komin, og þeir reitir eru faldir.
- **Netfang á vefnum:** alltaf hallo@innst.is. Ekkert símanúmer.
- **„Bóka fund“** vísar á formið (`#fyrirspurn`). Fundurinn er ókeypis og tekur 20 mínútur.

## Hýsing og innviðir

- **GitHub:** `axelorng/innst`. **Netlify** birtir `main` sjálfkrafa.
  - Netlify-verkefni: `313a6e94-dd6f-4573-9406-23bb201accbb`
  - Forskoðanir eru læstar á bak við innskráningu.
- **Form:** Netlify Forms, formið „samband“ (formId `6ade70634872188a6ac2c414`).
  - Tilkynningar fara á hallo@innst.is.
  - Falinn reitur `uppruni` fyllist úr UTM-merkjum (`utm_source / utm_campaign / utm_content`) eða úr vefnum sem vísaði á síðuna, og geymist í sessionStorage. Engar vafrakökur.
- **DNS:** hjá Cloudflare, allt stillt á „DNS only“.
  - `@` og `www` eru CNAME á `innst.netlify.app`.
  - Ekki snerta Migadu-færslurnar: MX, SPF, DKIM key1–3, DMARC, autoconfig og hosted-email-verify.
  - TXT-færslan `google-site-verification=…` staðfestir Search Console og **má ekki eyða**.
  - Gamli Cloudflare-workerinn „innst“ er aftengdur léninu.
- **Tölvupóstur:** Migadu.
  - Pósthólfin eru axel@ og olafur@. hallo@ er samnefni (alias).
  - IMAP: `imap.migadu.com:993`. SMTP: `smtp.migadu.com:465`.
- **Mælingar:** Cloudflare Web Analytics er sett inn handvirkt neðst á hverri síðu. Enginn Meta pixel, því hann krefst vafrakökuborða og gerir lítið gagn við þessa umferð.
- **Google Search Console:** lénseignin `sc-domain:innst.is` var staðfest 24. nóv. 2026 og sitemap.xml er sent inn.
- **Stuttir hlekkir** í `_redirects`:
  - `/ig` → `utm_source=instagram&utm_campaign=bio`
  - `/fb` → `utm_source=facebook&utm_campaign=sida`

## Markaðssetning

- **Facebook og Instagram:** síðan innst. Hlekkur í bio er innst.is/ig og hlekkur í færslum innst.is/fb.
- **Meta-herferð:** Traffic-herferð, sett upp 24.–25. nóv. 2026.
  - Kostnaður 1.500 kr. á dag. Hámark í mánuði er 50.000 kr. og markmiðið 2–3 viðskiptavinir.
  - Ísland, 25 ára og eldri, Advantage+ markhópur. Audience Network er undanskilið.
  - Fjórar auglýsingar: `fastverd`, `smidum`, `fyrireftir`, `gatlisti`.
  - Slóð:
    ```
    https://innst.is/?utm_source=facebook&utm_medium=paid&utm_campaign=fastverd&utm_content={{ad.name}}
    ```
- **UTM-nöfn:** lágstafir, engin bil, engir íslenskir stafir. `utm_campaign` er nýtt fyrir hverja herferð og `utm_content={{ad.name}}`. Ekki nota stutta hlekki í auglýsingum.
- **Hönnun auglýsinga og samfélagsmiðla** er í Claude-teikniborðum (artifacts):
  - „innst — auglýsingar“: https://claude.ai/artifact/CzyY5QY8km9zYAaGFCqgeL. Raðirnar eru „Í bið (áskrift)“, „Fast verð“ og „Nýjar · nóvember“.
  - „innst — samfélagsmiðlar“: https://claude.ai/artifact/AY2WqDFFqqa48XbBRfLB6J. Þar eru prófílmyndir, forsíðumyndir og tölvupóstundirskriftir.
  - Hönnun vefsins: https://claude.ai/artifact/E2Y6rQbe33VnPTXrbN6PXw
- **Skjöl:**
  - Markaðsherferð: https://claude.ai/artifact/GBcp6M4eSUZwg2zW3v4AUr
  - A/B-prófanir: https://claude.ai/artifact/W2uWaDNDsjJ3r1ySYUi8Ci

## Áætluð verkefni

- **„innst mánaðaryfirlit“** keyrir 1. hvers mánaðar kl. 08:39 að íslenskum tíma.
  - Það telur fyrirspurnir síðasta mánaðar úr Netlify og flokkar þær eftir uppruna og tegund.
  - Það bætir við Search Console tölum ef tenging er til. Annars kemur hlekkur á þær.
- **Migadu:** prufutíminn átti að renna út 24. nóv. 2026. Staðfesta að greidd leið sé valin, Micro eða Mini.

## Opin atriði

- Kennitala, heimilisfang og VSK-númer á vefinn þegar fyrirtækið er skráð
- Greiðslusíða. Síðan má birta aftur áskrift, hýsingu og Umsjón.
- Lögfræðingur eða endurskoðandi les yfir `skilmalar.html`
- Myndir af Axel og Ólafi
