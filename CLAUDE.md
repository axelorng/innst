# innst — samhengi fyrir Claude

innst er íslensk vefstofa bræðranna **Axels Arnar Gíslasonar** og **Ólafs Rafns Gíslasonar**.
- **Axel** sér um vefhönnun og markaðsmál, axel@innst.is. Hann er viðurkenndur stafrænn markaðssérfræðingur og útskrifaður úr Viðurkenndri vefumsjón.
- **Ólafur** sér um forritun, vefi og öpp, olafur@innst.is. Hann er af forritunarbraut HR.

Vefurinn innst.is selur vandaða, sérforritaða vefi á föstu verði. Vefstofan er fyrir öll fyrirtæki, ekki bara íslensk þjónustufyrirtæki.

Þessi skrá geymir allt sem kom fram í löngu Claude-samtali um verkefnið, frá október til nóvember 2026, svo nýjar lotur geti haldið áfram frá sama stað. Tæknilegar upplýsingar um skrár, formið og falda hluta eru líka í `README.md`: lestu hana líka.

---

## 1. Vinnureglur (skylda)

- **Tungumál:** allt efni á vefnum og í markaðsefni er á íslensku. Vandaðu málfarið og beygingar og lestu yfir. Svaraðu Axel á því tungumáli sem hann skrifar á, íslensku eða ensku.
- **Git:** búa til grein → PR → **sameina aðeins þegar Axel biður um það** („merge“, „push and merge“, „sameinaðu“). Notaðu squash merge.
  - Aldrei force-push eða endurskrifa `main`.
  - Höfundur commita er Claude <noreply@anthropic.com>.
  - Merge-commit sem GitHub býr til er Verified og er í lagi.
- **Lykilorð og greiðslur:** Claude slær aldrei inn lykilorð, greiðslukort eða kóða. Axel skráir sig sjálfur inn, t.d. á Cloudflare, Meta og Migadu.
- **Eyðingar og stillingar** á þjónustum (DNS, Netlify, Migadu): spyrja fyrst nema Axel hafi beðið um nákvæmlega það.
- **Markaðsefni** (færslur, auglýsingar, textar):
  - Stutt og hnitmiðað. Á að grípa athygli á fyrstu 0,46 sekúndunum, sama tíma og innst.is tekur að opnast.
  - Engir langir textar. Fyrsta lína grípur, ein til tvær línur fylgja, svo hlekkur.
  - Myndin ber skilaboðin og textinn styður hana.
- **Orðalag:**
  - Forðast „hleðst“ og „hlaðast“ um hraða vefsins, því það minnir á rafbíla. Nota „opnast“ og engin ⚡.
  - Segja „sérforritað“. Ekki segja „ekki sniðmát“ og ekki „fyrir íslensk þjónustufyrirtæki“.
  - Skrifa „inn að kjarna“ en aldrei „innað“.
- **Ekki nefna Axel og Ólaf** í auglýsingum eða færslum. Efnið á að fjalla um innst og þjónustuna.
- **PDF-skjöl** eru aðeins uppfærð þegar Axel biður sérstaklega um það.
- **Engin uppdiktuð dæmi** sýnd sem raunveruleg verk eða umsagnir. Dæmi eru merkt „DÆMI“, t.d. á fyrir/eftir-myndinni.
- **Tölur eins og „2 laus pláss“** má aðeins nota ef þær eru sannar. Axel hafnaði þeirri hugmynd.

---

## 2. Vefurinn

### Tækni
- Kyrrstæð HTML-síða án byggingarskrefs. Síðurnar eru `index.html`, `personuvernd.html`, `skilmalar.html` og `takk.html`.
- Sameiginlegt CSS undirsíðna er í `assets/sidur.css`.
- Letrið er hýst á vefnum sjálfum í `assets/letur/` (`manrope.woff`, `inter.woff`, `letur.css`), aðeins latneskir og íslenskir stafir.
  - Ef þarf að búa til ný letursnið: fyrst taka út stafamengið (subset) og síðan festa breytilega letrið (instance), ekki öfugt.
