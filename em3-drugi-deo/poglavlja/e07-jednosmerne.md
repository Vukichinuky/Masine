# Tema 7 — Mašine jednosmerne struje na ovom ispitu: neutralna zona i srodna pitanja

## Zašto se ovo pita

Mašina jednosmerne struje se na ovom ispitu pojavljuje u primerima pitanja za vežbu, i to kroz pitanje koje je čist test razumevanja: *„Objasnite na koji način biste odredili neutralnu zonu motora jednosmerne struje sa nezavisnom pobudom."* To pitanje proverava da li student ume da **iskoristi transformatorski princip na mašini koja u normalnom radu uopšte nije transformator** — da armaturu koja miruje tretira kao sekundar, a pobudu kao primar. Uz to, mašina jednosmerne struje se u beleškama pominje na još dva mesta koja se lako uvezuju u isto pitanje:

1. **komutacija** — iz beležaka: zalet mašine jednosmerne struje se radi **kontrolisano**, velike mašine se ne pokreću direktno zbog ogromnih struja, a **komutacija ulazi u problem ako kroz mašinu prolazi više od $2 I_n$** — dakle profesor komutaciju tretira kao ozbiljno ograničenje, a neutralna zona je uslov da komutacija uopšte bude zdrava;
2. **rezolver** (sinusni i kosinusni namotaj) — srodni uređaj kojim se određuje **položaj rotora**, obrađen u beleškama i naglašen („Primarni namotaj se pobuđuje NAIZMENIČNOM strujom a ne JEDNOSMERNOM!!!") — ista transformatorska logika kao kod određivanja neutralne zone.

Ispitivač očekuje: kratku sliku konstrukcije (šta je armatura, kolektor, četkice, pobuda), definiciju neutralne zone (geometrijska i magnetna, i šta ih razdvaja), **zašto** četkice moraju stajati u njoj, i **postupak** indukcione (transformatorske) metode korak po korak, sa šemom i izborom instrumenata.

> **Prevod na običan jezik:** Neutralna zona je mesto na obodu armature gde je magnetno polje glavnih polova jednako nuli — tačno „između polova". Četkice moraju da kratko spajaju baš one navojke koje se u tom trenutku nalaze u neutralnoj zoni, jer se u navojku u kojem nema polja ne indukuje napon, pa kroz kratko spojeni navojak ne teče štetna struja i komutacija prolazi **bez varničenja**. Neutralna zona se nalazi ovako: rotor se **ukoči** (miruje), pobuda se napoji **naizmeničnom** (ili prekidanom jednosmernom) strujom, pa mašina postane transformator — pobuda je primar, armatura sekundar. Na četkice se prisloni osetljiv milivoltmetar i **most četkica se polako pomera dok skretanje ne padne na nulu**: tada fluks polova ne obuhvata (neto) navojke između četkica, četkice su u neutralnoj zoni i tu se učvrste.

## Teorija — sve što moraš znati

### Konstrukcija mašine jednosmerne struje sa nezavisnom pobudom

Za odgovor na ispitu dovoljna je funkcionalna slika, ali svaki pojam mora biti definisan:

- **Stator (induktor):** nosi **glavne polove** sa **pobudnim namotajem**. Kod **nezavisne pobude** pobudni namotaj se napaja iz **posebnog jednosmernog izvora**, nezavisnog od armaturnog kola — pobudna struja $I_f$ stvara glavni fluks $\Phi$ usmeren duž ose polova (tzv. **podužna osa**, osa $d$). Iz beležaka (pravilo za procene): snaga pobude se uzima kao **$0{,}5\,\%$ ukupne snage mašine**.
- **Rotor (indukt, armatura):** nosi **armaturni namotaj** raspoređen u žlebovima po obodu. Krajevi sekcija namotaja izvedeni su na **kolektor** (komutator) — venac međusobno izolovanih bakarnih **lamela** koji se obrće zajedno sa rotorom.
- **Četkice:** grafitni kontakti koji klize po kolektoru i vezuju obrtni namotaj sa spoljašnjim (mirujućim) krajevima. Četkice su smeštene na **mostu (držaču) četkica** koji se kod većine mašina može **olabaviti i zakretati po obodu** — upravo to zakretanje koristimo pri određivanju neutralne zone.
- **Kolektor + četkice = mehanički ispravljač/invertor:** u svakoj sekciji armaturnog namotaja struja je naizmenična (menja smer kad sekcija prođe ispod suprotnog pola), a kolektor sa četkicama tu struju prema spoljašnjem kolu „ispravlja". Trenutak u kojem četkica premosti dve susedne lamele i struja sekcije **promeni smer** zove se **komutacija**.
- Veće mašine imaju još **pomoćne polove** (uski polovi između glavnih, namotaj vezan **na red sa armaturom**) i eventualno **kompenzacioni namotaj** — o tome u varijaciji V2.

Dve osnovne jednačine koje se ovde koriste (obe su posledica $e = \frac{d\Psi}{dt}$, tj. indukovane ems u provodniku koji se kreće u polju):

$$E = k\,\Phi\,\omega \qquad \text{(indukovani napon armature)}, \qquad M = k\,\Phi\,I_a \qquad \text{(elektromagnetni momenat)},$$

gde je $k$ konstruktivna konstanta mašine, $\Phi$ fluks po polu, $\omega$ ugaona brzina, $I_a$ struja armature. Iz prve jednačine sledi i logika tahogeneratora (Tema 2): konstantan fluks $\Rightarrow$ napon srazmeran brzini.

### Šta je neutralna zona — geometrijska i magnetna

- **Geometrijska neutralna zona** je linija (ravan) po obodu armature **tačno na sredini između dva susedna glavna pola** — geometrijski upravna na osu polova. Određena je čistom geometrijom mašine i ne zavisi od režima rada.
- **Magnetna neutralna zona** je mesto na obodu gde je **rezultantna magnetna indukcija $B = 0$** — provodnik koji se u tom trenutku tamo nalazi ne seče linije polja i u njemu se **ne indukuje ems** ($e = B\,l\,v = 0$).

**U praznom hodu** (kroz armaturu ne teče struja) polje pravi samo pobuda, pa se magnetna neutralna zona **poklapa sa geometrijskom**. **Pod opterećenjem** kroz armaturu teče struja $I_a$ koja pravi sopstvenu magnetopobudnu silu — **reakciju indukta**. Osa armaturne mps leži duž **ose četkica**; kada su četkice u neutralnoj zoni, reakcija indukta je **poprečna** (upravna na glavni fluks, osa $q$). Poprečno polje se sabira sa glavnim poljem: pod jednom ivicom pola polje pojača, pod drugom oslabi — rezultat je da se tačka $B=0$ **pomeri po obodu**:

- kod **generatora** — u **smeru obrtanja**;
- kod **motora** — **suprotno smeru obrtanja**;
- pomeraj je **utoliko veći ukoliko je opterećenje veće** (jer je reakcija indukta srazmerna $I_a$).

Dakle: geometrijska neutralna zona stoji, a magnetna „beži" sa opterećenjem. Zato se kod mašina bez pomoćnih polova četkice nekada pomeraju za ugao koji odgovara tipičnom opterećenju, a kod mašina sa pomoćnim polovima četkice stoje u geometrijskoj neutralnoj zoni, a „bežanje" magnetne neutralne zone lokalno poništavaju pomoćni polovi (varijacija V2).

### Zašto četkice moraju stajati u neutralnoj zoni — komutacija bez varničenja

U trenutku komutacije četkica premošćava dve susedne lamele, pa je sekcija koja komutira **kratko spojena preko četkice**. Šta se dešava zavisi od toga gde se ta sekcija fizički nalazi:

1. **Sekcija u neutralnoj zoni ($B=0$):** rotaciona ems u njoj je nula, kroz kratko spojenu sekciju ne teče dodatna struja, struja sekcije se mirno preokrene i četkica napusti lamelu bez posledica — **komutacija bez varničenja**.
2. **Sekcija van neutralne zone ($B\neq 0$):** u kratko spojenoj sekciji indukuje se rotaciona ems $e = B\,l\,v \neq 0$, pa kroz malu otpornost kratkog spoja protekne osetna **struja kratkog spoja**. Kad četkica sklizne sa lamele, ta struja se **naglo prekida u induktivnoj sekciji** — a nagli prekid struje kroz induktivnost znači veliki $L\,\frac{di}{dt}$, dakle naponski impuls i **električni luk (varnicu)** između lamele i četkice. (Ista fizika kao u Temi 1: zato se tamo RL kolo nikad ne prekida naglo — i zato voltmetar u UI metodi „nije fiksan".) Varničenje nagriza kolektor i četkice, a u težem slučaju prelazi u **kružnu vatru** po kolektoru.
3. **Dodatna posledica:** kada osa četkica nije upravna na osu polova, reakcija indukta dobija i **podužnu ($d$) komponentu** — srazmernu $\sin\beta$, gde je $\beta$ ugao zakretanja četkica iz neutralne zone. Ta komponenta **magnetiše ili razmagnetiše** glavno polje (znak zavisi od smera struje, tj. smera obrtanja), pa mašina u dva smera obrtanja radi **nesimetrično** — različite brzine kao motor, različiti naponi pod opterećenjem kao generator. Upravo na tome počiva pogonska provera (metoda 2 dole).

### Metoda 1 — indukciona (transformatorska) metoda: nulta metoda

Ideja: **isključiti rotacionu ems** (rotor miruje) i naterati mašinu da radi kao **transformator**:

- **armatura MIRUJE** — rotor se ne pogoni, po potrebi se i mehanički ukoči da ga slučajni momenat ne pomeri;
- **pobuda se napaja NAIZMENIČNOM strujom** (snižen naizmenični napon), ili **prekidanom jednosmernom strujom** (baterija + predotpor + prekidač koji se ritmično uklapa/isklapa) — bitno je samo da fluks polova **pulsira**, jer transformatorsku ems pravi $\frac{d\Phi}{dt}$, a njega nema pri konstantnoj jednosmernoj struji;
- na četkice se **prisloni osetljiv voltmetar/milivoltmetar** — armaturni namotaj između četkica je „sekundar";
- **most četkica se polako pomera** i traži se položaj u kojem je skretanje **NULA (minimum)** — to je neutralna zona; tu se most učvrsti.

**Zašto je napon nula baš u neutralnoj zoni?** Armaturni namotaj između dve četkice čini paralelne grane koje se protežu po obodu. Pulsirajući fluks polova prožima navojke tih grana: navojci pod jednim polom obuhvataju fluks jednog znaka, navojci pod drugim polom fluks suprotnog znaka. Kada je osa četkica **upravna na osu polova** (četkice u neutralnoj zoni), svaka grana obuhvata **jednake i suprotne** delove fluksa, pa je **ukupni fluksni obuhvat grane nula** — neto transformatorska ems između četkica je nula. Rečeno jezikom sprege: međuinduktivnost pobude i armature između četkica je

$$M(\beta) = M_{\max}\sin\beta \;\;\Rightarrow\;\; U_{\check{c}etkice} = U_{\max}\sin\beta \approx U_{\max}\,\beta \; \text{za malo } \beta,$$

gde je $\beta$ (električni) ugao zakretanja četkica iz neutralne zone. Dve posledice koje vredi izgovoriti na ispitu:

- metoda je **nulta metoda**, a nulte metode su najtačnije — ne zavisi od klase tačnosti instrumenta ni od vrednosti napona, nego samo od sposobnosti da se prepozna minimum;
- osetljivost oko nule je **najveća moguća** (izvod $\frac{dU}{d\beta}=U_{\max}\cos\beta$ je maksimalan baš u $\beta=0$), a napon **menja znak** pri prolasku kroz neutralnu zonu — kod prekidane jednosmerne struje impulsi skretanja galvanometra **promene smer**, što nulu čini nepogrešivo prepoznatljivom.

Napomena o instrumentu (detalj koji razdvaja ocene): pri **naizmeničnom** napajanju pobude signal na četkicama je naizmeničan — instrument sa **kretnim kalemom** bi pokazivao srednju vrednost, tj. **nulu svuda**, pa treba milivoltmetar za naizmenične veličine (sa kretnim gvožđem ili sa ispravljačem). Pri **prekidanoj jednosmernoj** struji koristi se osetljivi instrument **sa kretnim kalemom** (iz beležaka: kretni kalem je za jednosmerne veličine) — najbolje **galvanometar sa nulom na sredini skale**, da se vidi promena smera impulsa.

### Metoda 2 — provera u radu (pogonska provera)

Indukciona metoda daje neutralnu zonu **na mirnoj mašini** (bez reakcije indukta). Konačna potvrda se radi u pogonu:

- **varničenje:** mašina se pusti u rad (kao motor u praznom hodu pa pod opterećenjem) i posmatra se kolektor — ako su četkice u neutralnoj zoni, komutacija je **bez varničenja** (ili sa jedva primetnim iskricama) u **oba smera obrtanja**;
- **simetrija u dva smera:** mašina se pusti u **oba smera obrtanja** pod istim uslovima (isti napon, ista pobuda, isto opterećenje). Ako su četkice u neutralnoj zoni, podužne komponente reakcije indukta nema, pa su **brzine (kao motor)**, odnosno **naponi (kao generator pod opterećenjem)**, u oba smera **jednaki**. Ako nisu jednaki — četkice su zakrenute, i to na stranu koja se prepoznaje po tome u kom smeru mašina „beži" (magnetišuća komponenta smanjuje brzinu motora, razmagnetišuća je povećava; brojčani primer u varijaciji V1).

### Srodna tema iz beležaka — rezolver (sinusni i kosinusni namotaj)

Ista transformatorska logika, ali iskorišćena da se položaj rotora **izmeri**, a ne da se nađe nula. Iz beležaka: **rezolver** je uređaj za merenje brzine (asinhronog tipa) sa **primarnim namotajem na rotoru** i **dva sekundarna namotaja na statoru — sinusnim i kosinusnim — prostorno pomerenim za $90^\circ$** (otud im imena). **Primar se pobuđuje NAIZMENIČNOM strujom, a ne jednosmernom** (profesorov naglasak) i pravi naizmenično pulsaciono polje. Kako se rotor obrće, njegov položaj $\theta$ se „utiskuje" u flukseve koji prožimaju sinusni i kosinusni namotaj, pa su amplitude njihovih indukovanih napona srazmerne $\sin\theta$ i $\cos\theta$. Položaj rotora se dobija iz količnika:

$$\operatorname{tg}\theta = \frac{U_{\sin}}{U_{\cos}} \;\;\Rightarrow\;\; \theta = \operatorname{arctg}\frac{U_{\sin}}{U_{\cos}},$$

a praćenjem $\theta$ u vremenu i brzina. Koristi se u agresivnim sredinama (vlaga, prašina), gde optički enkoderi ne opstaju. Veza sa neutralnom zonom: u oba slučaja **naizmenična pobuda + transformatorska sprega zavisna od ugla** — kod rezolvera se ugao čita iz odnosa dva napona, kod neutralne zone se traži ugao u kojem je sprega (napon) **nula**.

## Oprema i šema merenja

Za indukcionu (transformatorsku) metodu treba:

1. **Izvor za pobudu — jedna od dve varijante:**
   - **naizmenični izvor sniženog napona:** mrežni napon preko **regulacionog autotransformatora** (ili razdvojnog transformatora) — napon se podiže postepeno od nule. Kako pobudni namotaj ima veliku induktivnost, na $50\ \mathrm{Hz}$ njegova impedansa $\omega L$ je ogromna, pa je struja i pri punom naponu vrlo mala (procena u modelu odgovora: reda $\mathrm{mA}$) — fluks je mali, ali za milivoltmetar sasvim dovoljan;
   - **prekidana jednosmerna struja:** **akumulator $12\ \mathrm{V}$** + **predotpor** (promenljiv, kreće se od najveće vrednosti) + **prekidač** koji se ritmično uklapa i isklapa. Ovo je isto napojno kolo kao kod UI metode iz Teme 1 — slika iz beležaka:

![UI merna šema — napojno kolo sa predotporom, prekidačem i namotajem](../slike/image3.jpeg)

**Slika —** merna šema iz beležaka (Tema 1): jednosmerni izvor (baterija), promenljivi predotpor, ampermetar, namotaj označen sa $L, R$ i voltmetar koji se samo „prislanja" (strelice). Napomena na slici podseća da se meri **namotaj** (ima induktivnost), a ne čist otpornik. Za našu svrhu iz nje se preuzima levi deo — **baterija + predotpor + prekidač + namotaj** — kao napojno kolo **pobude** u varijanti sa prekidanom jednosmernom strujom; umesto voltmetra na namotaju, kod određivanja neutralne zone milivoltmetar stoji **na četkicama armature**.

> **Kako čitati šemu (prilagođeno našem ogledu):** Na slici se vide: levo baterija (jednosmerni izvor, + i −); od plus pola **promenljivi predotpor** (njime se struja pobude svede na malu vrednost i ograniči $\frac{di}{dt}$); zatim **ampermetar sa kretnim kalemom** (kontroliše da struja pobude ne pređe izabranu vrednost); pa **namotaj** ($L, R$ — velika induktivnost!), na čije je priključke strelicama prislonjen voltmetar. Za naš ogled se u ovo kolo **docrtavaju dva elementa kojih na slici nema**: **prekidač** između izvora i predotpora (beleške ga i u Temi 1 zahtevaju — ovde se njime pobuda ritmično prekida i uspostavlja) i **zaštitni otpornik paralelno pobudnom namotaju** (vidi tačku 4); namotaj $L, R$ je sada **pobudni namotaj** mašine. Voltmetar sa slike se izostavlja — umesto njega se **milivoltmetar** prislanja na **četkice armature**: armatura je „sekundar" i u njenom kolu nema izvora.

2. **Milivoltmetar na četkicama:** osetljiv instrument malog opsega (npr. $0\ldots100\ \mathrm{mV}$ / $0\ldots1\ \mathrm{V}$, klasa $0{,}5$); za naizmeničnu varijantu instrument za naizmenične veličine (kretno gvožđe ili kretni kalem sa ispravljačem), za prekidanu jednosmernu — **galvanometar sa kretnim kalemom i nulom na sredini skale**. Klasa tačnosti ovde nije kritična — metoda je **nulta**.
3. **Ampermetar sa kretnim kalemom** u kolu pobude (jednosmerna varijanta), opsega prema izabranoj struji ogleda.
4. **Zaštitni (rasteretni) otpornik paralelno pobudnom namotaju** — kod prekidane jednosmerne struje obavezno: pri otvaranju prekidača struja pobude nastavlja da teče kroz njega, pa se energija $\frac{1}{2}LI^2$ kontrolisano potroši i ne javlja se razorni naponski impuls $L\frac{di}{dt}$ (brojka u modelu odgovora).
5. **Mehanička oprema:** ključ za otpuštanje stege mosta četkica; po potrebi sredstvo da se rotor ukoči.

**Recept za crtanje šeme na papiru:** (1) nacrtaj krug — to je armatura; na njemu dve četkice jedna naspram druge, sa naznakom strelicom da se **most četkica može zakretati**; (2) sa strane nacrtaj pobudni namotaj (kalem uz oznaku glavnog pola); (3) na četkice veži **mV** (milivoltmetar) — to je celo armaturno kolo, bez izvora; (4) na pobudni namotaj veži izvor: ili simbol naizmeničnog izvora sa autotransformatorom, ili bateriju — predotpor — prekidač — ampermetar na red, plus zaštitni otpornik paralelno namotaju; (5) strelicom pokaži smer pomeranja četkica i upiši „traži se $U_{mV}=0$".

## Rešeno ispitno pitanje

> **Pitanje (primeri pitanja za vežbu):** „Objasnite na koji način biste odredili neutralnu zonu motora jednosmerne struje sa nezavisnom pobudom."

**Model odgovor:**

**1) Šta se traži i zašto.** Neutralna zona je mesto na obodu armature gde je indukcija glavnog polja jednaka nuli (u praznom hodu se poklapa sa geometrijskom sredinom između glavnih polova). Četkice moraju stajati tako da kratko spajaju sekcije koje se nalaze baš u neutralnoj zoni: u takvoj sekciji nema rotacione ems, pa kroz kratko spojenu sekciju ne teče struja i komutacija prolazi **bez varničenja**. Ako su četkice zakrenute, u komutirajućoj sekciji se indukuje ems, četkica je kratko spaja, a pri prekidu te struje induktivna sekcija odgovara impulsom $L\frac{di}{dt}$ — varnica, nagrizanje kolektora; uz to reakcija indukta dobija podužnu komponentu koja kvari simetriju rada.

**2) Princip metode — indukciona (transformatorska) metoda.** Rotor **miruje** (mašina se ne pogoni; po potrebi se rotor ukoči). Pobudni namotaj — koji je kod nezavisne pobude ionako izveden na posebne priključke — napoji se **naizmeničnom strujom sniženog napona** (ili prekidanom jednosmernom strujom iz akumulatora). Fluks polova tada **pulsira**, pa se mašina ponaša kao transformator: pobuda je primar, armaturni namotaj između četkica sekundar. Na četkice se prisloni **milivoltmetar**. Napon na četkicama je $U = U_{\max}\sin\beta$ ($\beta$ — ugao četkica prema neutralnoj zoni): kada su četkice u neutralnoj zoni, svaka grana namotaja između četkica obuhvata jednake i suprotne delove pulsirajućeg fluksa, neto fluksni obuhvat je nula i **milivoltmetar pokazuje nulu**.