- Flipar eru gerðir með CSS-útvarpshnöppum (radio). `[hidden]{display:none !important}` er í CSS.
- Merki, tákn og prófílmyndir eru í `assets/merki/`.
  - `innst-takn-hvitt-256.png` er fyrir dökku tölvupóstundirskriftirnar.
- Skjámyndir verka eru í `assets/verkefni/`: `verkstyring.jpg` og `gisli.jpg`.

### Útlit
- **Slagorð:** „Vandað inn að kjarna.“ Það var stytt úr „Vandað alla leið inn að kjarna“.
- **Litir:**
  - dökkblár `#08111D` og `#0F1B2A`
  - ljós `#EEF3F7`, ljósblágrár `#E2EAF1`
  - rauður kjarni `#C8361B`
  - grár texti `#CDD7E2` og `#3A4A5C`
  - millilitir `#13233A`, `#1F3350`, `#8FB3D3`
- **Merkið:** tveir ávalir ferningar hvor inni í öðrum, með rauðum kjarna í miðjunni, og orðmerkið „innst“ með rauðum punkti yfir i-inu. Hugmyndin er „innst inni“: dýpt, kjarni, það sem er undir yfirborðinu.
- **Letur:** Manrope 800 í fyrirsögnum (letter-spacing ≈ −0.045em) og Inter í meginmáli.

### Innihald forsíðu (staðan 25. nóv. 2026, PR #12)
- **Valmynd:** Verð, Ferlið, Kjarninn og Spurningar.
  - Kjarninn er falinn undir 480px breidd (`.nav-tolva`) svo valmyndin brotni ekki í síma.
- **Hetja:**
  - h1: „Vandað inn að kjarna.“
  - Texti: „Hraðir og vandaðir vefir, smíðaðir frá grunni á föstu verði.“
  - Hnappar: „Sjá verð“ og „Bóka fund“ (fer á `#fyrirspurn`).
  - Merkimiðar: „Lendingarsíða frá 59.990 kr.“, „Fast verð“ og „Sérforritað“.
- **Tekið út af ásetningi:** yfirlínan „Íslensk vefstofa“, kaflanúmerin „01 — Verð“ o.s.frv., og númerin á skrefunum í Ferlinu.
- **Verð:** „Hversu djúpt viltu fara?“ Flipinn Staðgreiða er sjálfvalinn og Áskrift er falin.
- **Ferlið:** „Frá yfirborði að kjarna, og aftur upp“, í fjórum skrefum: Yfirborðið, Undir yfirborðið, Kjarninn og Upp á yfirborðið.
- **Kjarninn:** „Það sem skiptir mestu sést ekki“. Fjórir punktar: Hreinn kóði, Hraði („Opnast á augabragði, líka í símanum uppi á heiði“), Öryggi og Mældur árangur.
- **Algengar spurningar:** verð, lén (skráð hjá ISNIC á nafni viðskiptavinar), eignarhald, breytingar á 14.990 kr./klst., og hvenær þarf fund.
- **Form:** „Segðu okkur frá fyrirtækinu þínu“, svarað innan sólarhrings.
  - Valmöguleikar: Lendingarsíðu, Fyrirtækjavef, Sérlausn, Sýnileika og Ekki viss enn.
  - Umsjón og Vöxtur eru faldir í HTML-athugasemd.
- **Meta description:** „Vandað inn að kjarna. innst er íslensk vefstofa sem smíðar hraðar og vandaðar vefsíður á föstu verði.“
- **Schema:** `priceRange` „59.990 kr. – 109.990 kr. (án vsk)“.

### Verð (öll án vsk)
**Sýnileg, greitt einu sinni og vefurinn er eign viðskiptavinar:**
- Lendingarsíða 59.990 kr. Ein síða, sérhönnuð í þeirra litum, virkar í síma og tölvu, með samskiptaformi, korti, opnunartímum, uppsetningu fyrir Google og tengingu við lén.
- Fyrirtækjavefur 109.990 kr. Allt að 5 síður, fréttir eða blogg og fyrirspurnar- eða tilboðsform.
- Sérlausn á tilboði eftir ókeypis 20 mínútna fund. Til dæmis bókanir, fleiri síður og tungumál, innskráning og tengingar við bókhald eða CRM.
- Sýnileiki 19.990 kr. eingreiðsla fyrir þá sem eiga vef. Google-fyrirtækjasíða, tenging við Search Console og nýir titlar og lýsingar.
- Breytingar eftir afhendingu 14.990 kr./klst. Tvær umferðir af breytingum á hönnun fylgja fyrir birtingu.

**Falið þar til greiðslusíða („borga“-síða) er komin** (nánar í `README.md`):
- Áskrift 12.990 kr. á mánuði (lendingarsíða) og 18.990 kr. á mánuði (fyrirtækjavefur).
  - Ekkert stofngjald, 12 mánaða binding og 1 vinnustund á mánuði.
  - Uppkaup eftir 12 mánuði: 29.990 eða 49.990 kr.
  - Áskriftin er um 40% dýrari en staðgreiðsla, samkvæmt ákvörðun Axels.
- Hýsing fyrir staðgreidda vefi 3.990 kr. á mánuði.
- Umsjón 4.990 kr. á mánuði (1 klst.) og Vöxtur 19.990 kr. á mánuði (3 klst., mánaðaryfirlit, leitarvélabestun).
- Vefverslun frá 199.990 kr. + 6.990 kr. á mánuði („Bráðum“), smáforrit („Væntanlegt“), Verkin og teymishlutinn.

### Annað á vefnum
- **Kennitala, heimilisfang og VSK** eru ekki komin. Þau eru falin með `<span hidden>` í fætinum, persónuvernd og skilmálum.
- **Netfang á vefnum:** alltaf hallo@innst.is. Ekkert símanúmer og enginn bókunarhlekkur.
- **Persónuvernd** nefnir Cloudflare Web Analytics, Netlify (vinnsluaðila formsins), Cloudflare (DNS), reikningsupplýsingar, „uppruna“-reitinn og hallo@.
  - Ef Meta fyrirspurnaform verður einhvern tímann notað þarf að bæta því við.

### Verk í safni
- **Verkstýring ehf.:** fyrirtækjavefur með verkbeiðnum á netinu, á íslensku og ensku. Ný útgáfa er á verkstyring.netlify.app.
- **Gísli Rafn Ólafsson:** persónulegur vefur ráðgjafa og fyrirlesara, gislio.gislio.workers.dev.

---

## 3. Hýsing og innviðir

- **GitHub:** `axelorng/innst`. **Netlify** birtir `main` sjálfkrafa.
  - Netlify-verkefni: `313a6e94-dd6f-4573-9406-23bb201accbb` (innst.netlify.app).
  - Forskoðanir eru læstar á bak við innskráningu. Let's Encrypt skírteini er virkt fyrir innst.is.
  - Tilkynningar Netlify fara á hallo@innst.is.
- **Form:** Netlify Forms, formið „samband“ (formId `6ade70634872188a6ac2c414`).
  - Netfangsreiturinn heitir `email`, svo hann verður Reply-To.
  - Ruslpóstsvörn er falinn reitur (honeypot).
  - Falinn reitur `uppruni` fyllist úr `utm_source / utm_campaign / utm_content` eða úr „vísað frá <lén>“. Ef hvorugt er til stendur „beint“. Gildið geymist í sessionStorage undir lyklinum `innst-uppruni` og engar vafrakökur eru notaðar.
  - Prófað á lifandi vef 24. nóv.: `?utm_source=facebook&utm_campaign=fastverd&utm_content=fastverd` gaf „facebook / fastverd / fastverd“.
- **DNS:** hjá Cloudflare, allt stillt á „DNS only“ (grátt ský).
  - `@` og `www` eru CNAME á `innst.netlify.app`.
  - **Migadu-færslur, ekki snerta:**
    - MX `aspmx1.migadu.com` og `aspmx2.migadu.com`
    - SPF
    - DKIM key1–3 (CNAME)
    - `_dmarc`
    - `autoconfig` CNAME
    - TXT `hosted-email-verify=ipbox2if`
  - **TXT `google-site-verification=pV31XYzwOBRxYhpCc9w8sTBFFQ-Zo7g9fSti5eFOtHo`** staðfestir Search Console og **má ekki eyða**.
  - **Saga:** innst.is benti áður á Cloudflare Worker („innst“) með kyrrstæðu afriti af vefnum, svo formið skilaði villu 405. Workerinn var aftengdur léninu (ekki eytt) og CNAME settar á Netlify, sem lagaði það.