**3) Izbor opreme sa procenom brojki.** Podaci mašine nisu zadati, pa uzimam reprezentativan motor i to eksplicitno kažem: $P = 10\ \mathrm{kW}$, $U = 220\ \mathrm{V}$, $n = 1500\ \mathrm{o/min}$, nezavisna pobuda $U_f = 220\ \mathrm{V}$ (razumne vrednosti za laboratorijsku mašinu).

- Snaga pobude po pravilu iz beležaka ($0{,}5\,\%$ snage mašine): $P_f = 0{,}005\cdot 10\,000 = 50\ \mathrm{W}$, pa je nominalna struja pobude $I_f = P_f/U_f = 50/220 \approx 0{,}23\ \mathrm{A}$, a otpornost pobude $R_f = U_f/I_f = 220/0{,}227 \approx 968\ \mathrm{\Omega}$.
- Pobudni namotaj ima veliku induktivnost; uz **pretpostavku** vremenske konstante pobude $\tau_f = L_f/R_f = 0{,}5\ \mathrm{s}$ (tipičan red veličine za nezavisnu pobudu): $L_f = \tau_f R_f \approx 484\ \mathrm{H}$, pa je na $50\ \mathrm{Hz}$ reaktansa $X_f = 2\pi f L_f \approx 152\ \mathrm{k\Omega} \gg R_f$.
- **Naizmenična varijanta:** i da se pobuda veže pravo na mrežni napon $230\ \mathrm{V}$, tekla bi struja svega $I \approx U/X_f = 230/152\,000 \approx 1{,}5\ \mathrm{mA}$ — oko **150 puta manja** od nominalne jednosmerne: namotaj je bezbedan, fluks je mali, ali za osetljiv milivoltmetar dovoljan. Napon ipak dižem postepeno autotransformatorom od nule (dobra praksa; magnetno kolo i izolaciju ništa ne ugrožava).
- **Prekidana jednosmerna varijanta:** akumulator $12\ \mathrm{V}$, predotporom svedem struju na $\approx 20\,\%$ nominalne pobudne, $I_{og} \approx 45\ \mathrm{mA}$; paralelno pobudi vezujem zaštitni otpornik $R_p = R_f$, pa je pri otvaranju prekidača vršni napon na namotaju samo $I_{og} R_p \approx 44\ \mathrm{V}$. Bez tog otpornika bi nagli prekid (recimo za $10\ \mathrm{ms}$) dao impuls reda $L_f \frac{\Delta i}{\Delta t} = 484 \cdot 0{,}045/0{,}01 \approx 2{,}2\ \mathrm{kV}$ — proboj izolacije pobude i luk na prekidaču.
- **Instrument na četkicama:** milivoltmetar opsega $0\ldots100\ \mathrm{mV}$ (po potrebi i osetljiviji); za naizmeničnu varijantu instrument za naizmenične veličine, za prekidanu jednosmernu galvanometar sa kretnim kalemom i **nulom na sredini** (impulsi menjaju smer pri prolasku kroz neutralnu zonu).

**4) Postupak, korak po korak.**

1. Mašina odvojena od mreže i od pogonskog stroja; rotor miruje (ukočen). Armaturno kolo otvoreno — na četkicama samo milivoltmetar.
2. Otpusti se stega mosta četkica toliko da se most može lagano zakretati.
3. Pobuda se napoji: autotransformatorom se postepeno digne naizmenični napon (ili se u jednosmernoj varijanti predotpor stavi na najveću vrednost, uklopi prekidač, struja udesi na $I_{og}$, pa se prekidač ritmično uklapa/isklapa).
4. Most četkica se **polako pomera po obodu** u jednom smeru i posmatra skretanje milivoltmetra: skretanje opada, prolazi kroz **minimum (nulu)** i ponovo raste — kod prekidane jednosmerne struje impulsi pri prolasku kroz nulu **promene smer**.
5. Most se vrati tačno u položaj nultog skretanja i **učvrsti**. Zbog oštrine nule položaj se nađe na delić stepena tačno: uz $U_{\max}$ reda $0{,}5\ \mathrm{V}$, već zakretanje od $1^\circ$ (el.) daje $U = 0{,}5\sin 1^\circ \approx 8{,}7\ \mathrm{mV}$ — jasno vidljivo na opsegu $100\ \mathrm{mV}$.
6. Isključi se napajanje pobude (jednosmerna varijanta: prvo predotpor na najveću vrednost, pa prekidač — zaštitni otpornik ostaje vezan dok struja ne iščezne).