- **Tölvupóstur:** Migadu.
  - Pósthólfin eru axel@ og olafur@. hallo@ er samnefni (alias) og sendir í pósthólf.
  - **IMAP:** `imap.migadu.com`, port 993, SSL.
  - **SMTP:** `smtp.migadu.com`, port 465 SSL, eða 587 STARTTLS.
  - Notandanafn er fullt netfang. Lykilorðið er lykilorð pósthólfsins, ekki stjórnborðsins.
  - Til að senda sem hallo@ í iPhone Mail er því bætt við sem aukanetfangi.
  - **Áskriftarleiðir:** Micro $19 á ári (20 send bréf á dag fyrir allan aðganginn) og Mini $90 á ári (100 á dag, og þarf fyrir lén viðskiptavina). Prufutíminn átti að renna út 24. nóv. 2026.
  - **Framtíðarhugmynd:** bjóða viðskiptavinum tölvupóst á eigin léni gegn gjaldi, án ábyrgðar á uppitíma.
- **Mælingar:**
  - Cloudflare Web Analytics er sett inn handvirkt fyrir `</body>` á öllum síðum (token `2d3fbfefe7d34773bc6aa583acd78531`, opinbert gildi).
  - Fyrsta mæling: 30 heimsóknir, og vefurinn opnast á um 459 ms. „0,46 s“ í auglýsingum byggir á því.
- **Enginn Meta pixel**, samkvæmt ákvörðun. Hann krefst vafrakökuborða vegna GDPR, hægir á vefnum og gerir lítið gagn við litla umferð (Meta þarf um 50 viðskipti á viku).
  - Endurskoða ef þörf verður á endurmarkaðssetningu (retargeting) eða umferð fer í nokkur hundruð heimsóknir á viku.
- **Google Search Console:**
  - Lénseignin `sc-domain:innst.is` var staðfest 24. nóv. 2026 með DNS-færslu.
  - `https://innst.is/sitemap.xml` er sent inn og fann 3 síður.
  - Fyrstu tölur birtast undir Performance eftir 2–3 daga.
  - Engin opinber Google-tenging er til fyrir Claude. Þriðju aðila kostir eru Windsor.ai og Supermetrics, en ekkert hefur verið tengt.
- **Stuttir hlekkir** í `_redirects` (302):
  - `/ig` → `/?utm_source=instagram&utm_medium=social&utm_campaign=bio`
  - `/fb` → `/?utm_source=facebook&utm_medium=social&utm_campaign=sida`

---

## 4. Leitarvélar — staðan 24. nóv. 2026

- `site:innst.is` sýnir 3 síður í Google: forsíðuna, persónuvernd og skilmála.
- innst.is var **ekki á topp ~30** fyrir: vefsíðugerð, vefsíðuhönnun, vefhönnun, heimasíða fyrir fyrirtæki og vefsíða fyrir fyrirtæki.
  - Ekki náðist að prófa fleiri orð, því Google bað um CAPTCHA. Ekki reyna að komast fram hjá því.
- **Keppinautar á fyrstu síðu:** vefsidugerd.com, vefsida.is, vefsidugerd.is, sahara.is, vefhonnun.is, vefsiduhonnun.is, 29.is, herognu.is, salt.is, hugsmidjan.is, norda.is, wpvefhonnun.is, avista.is, vefmynd.is, sidavefhonnun.is, webpro.is, origo.is og is.site123.com.
- **Leitarorð sem skipta máli:** heimasíða verð, vefsíðugerð, vefsíða fyrir fyrirtæki, búa til heimasíðu, vefhönnun, vefsíða verð, vefstofa og lendingarsíða.

---

## 5. Markaðssetning

### Stefna
- **Markmið:** landa 2–3 fyrstu viðskiptavinunum til að afla fjár og fjárfesta frekar í innst.
- **Kostnaðaráætlun:** 50.000 kr. fyrsta mánuðinn.
- **Herferðarskjal:** 16. nóv.–13. des. 2026.
- **Loforð til viðskiptavina:** mánaðarlegt yfirlit yfir hvað vefurinn skilar.