**5) Provera u radu.** Motor se pusti u prazan hod pa pod opterećenje, u **oba smera obrtanja**, uz isti napon i pobudu: komutacija mora biti **bez varničenja**, a **brzine u oba smera jednake** (kao generator: jednaki naponi). Nesimetrija ili varničenje znače da neutralna zona nije pogođena, pa se postupak ponovi.

## Varijacije zadatka

### V1 — „Šta se dešava ako četkice NISU u neutralnoj zoni?" (sa brojkama)

**Odgovor u tri tačke, pa račun.**

1. **Varničenje:** komutirajuća sekcija više nije u polju $B=0$; rotaciona ems tera struju kroz sekciju kratko spojenu četkicom, a njen nagli prekid pri izlasku lamele ispod četkice daje $L\frac{di}{dt}$ impuls — varnica, nagrizanje kolektora i četkica, u težem slučaju kružna vatra.
2. **Podužna komponenta reakcije indukta:** armaturna mps dobija komponentu duž ose polova, srazmernu $\sin\beta$, koja **razmagnetiše ili magnetiše** glavno polje — znak zavisi od smera struje armature, dakle od smera obrtanja.
3. **Nesimetrija u dva smera:** pošto ta komponenta u jednom smeru obrtanja fluks povećava, a u drugom smanjuje, motor u dva smera radi različitim brzinama ($n = \frac{U - R_a I_a}{k\Phi}$ — fluks u imeniocu).