### Samfélagsmiðlar
- Facebook-síðan og Instagram-aðgangurinn innst eru virk og tengd. Axel setti þau upp sjálfur.
- Hlekkur í Instagram-bio er innst.is/ig, og í Facebook-færslum innst.is/fb.
- Bio á báðum miðlum á að vera „Vandað inn að kjarna.“, og Axel átti eftir að uppfæra þau.
- Nýja Facebook-forsíðumyndin átti eftir að fara inn.
- **Fyrstu þrjár færslurnar** voru gerðar í október og nóvember. Færsla 3 var hraðafærslan „0,46 sekúndur. Svo fljótt opnast innst.is.“
- **Ráð um birtingar:** byrja á „Fast verð“ og setja hinar inn með 2–3 daga millibili. Geyma „Nýtt ár“ til 27.–30. desember.
- **Sögur (stories):** enginn texti, bara hlekkjalímmiði á innst.is/fb eða innst.is/ig.

### Textar (Facebook / Instagram)
Á Instagram kemur alltaf „Hlekkur í bio.“ í stað hlekksins, og 2–3 myllumerki.

| Auglýsing | Texti | Instagram-myllumerki |
|---|---|---|
| Svona verður vefur til | Smíðað frá grunni. Fast verð frá 59.990 kr. 👉 innst.is/fb | #vefsíða #vefhönnun #innst |
| Fyrir / eftir | Vefurinn þinn á að vinna fyrir þig. 👉 innst.is/fb | #vefsíða #vefhönnun #innst |
| Gátlisti (og varaútgáfa) | Ef svarið er nei, getum við hjálpað. 👉 innst.is/fb | #vefsíða #vefhönnun #innst |
| Fast verð | Vefsíða á föstu verði. 59.990 kr. Greitt einu sinni. Þín eign. | #vefsíða #vefhönnun #innst |
| Pakkarnir | Ein síða, nokkrar síður eða sérlausn. Þú velur. | #vefsíða #fyrirtæki #innst |
| Fyrirtækjavefur | Allt að 5 síður. 109.990 kr. Einn vefur fyrir allt fyrirtækið. | #fyrirtækjavefur #vefsíða #innst |
| Hraði | 0,46 sekúndur. Svo fljótt opnast innst.is. Hraður vefur heldur fólki. | #vefsíða #vefhönnun #innst |
| Nýtt ár | Ný vefsíða fyrir nýtt ár. Fast verð frá 59.990 kr. | #nýttár #vefsíða #innst |

### Auglýsingamyndir
- **Teikniborðið „innst — auglýsingar“:** https://claude.ai/artifact/CzyY5QY8km9zYAaGFCqgeL (Design artifact)
  - **„Í bið (áskrift)“:** Main, Post3, Story og Val. Ekki birta fyrr en greiðslusíðan er komin.
  - **Tilbúið, eldri:**
    - Post2: „Facebook-síða er ekki heimasíða“, A/B-próf 1 B
    - Stadgreitt og StadgreittSaga: A/B-próf 1 A
    - LinkAd: Sýnileiki 19.990 kr.
    - SearchAd: Google-leitarauglýsingar A og B
  - **„Fast verð“:** FastVerd, FastVerdSaga, Pakkar, Fyrirtaekjavefur, Hradi og NyttAr.
  - **„Nýjar · nóvember“:** NySmidum, NyFyrirEftir, NyGatlisti, NyGatlisti2 og Saga-útgáfur þeirra (1080×1920).
    - Fyrir/eftir notar tilbúna „Vefurinn þinn“ sem dæmi og er merkt „DÆMI“.
    - Gátlistinn: „Gerir vefurinn þinn þetta?“ með Opnast strax, Virkar vel í síma og Fær fólk til að hafa samband.
    - Varaútgáfa gátlistans: Finnst á Google, Lítur fagmannlega út og Selur fyrir þig.
  - **24. nóv. var allt samræmt við vefinn:**
    - „Ókeypis vefskoðun“ tekin út, því hún er ekki á vefnum.
    - Hnappar segja „Bóka fund“.
    - Textar styttir.