**Brojčani primer.** Motor $10\ \mathrm{kW}$, $220\ \mathrm{V}$, $1500\ \mathrm{o/min}$, $\eta = 0{,}85$ (pretpostavka stepena iskorišćenja, razumna za ovu snagu). Ulazna snaga $P_{ul} = P/\eta = 11\,765\ \mathrm{W}$, struja armature $I_a = P_{ul}/U = 11\,765/220 \approx 53{,}5\ \mathrm{A}$. Ukupni gubici $P_{ul} - P = 1765\ \mathrm{W}$; po pravilu iz beležaka $60\,\%$ su gubici u bakru, a kod jednosmerne mašine **svih $60\,\%$ ide na rotor**: $P_{Cu} \approx 1059\ \mathrm{W}$, pa je $R_a = P_{Cu}/I_a^2 = 1059/53{,}5^2 \approx 0{,}37\ \mathrm{\Omega}$ i $E = U - R_a I_a \approx 220 - 19{,}8 \approx 200\ \mathrm{V}$. Neka je zakretanje četkica toliko da podužna komponenta reakcije indukta menja fluks za $\pm 2\,\%$ (pretpostavka radi ilustracije). Pošto je $n \propto E/\Phi$, pri istom naponu i opterećenju:

$$n_1 = \frac{1500}{1{,}02} \approx 1471\ \mathrm{o/min}, \qquad n_2 = \frac{1500}{0{,}98} \approx 1531\ \mathrm{o/min},$$

razlika $\Delta n \approx 60\ \mathrm{o/min}$, tj. **$4\,\%$ nesimetrije** — lako merljivo tahogeneratorom iz Teme 2. Zaključak koji se izgovara na ispitu: jednakost brzina u oba smera je praktičan test neutralne zone, a nejednakost odmah kvantitativno pokazuje koliko su četkice zakrenute.

### V2 — „Kako se metoda menja za mašinu sa pomoćnim polovima?"

**Šta su pomoćni polovi:** uski polovi smešteni **u geometrijskoj neutralnoj zoni** (između glavnih polova), čiji je namotaj vezan **na red sa armaturom**, pa im je mps srazmerna $I_a$. Zadatak im je da u zoni komutacije naprave malo polje koje **poništava poprečnu reakciju indukta i pride indukuje komutacionu ems** koja pomaže preokret struje u sekciji. Pošto su na red sa armaturom, kompenzacija „prati" opterećenje sama od sebe — magnetna neutralna zona **prestaje da beži** sa opterećenjem.

**Posledice po postupak:**

1. **Indukciona metoda ostaje ista i ništa joj ne smeta:** tokom ogleda armaturno kolo je otvoreno (na četkicama je samo milivoltmetar), pa kroz redno vezani namotaj pomoćnih polova **ne teče struja** — pomoćni polovi su tokom ogleda magnetno „mrtvi" i ne kvare nulu. Metodom se četkice postave u **geometrijsku neutralnu zonu i tu trajno fiksiraju** — kod mašine sa pomoćnim polovima četkice se u pogonu **ne pomeraju**.
2. **Fino podešavanje se prebacuje sa četkica na pomoćne polove:** pogonska provera (varničenje i simetrija u oba smera, pod opterećenjem) više ne služi da se pomere četkice, nego da se podesi **jačina pomoćnih polova** — podmetačima (magnetnim/nemagnetnim ulošcima) kojima se menja vazdušni zazor pomoćnog pola, izuzetno i šentiranjem njihovog namotaja otpornikom. Prejaki pomoćni polovi „prekompenzuju" (varniči pri jednom znaku opterećenja), preslabi „potkompenzuju".
3. **Kontrola veze:** pomoćni polovi moraju biti vezani tako da im polaritet odgovara smeru struje armature (pogrešan polaritet udvostručuje problem umesto da ga leči) — provera u oba smera obrtanja ovo odmah otkrije, jer redna veza sama menja znak mps kad se promeni smer struje.