- **Zip-skrá `innst-auglysingar.zip`** var send Axel 24. nóv.:
  - `1-Tilbuid-til-birtingar/`: Faerslur-1080x1080 (11), Sogur-1080x1920 (6), Hlekkjaauglysing-1200x628, Google-leitarauglysingar og textar.txt
  - `2-I-bid-askrift/`
- **Samfélagsmiðlaborðið „innst — samfélagsmiðlar“:** https://claude.ai/artifact/AY2WqDFFqqa48XbBRfLB6J
  - Prófílmyndir, Facebook- og LinkedIn-forsíður með „Vandað inn að kjarna.“
  - Tölvupóstundirskriftir í hvítri og dökkblárri útgáfu. hallo@-undirskriftin notar slagorðið sem hlutverkslínu.
  - Axel átti eftir að setja nýju hallo@-undirskriftina inn í vefpóstinn.
- **Hönnun vefsins:** https://claude.ai/artifact/E2Y6rQbe33VnPTXrbN6PXw. Hún er aðeins að hluta samstillt við lifandi vef.
- **Merki:** https://claude.ai/artifact/7uKZXD9tH42Xap2yVdkMEE

### Skjöl
- **Markaðsherferð, opnun:** https://claude.ai/artifact/GBcp6M4eSUZwg2zW3v4AUr. 50 þús. kr., 16. nóv.–13. des., markmið 2–3 viðskiptavinir.
- **A/B-prófanir:** https://claude.ai/artifact/W2uWaDNDsjJ3r1ySYUi8Ci
  - Próf 1: verð á móti vandamáli á Facebook og Instagram, UTM-gildin `verd` og `vandamal`.
  - Próf 2: fyrirsagnir í Google-leitarauglýsingum.

### Meta-herferðin (sett upp 24.–25. nóv. 2026 í Ads Manager)
**Ákvarðanir og ástæður:**
- **Ads Manager, ekki „Boost post“.** Boost gefur aðallega like.
- **Traffic á vefinn, ekki Meta fyrirspurnaform.** Vefurinn er besta söluefnið og fyrirspurnir koma inn í mánaðaryfirlitið með uppruna.
  - Meta form gefa ódýrari en veikari fyrirspurnir, sem fara bara í Leads Center.
  - Mögulegt síðar: skipta kostnaðinum í tvennt og prófa bæði.
- **Manual traffic campaign**, ekki „Recommended“, svo hægt sé að taka Audience Network út.
- **Enginn tímarammi á birtingum (dayparting).** Hann sparar ekki pening, því sama upphæð eyðist á færri tímum, og krefst lifetime budget. Hægt að skoða Breakdown → Time of day eftir 1–2 vikur.

**Stillingar:**
- **Herferð:** Traffic, Campaign budget (Advantage), 1.500 kr. á dag, bid strategy Highest volume.
- **Auglýsingasett** „Ísland 25-65 – Advantage+“:
  - Conversion location Website og Maximise number of link clicks. Landing page views þarf pixel.
  - Iceland, lágmarksaldur 25 í Audience controls, engin tungumál og engin áhugamál.
  - Advantage+ placements, Audience Network undanskilið.
  - Beneficiary og payer: innst.
  - Byrjar morguninn eftir uppsetningu og hefur engan lokadag.
- **Auglýsingar**, allar í sama setti:

  | Nafn | Mynd | Fyrirsögn |
  |---|---|---|
  | `fastverd` | 05-fast-verd | „Vefsíða frá 59.990 kr.“ |
  | `smidum` | 01-svona-verdur-vefur-til | „Svona verður vefur til“ |
  | `fyrireftir` | 02-fyrir-eftir | „Sama fyrirtæki. Nýr vefur.“ |
  | `gatlisti` | 03-gatlisti | „Fast verð frá 59.990 kr.“ |

  - Call to action: Learn more. Display link: innst.is. Description: „Fast verð · innst.is“.
  - Allar Advantage+ creative enhancements eru af: engin AI-texti, þýðing, tónlist eða myndbreyting.
  - **Slóð**, sú sama á öllum. Meta fyllir `{{ad.name}}` inn sjálft og það á að standa svona í reitnum:
    ```
    https://innst.is/?utm_source=facebook&utm_medium=paid&utm_campaign=fastverd&utm_content={{ad.name}}
    ```