### V3 — „Rezolver: kako se sinusnim i kosinusnim namotajem određuje položaj rotora?" (sa brojkama)

**Odgovor po beleškama:** rezolver je uređaj asinhronog tipa sa primarom **na rotoru** i dva sekundara **na statoru**, pomerena za $90^\circ$ — **sinusni i kosinusni namotaj**. Primar se pobuđuje **naizmeničnom strujom** (profesorov naglasak: ne jednosmernom!) i pravi pulsaciono polje; položaj rotora $\theta$ „utiskuje" se u flukseve koji prožimaju dva sekundara, pa su amplitude indukovanih napona $U_{\sin} \propto \sin\theta$ i $U_{\cos} \propto \cos\theta$. Položaj se dobija iz količnika (amplitude se skrate, pa rezultat ne zavisi od jačine pobude):

$$\theta = \operatorname{arctg}\frac{U_{\sin}}{U_{\cos}}.$$

**Brojčani primer:** izmereno $U_{\sin} = 3{,}2\ \mathrm{V}$ i $U_{\cos} = 4{,}0\ \mathrm{V}$ (amplitude, uz praćenje faznog stava radi znaka):

$$\theta = \operatorname{arctg}\frac{3{,}2}{4{,}0} = \operatorname{arctg}0{,}8 \approx 38{,}7^\circ.$$

Praćenjem $\theta(t)$ dobija se i brzina obrtanja. Primena: agresivne sredine (vlaga, prašina). Veza sa glavnim pitanjem: i određivanje neutralne zone i rezolver koriste **transformatorsku spregu zavisnu od ugla uz naizmeničnu pobudu** — samo što se kod rezolvera ugao čita iz odnosa dva napona, a kod neutralne zone traži ugao u kojem je napon nula.

## Česte greške i zamke na ispitu

1. **Pobuda na pun jednosmerni napon i „čekamo napon na četkicama".** Pri konstantnoj jednosmernoj struji fluks ne pulsira, $\frac{d\Phi}{dt}=0$, transformatorske ems **nema** — milivoltmetar pokazuje nulu u svakom položaju četkica i „nađeš" neutralnu zonu bilo gde. Fluks mora da **pulsira**: naizmenična ili prekidana jednosmerna struja.
2. **Rotor se obrće tokom ogleda.** Čim se rotor okreće u pobuđenoj mašini, javlja se **rotaciona** ems $k\Phi\omega$ koja je mnogo veća od transformatorske i potpuno maskira nulu. Armatura **miruje** — to je prva rečenica postupka.
3. **Naglo prekinuto pobudno kolo bez zaštitnog otpornika.** Pobuda je ogromna induktivnost (u primeru $\approx 484\ \mathrm{H}$): prekid i male struje od $45\ \mathrm{mA}$ za $10\ \mathrm{ms}$ daje impuls $\approx 2{,}2\ \mathrm{kV}$ — proboj izolacije pobude, luk na prekidaču. Ista logika kao u Temi 1 (zato tamo voltmetar „nije fiksan"): paralelno pobudi zaštitni otpornik, struju gasiti postepeno predotporom.
4. **Pogrešan instrument.** Kod naizmenične varijante instrument **sa kretnim kalemom** pokazuje srednju vrednost naizmeničnog signala — **nulu svuda** — pa student „izmeri" neutralnu zonu gde god stane. Kretni kalem ide uz prekidanu jednosmernu varijantu (galvanometar sa nulom na sredini), a uz naizmeničnu ide instrument za naizmenične veličine.
5. **Brkanje smera bežanja magnetne neutralne zone.** Pod opterećenjem se pomera **u smeru obrtanja kod generatora**, **suprotno kod motora** — i srazmerno opterećenju. I obratno pitanje: indukciona metoda se radi na mašini koja miruje, pa daje neutralnu zonu **bez** reakcije indukta.
6. **Kod mašine sa pomoćnim polovima pomerati četkice po pogonskoj proveri.** Tamo četkice stoje fiksno u geometrijskoj neutralnoj zoni, a doteruje se **jačina pomoćnih polova**; tokom indukcione metode pomoćni polovi ne smetaju jer kroz njihov redni namotaj ne teče struja.

## Kontrolna pitanja za samoproveru

1. **Šta je neutralna zona i gde se nalazi u praznom hodu?** Mesto na obodu armature gde je rezultantna indukcija nula; u praznom hodu se poklapa sa geometrijskom sredinom između glavnih polova.
2. **Zašto četkice moraju stajati u neutralnoj zoni?** Da bi sekcija kratko spojena četkicom tokom komutacije bila bez indukovane ems — nema struje kratkog spoja ni njenog prekida, pa nema varničenja.
3. **Zašto se u indukcionoj metodi pobuda napaja naizmeničnom (ili prekidanom jednosmernom) strujom?** Jer transformatorsku ems pravi samo promenljiv fluks ($e = d\Psi/dt$); konstantna jednosmerna struja ne indukuje ništa.
4. **Zašto je napon na četkicama nula baš u neutralnoj zoni?** Jer tada svaka grana namotaja između četkica obuhvata jednake i suprotne delove pulsirajućeg fluksa — neto fluksni obuhvat je nula ($U = U_{\max}\sin\beta$, $\beta = 0$).
5. **Kako se neutralna zona proverava u radu?** Bez varničenja na kolektoru i jednake brzine (motor) odnosno naponi (generator) u oba smera obrtanja pod istim uslovima.
6. **Kuda se pomera magnetna neutralna zona pod opterećenjem?** Kod generatora u smeru obrtanja, kod motora suprotno smeru obrtanja — srazmerno struji armature (reakciji indukta).