**Næstu skref:**
- **Ekki breyta neinu í 7 daga** meðan Meta er að læra.
- Fylgjast með CTR (gott ef yfir 1%) og CPC (gott ef undir um 100 kr.).
- Eftir 7 daga: slökkva á auglýsingunni með lægsta CTR.
- Ef herferðin fær smelli en engar fyrirspurnir eftir 2 vikur: skoða það sem fólk sér fyrst á vefnum.

### UTM-reglur
- Lágstafir, engin bil og engir íslenskir stafir, t.d. `fastverd`, `nyttar-2027`, `synileiki`.
- `utm_source` er `facebook` (líka fyrir Instagram-birtingar í Meta), `google` eða `instagram` (bio).
- `utm_medium` er `paid` fyrir auglýsingar og `social` fyrir lífrænt efni.
- `utm_campaign` er nýtt fyrir hverja herferð og `utm_content={{ad.name}}`.
- Ekki nota stutta hlekki í auglýsingum. Þeir eru fyrir staði þar sem fólk sér eða slær inn slóðina: bio, færslur og prent.

---

## 6. Áætluð verkefni (scheduled tasks)

- **„innst mánaðaryfirlit“** (`trig_01PjNZgxBgewRi5aQexDYhBc`) keyrir 1. hvers mánaðar kl. 08:39 að íslenskum tíma. Fyrsta keyrsla er 1. des. 2026 og það sendir tilkynningu í síma.
  - Sækir fyrirspurnir síðasta mánaðar úr Netlify-forminu (aðeins lesið).
  - Telur þær og ber saman við mánuðinn á undan.
  - Flokkar eftir `uppruni` og `tegund`.
  - Listar dagsetningu, nafn, fyrirtæki og þjónustu.
  - Bætir við Search Console tölum ef tenging er til, annars hlekk á Performance.
  - Endar á ábendingu og er undir 300 orðum.
- **Migadu-áminning** var send 21. nóv.

---

## 7. Verklag Claude (tæknileg atriði)

- **Myndir búnar til í kóða:**
  - HTML með inline stílum og `letur.css`, gert að PNG með Playwright (`require('playwright')`, chromium).
  - Stærðir: færslur 1080×1080, sögur 1080×1920, hlekkjaauglýsing 1200×628.
  - Í sögum er autt svæði efst (um 250px) og neðst (um 360px) fyrir viðmót Instagram og Facebook.
- **Design-teikniborð:**
  - Uppfært með Artifact-tólinu: lesa fyrst (`action: read`), svo publish með `root` = möppunni sem geymir `project/`, `file_path` = `project/canvas.json` og `files` = breyttar `.dc.html`.
  - Hvert artboard er `.dc.html` með `<x-dc>`, inline stílum, Google Fonts `<link>` í `<helmet>` og `data-dc-script` blokk.
- **Claude Docs:** herferðarskjölin eru Docs-artifacts. Uppfæra með find/replace.
- **Innbyggði vafrinn** (Claude-appið) var notaður fyrir Google-leit, Search Console og Cloudflare. Axel þarf að vera skráður inn sjálfur.

---

## 8. Opin atriði og hugmyndir

- Kennitala, heimilisfang og VSK-númer á vefinn þegar fyrirtækið er skráð.
- **Greiðslusíða.** Síðan má birta aftur áskrift, hýsingu, Umsjón og Vöxt.
- Lögfræðingur eða endurskoðandi les yfir `skilmalar.html` fyrir fyrsta samning.
- Myndir af Axel og Ólafi, og birta teymishlutann og Verkin þegar þau eru tilbúin.
- Staðfesta að greidd Migadu-leið sé valin.
- Uppfæra Facebook- og Instagram-bio og forsíðumynd, og setja hallo@-undirskriftina inn.
- Skoða Search Console tölur þegar þær koma. Mögulega tengja Search Console við mánaðaryfirlitið í gegnum þriðja aðila.
- Endurskoða Meta-herferðina eftir 7 daga og 2 vikur, sjá kafla 5.
- **Seinna:** vefverslun, smáforrit, tölvupóstþjónusta fyrir viðskiptavini, og hugsanlega Meta pixel með kökuborða.
