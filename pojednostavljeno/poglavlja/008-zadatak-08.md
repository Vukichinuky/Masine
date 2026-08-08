# Zadatak 8 — Porast napona hidrogeneratora posle naglog isključenja sa mreže

## Postavka

Hidrogenerator ima sledeće nazivne podatke: prividna snaga $203{,}5\ \mathrm{MVA}$; napon $13{,}8\ \mathrm{kV}$; sprega statorskog namotaja zvezda (Y); brzina obrtanja $300\ \mathrm{min^{-1}}$; faktor snage $\cos\varphi = 0{,}85$; sinhrona reaktansa po uzdužnoj osi $x_d = 1{,}05$ (relativna vrednost); sinhrona reaktansa po poprečnoj osi $x_q = 0{,}69$ (relativna vrednost). Generator radi sa nazivnim opterećenjem i usled delovanja zaštite biva odvojen od mreže. Koliki iznosi porast napona generatora neposredno nakon isključenja prekidača?

> **Prevod na običan jezik:** Veliki generator u hidroelektrani radi punom snagom i "gura" nazivnu struju u mrežu. Odjednom — recimo zbog kvara negde u mreži — zaštita otvori prekidač i generator ostane bez ijednog potrošača. Struja statora u tom trenutku padne na nulu, ali pobuda rotora (jednosmerna struja koja pravi magnetno polje) ostaje ista kao trenutak ranije, jer se ona ne može promeniti trenutno. Pitanje glasi: koliko puta poraste napon na krajevima generatora u tom prvom trenutku, pre nego što regulator pobude stigne da reaguje? Da bismo odgovorili, moramo prvo da izračunamo koliku je elektromotornu silu $E_{0f}$ pobuda "pravila" u nazivnom režimu — jer upravo ta vrednost postaje napon na krajevima čim struja nestane.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna prividna snaga | $S_{\mathrm{n}}$ | $203{,}5\ \mathrm{MVA}$ | Ukupna ("puna") snaga koju generator sme trajno da daje; proizvod $\sqrt{3}\,U_{\mathrm{n}} I_{\mathrm{n}}$. |
| Nazivni napon (linijski) | $U_{\mathrm{n}}$ | $13{,}8\ \mathrm{kV}$ | Efektivna vrednost napona **između dva fazna provodnika** na krajevima statora u nazivnom režimu. |
| Sprega statora | — | Y (zvezda) | Tri fazna namotaja spojena u zajedničku tačku (zvezdište); fazni napon je tada $U_{\mathrm{n}}/\sqrt{3}$. |
| Nazivna brzina obrtanja | $n$ | $300\ \mathrm{min^{-1}}$ | Broj obrtaja rotora u minuti. Mala brzina odaje hidrogenerator sa mnogo pari polova i **isturenim polovima**. |
| Nazivni faktor snage | $\cos\varphi$ | $0{,}85$ (induktivno) | Kosinus ugla između faznog napona i fazne struje; struja **kasni** za naponom (generator daje i reaktivnu snagu mreži). |
| Relativna sinhrona reaktansa po uzdužnoj (d) osi | $x_d$ | $1{,}05$ | Reaktansa koju struja "vidi" kada njeno polje deluje **duž ose polova** rotora, izražena u delovima bazne impedanse. |
| Relativna sinhrona reaktansa po poprečnoj (q) osi | $x_q$ | $0{,}69$ | Reaktansa koju struja "vidi" kada njeno polje deluje **između polova** (kroz veliki vazdušni međuprostor), u delovima bazne impedanse. |

Napomena: brzina $300\ \mathrm{min^{-1}}$ se u samom računu ne koristi, ali nam govori nešto važno — na mreži od $50\ \mathrm{Hz}$ takva brzina znači $p = 60f/n = 60\cdot 50/300 = 10$ pari polova. Toliko polova može da se smesti samo na rotor sa **isturenim polovima**, a upravo zato mašina ima dve različite reaktanse ($x_d \neq x_q$) i zato ćemo morati da koristimo dvoosnu teoriju.

## Šta se traži i zašto

Traži se **porast napona generatora neposredno nakon isključenja prekidača** — bezdimenzioni odnos napona koji se pojavi na krajevima odmah po isključenju i nazivnog napona.

**Zašto to inženjera zanima?** Kada generator pod punim opterećenjem naglo ostane bez mreže (tzv. *naglo rasterećenje*), napon na njegovim krajevima skoči. Taj skok mora da izdrži izolacija namotaja, mernih transformatora i svega što ostane priključeno na sabirnice generatora. Ako projektant ne zna koliki je skok, ne može ispravno da odabere izolacioni nivo opreme, podešenja prenaponske zaštite ni brzinu kojom regulator pobude mora da obori pobudnu struju. Videćemo da skok nije mali — napon poraste na skoro **1,8 puta** nazivne vrednosti!

**Plan rešavanja** (običnim jezikom):

1. Reaktanse su zadate u relativnim jedinicama — prvo izračunamo **baznu impedansu** $Z_b$ da bismo ih pretvorili u ome.
2. Izračunamo **nazivnu faznu struju** $I_{\mathrm{n}f}$, jer u nazivnom režimu kroz stator teče baš ta struja.
3. Nacrtamo (u glavi, a opisaćemo ga detaljno) **fazorski dijagram** generatora sa isturenim polovima u nazivnom režimu i iz njega ispišemo dve jednačine — projekcije na d- i q-osu.
4. Iz jednačine za d-osu izračunamo **ugao opterećenja** $\delta$.
5. Iz jednačine za q-osu izračunamo **ems praznog hoda** $E_{0f}$ — napon koji pobuda "drži spreman" iza reaktansi.
6. Porast napona je odnos $E_{0f}$ i nazivnog faznog napona: čim struja nestane, na krajevima se pojavi cela $E_{0f}$.

## Potrebna teorija — mini-lekcije

### 1. Mašina sa isturenim polovima: zašto postoje dve reaktanse ($X_d$ i $X_q$)

Rotor hidrogeneratora nije gladak valjak, nego točak sa **isturenim polovima** — jasno izraženim magnetnim "pečurkama" oko kojih je namotana pobudna (jednosmerna) struja. Zbog toga magnetno kolo mašine nije isto u svim pravcima:

- **Uzduž ose pola** (tzv. *uzdužna* ili *d-osa*, od engl. *direct*): magnetni fluks prolazi kroz gvožđe pola i mali vazdušni zazor — put mu je magnetno "lak", pa je induktivnost velika.
- **Između dva pola** (tzv. *poprečna* ili *q-osa*, od engl. *quadrature*, pomerena za 90 električnih stepeni od d-ose): fluks mora da premosti veliki vazdušni prostor između polova — put mu je magnetno "težak", pa je induktivnost manja.

Statorska struja zato ne "vidi" jednu reaktansu, nego dve: komponenta struje čije polje deluje po d-osi vidi **sinhronu reaktansu po uzdužnoj osi** $X_d$, a komponenta čije polje deluje po q-osi vidi **sinhronu reaktansu po poprečnoj osi** $X_q$, pri čemu je uvek $X_q < X_d$ (kod nas: $0{,}69$ prema $1{,}05$ relativno). Ova ideja — da se statorska struja razloži na dve komponente, $I_d$ i $I_q$, i da svaka "radi" sa svojom reaktansom — zove se **teorija dvostruke reakcije** (Blondelova teorija) i ona je standardni alat za mašine sa isturenim polovima.

*Analogija:* zamisli da guraš kolica po dvorištu u kome su betonske staze u jednom pravcu, a duboka trava u drugom. Isti trud (ista struja) daje različit učinak (različit fluks) zavisno od pravca — zato pravcu "staze" pripisujemo jednu "otpornost kretanju", a pravcu "trave" drugu.

### 2. Relativne (per-unit) jedinice i bazna impedansa

Podaci $x_d = 1{,}05$ i $x_q = 0{,}69$ nisu u omima — to su **relativne vrednosti**: reaktansa je podeljena jednom dogovorenom, "baznom" impedansom mašine. Tako izražene, reaktanse raznih mašina se lako porede (npr. $x_d \approx 1$ je tipično za sinhroni generator, bez obzira da li je mašina od 1 MVA ili od 500 MVA).

**Bazna impedansa** se definiše kao odnos baznog (nazivnog faznog) napona i bazne (nazivne fazne) struje:

$$Z_b = \frac{U_b}{I_b} = \frac{U_{\mathrm{n}}/\sqrt{3}}{I_{\mathrm{n}f}}.$$

Pošto je nazivna prividna snaga trofazne mašine $S_{\mathrm{n}} = \sqrt{3}\, U_{\mathrm{n}} I_{\mathrm{n}f}$, nazivna struja je $I_{\mathrm{n}f} = S_{\mathrm{n}}/(\sqrt{3}\,U_{\mathrm{n}})$, pa kada to uvrstimo:

$$Z_b = \frac{U_{\mathrm{n}}/\sqrt{3}}{S_{\mathrm{n}}/(\sqrt{3}\,U_{\mathrm{n}})} = \frac{U_{\mathrm{n}}}{\sqrt{3}}\cdot\frac{\sqrt{3}\,U_{\mathrm{n}}}{S_{\mathrm{n}}} = \frac{U_{\mathrm{n}}^2}{S_{\mathrm{n}}}.$$

Zapamti praktičan oblik: **bazna impedansa = kvadrat linijskog nazivnog napona podeljen nazivnom prividnom snagom.** Ako napon uvrstiš u kilovoltima, a snagu u megavoltamperima, rezultat izlazi direktno u omima (jer je $\mathrm{kV^2/MVA} = 10^6\,\mathrm{V^2} / (10^6\,\mathrm{VA}) = \Omega$). Stvarna (omska) reaktansa se onda dobija prostim množenjem: $X = x \cdot Z_b$.

### 3. Ems praznog hoda $E_{0f}$ — i zašto je u nazivnom režimu maksimalna

Pobudna (jednosmerna) struja u rotoru pravi glavni magnetni fluks. Kada se rotor obrće, taj fluks seče statorske provodnike i u svakoj fazi indukuje elektromotornu silu. Njena efektivna vrednost **po fazi**, kada statorska struja ne teče, zove se **ems praznog hoda** i označava se $E_{0f}$ (indeks $0$ = prazan hod, indeks $f$ = fazna vrednost). Ona zavisi samo od pobudne struje i brzine obrtanja: veća pobuda → veći fluks → veća $E_{0f}$.

Kada generator **jeste** opterećen, na njegovim krajevima ne vidimo $E_{0f}$, nego manji napon $U_f$, jer deo emsa "pojedu" padovi napona na reaktansama ($X_d$, $X_q$) usled statorske struje. Ali $E_{0f}$ i dalje "postoji" unutra — to je napon koji bi se pojavio na krajevima kada bi struja nestala.

**Ključna napomena iz originalnog rešenja:** fazorski dijagram crtamo baš za **nazivni režim** (nazivni napon, nazivna struja, $\cos\varphi = 0{,}85$ induktivno) zato što je **u tom režimu pobudna struja nazivna, pa je $E_{0f}$ najveća moguća u normalnom pogonu**. Drugim rečima, nazivni režim je najgori mogući slučaj za naglo rasterećenje: nigde u dozvoljenom pogonu pobuda nije jača, pa nigde skok napona ne bi bio veći. Zato porast napona računamo upravo iz ovog režima.

### 4. Fazorski dijagram generatora sa isturenim polovima i njegove dve jednačine

Pošto poglavlje nema sliku, dijagram ćemo pažljivo opisati rečima — nacrtaj ga na papiru dok čitaš, to je najbolji način da ga zaista razumeš.

**Kako se dijagram crta.** Nacrtaj dve međusobno normalne ose: horizontalnu **d-osu** i vertikalnu **q-osu** (one prate rotor: d-osa je osa pola, q-osa je između polova). Dogovor je sledeći:

- Fazor emsa praznog hoda $\underline{E}_{0f}$ leži **tačno na q-osi** (to je posledica fizike: pobudni fluks je po d-osi, a ems koju on indukuje kasni za fluksom 90°, pa "padne" na q-osu). Ceo dijagram se zato "kači" o q-osu.
- Fazor faznog napona $\underline{U}_f$ zaklapa sa q-osom (tj. sa $\underline{E}_{0f}$) ugao $\delta$ — **ugao opterećenja** (o njemu u sledećoj mini-lekciji). Kod generatora $\underline{E}_{0f}$ **prednjači** naponu.
- Fazor fazne struje $\underline{I}_f$ kasni za naponom $\underline{U}_f$ za ugao $\varphi$ (induktivno opterećenje). Prema q-osi struja, dakle, zaklapa ugao $\delta + \varphi$.
- Struja se razlaže na komponente po osama: $I_q = I_f\cos(\delta+\varphi)$ duž q-ose i $I_d = I_f\sin(\delta+\varphi)$ duž d-ose.
- Na napon $\underline{U}_f$ se nadovezuju dva pada napona: $\mathrm{j}X_q \underline{I}_q$ i $\mathrm{j}X_d \underline{I}_d$; njihov zbir sa $\underline{U}_f$ zatvara se tačno u vrh fazora $\underline{E}_{0f}$ na q-osi.

Otpor statorskog namotaja je zanemaren (kod ovako velikih mašina on je stotinama puta manji od reaktansi), pa naponska jednačina generatora glasi:

$$\underline{E}_{0f} = \underline{U}_f + \mathrm{j}X_d \underline{I}_d + \mathrm{j}X_q \underline{I}_q .$$

**Zašto se padovi "razdvoje" po osama.** Množenje fazora imaginarnom jedinicom $\mathrm{j}$ znači zaokret za $+90°$. Komponenta struje $\underline{I}_d$ leži na d-osi, pa fazor $\mathrm{j}X_d\underline{I}_d$ (zaokrenut 90° od nje) leži na **q-osi**. Slično, $\underline{I}_q$ leži na q-osi, pa $\mathrm{j}X_q\underline{I}_q$ leži na **d-osi** (za induktivni režim generatora tako da "gura" vrh dijagrama ka d-osi). Zbog toga vektorsku jednačinu možemo rastaviti na dve obične, skalarne jednačine — **projekcije**:

- **Projekcija na q-osu.** Na q-osi se sabiraju: projekcija napona $U_f\cos\delta$ i ceo pad $X_d I_d$; njihov zbir mora dati $E_{0f}$ (koja je cela na q-osi):
$$U_f \cos\delta + X_d I_d = E_{0f} \qquad (1)$$
- **Projekcija na d-osu.** Na d-osi projekcija napona iznosi $U_f\sin\delta$, a od padova tu leži samo $X_q I_q$; pošto $E_{0f}$ nema d-komponentu, ta dva se moraju izjednačiti:
$$U_f \sin\delta = X_q I_q \qquad (2)$$
- **Definicija q-komponente struje.** Struja zaklapa ugao $\delta+\varphi$ sa q-osom, pa je njena q-komponenta:
$$I_q = I_f \cos(\delta + \varphi) = I_f\cos\delta\cos\varphi - I_f\sin\delta\sin\varphi \qquad (3)$$
Drugi oblik je samo primenjena trigonometrijska **adiciona formula** $\cos(\alpha+\beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta$ — trebaće nam da razdvojimo nepoznati ugao $\delta$ od poznatog ugla $\varphi$.

Analogno, d-komponenta struje je $I_d = I_f\sin(\delta+\varphi)$ — nju ćemo iskoristiti u jednačini (1).

### 5. Ugao opterećenja $\delta$

**Ugao opterećenja** (ili *ugao snage*) $\delta$ je ugao između fazora $\underline{E}_{0f}$ i fazora $\underline{U}_f$. Fizički, to je (u električnim stepenima) ugao za koji je rotor sa svojim polovima "odmakao" ispred rezultantnog obrtnog polja kada mašina radi kao generator. Što više aktivne snage generator daje, to je $\delta$ veći — rotor kao da "vuče" polje za sobom preko elastične magnetne veze. U praznom hodu je $\delta = 0$ (rotor i polje poravnati, $\underline{E}_{0f}$ i $\underline{U}_f$ se poklapaju). U našem zadatku $\delta$ ne znamo unapred — moramo ga izračunati iz jednačine (2), jer bez njega ne možemo razložiti struju na $I_d$ i $I_q$.

### 6. Šta se dešava u trenutku isključenja prekidača (naglo rasterećenje)

U trenutku otvaranja prekidača statorsko kolo se prekida i **statorska struja trenutno pada na nulu**: $I_f = 0$, pa i $I_d = 0$ i $I_q = 0$. Pogledaj sada jednačinu (1): bez struje nema padova napona na reaktansama, pa ostaje prosto

$$U_f = E_{0f}.$$

Na krajevima generatora se, dakle, pojavi **cela ems praznog hoda**. A pobudna struja rotora se u tom trenutku nije promenila — pobudni namotaj je veliki induktivitet i njegova struja ne može skočiti trenutno, a ni automatski regulator pobude još nije stigao da reaguje (reč "neposredno" u zadatku znači baš to: gledamo prvi trenutak, pre bilo kakve regulacije). Zato je napon **posle** isključenja jednak onoj $E_{0f}$ koju je pobuda pravila **pre** isključenja — a nju računamo iz fazorskog dijagrama nazivnog režima.

**Porast napona** je onda odnos novog i starog napona na krajevima:

$$\text{porast} = \frac{E_{0f}}{U_{\mathrm{n}f}} = \frac{E_{0f}}{U_{\mathrm{n}}/\sqrt{3}}.$$

*Mala ograda (pošteno rečeno):* ovo je proračun po ustaljenom (stacionarnom) modelu — on zanemaruje prelazne pojave u prigušnim namotajima i promenu brzine turbine, ali daje jednostavnu i konzervativnu (gornju) procenu skoka napona, i upravo tako se radi u originalnoj zbirci.

## Rešenje, korak po korak

### Korak 1: Bazna impedansa $Z_b$

**Zašto ovaj korak:** reaktanse $x_d$ i $x_q$ su zadate u relativnim jedinicama; da bismo u fazorskom dijagramu računali sa voltima i amperima, treba nam njihova vrednost u omima, a za to je potrebna bazna impedansa (mini-lekcija 2).

Opšti oblik (izveden u mini-lekciji 2):

$$Z_b = \frac{U_b}{I_b} = \frac{U_{\mathrm{n}}}{\sqrt{3}\cdot I_{\mathrm{n}f}} = \frac{U_{\mathrm{n}}^2}{S_{\mathrm{n}}}$$

gde je $U_{\mathrm{n}}$ nazivni linijski napon, $I_{\mathrm{n}f}$ nazivna fazna struja, a $S_{\mathrm{n}}$ nazivna prividna snaga. Uvrštavamo napon u $\mathrm{kV}$ i snagu u $\mathrm{MVA}$ (rezultat tada izlazi u omima):

$$Z_b = \frac{13{,}8^2}{203{,}5} = \frac{190{,}44}{203{,}5} = 0{,}9358\ \mathrm{\Omega}.$$

**Šta smo dobili:** merilo "100% impedanse" ove mašine — reaktansa od $0{,}9358\ \mathrm{\Omega}$ za ovaj generator predstavlja relativnu vrednost 1 (tj. 100%). Vrednost deluje malo u omima, ali to je normalno: mašina velike snage i umerenog napona ima malu baznu impedansu.

### Korak 2: Reaktanse u omima, $X_d$ i $X_q$

**Zašto ovaj korak:** jednačine (1) i (2) traže reaktanse u omima; dobijamo ih množenjem relativnih vrednosti baznom impedansom.

$$X_d = x_d \cdot Z_b = 1{,}05 \cdot 0{,}9358 = 0{,}9826\ \mathrm{\Omega}$$

$$X_q = x_q \cdot Z_b = 0{,}69 \cdot 0{,}9358 = 0{,}6457\ \mathrm{\Omega}$$

**Šta smo dobili:** stvarne (omske) sinhrone reaktanse po uzdužnoj i poprečnoj osi. Kao što teorija isturenih polova predviđa, $X_q < X_d$ — fluks između polova ima "teži" magnetni put.

### Korak 3: Nazivna fazna struja $I_{\mathrm{n}f}$

**Zašto ovaj korak:** generator radi sa nazivnim opterećenjem, dakle kroz stator teče nazivna struja — ona je "$I_f$" u našem fazorskom dijagramu i u jednačinama (2) i (3).

Iz definicije trofazne prividne snage $S_{\mathrm{n}} = \sqrt{3}\, U_{\mathrm{n}} I_{\mathrm{n}f}$ izrazimo struju (podelimo obe strane sa $\sqrt{3}\,U_{\mathrm{n}}$):

$$I_{\mathrm{n}f} = \frac{S_{\mathrm{n}}}{\sqrt{3}\cdot U_{\mathrm{n}}} = \frac{203\,500}{\sqrt{3}\cdot 13{,}8} = \frac{203\,500}{23{,}902} = 8513{,}8\ \mathrm{A}.$$

(Ovde je snaga uvrštena u $\mathrm{kVA}$, a napon u $\mathrm{kV}$, pa kilo-faktori skrate jedan drugi i struja izlazi u amperima.) Napomena o oznaci: kod sprege zvezda fazna struja namotaja jednaka je linijskoj struji, pa je $I_{\mathrm{n}f}$ ujedno i struja koju bismo izmerili u provodniku ka mreži.

**Šta smo dobili:** preko osam i po hiljada ampera — sasvim očekivano za mašinu od $203{,}5\ \mathrm{MVA}$ na svega $13{,}8\ \mathrm{kV}$; velika snaga pri umerenom naponu mora značiti ogromnu struju.

### Korak 4: Ugao faktora snage $\varphi$ i fazni napon $U_f$

**Zašto ovaj korak:** u jednačinama (2) i (3) figurišu i $\cos\varphi$ i $\sin\varphi$, a u svim jednačinama fazni napon $U_f$ — pripremimo te brojeve unapred.

Iz $\cos\varphi = 0{,}85$ sledi:

$$\varphi = \arccos 0{,}85 = 31{,}79°, \qquad \sin\varphi = \sin 31{,}79° = 0{,}5268.$$

(Isto se dobija i iz osnovnog identiteta: $\sin\varphi = \sqrt{1-\cos^2\varphi} = \sqrt{1-0{,}85^2} = \sqrt{0{,}2775} = 0{,}5268$.)

Fazni napon kod sprege zvezda je linijski podeljen sa $\sqrt{3}$:

$$U_f = \frac{U_{\mathrm{n}}}{\sqrt{3}} = \frac{13\,800}{\sqrt{3}} = 7967{,}4\ \mathrm{V}.$$

**Šta smo dobili:** ugao od $31{,}79°$ za koji struja kasni za naponom i fazni napon od oko $7{,}97\ \mathrm{kV}$ — sve što nam treba da jednačine dijagrama "napunimo" brojevima.

### Korak 5: Jednačine fazorskog dijagrama za nazivni režim

**Zašto ovaj korak:** iz mini-lekcije 3 znamo da dijagram treba nacrtati baš za nazivni režim ($U_f$, $I_{\mathrm{n}f}$, $\cos\varphi = 0{,}85$ induktivno), jer je tada pobudna struja nazivna i $E_{0f}$ maksimalna moguća — to je merodavan (najgori) slučaj za skok napona. Ovde samo prepisujemo tri jednačine izvedene u mini-lekciji 4, sada sa konkretnim oznakama:

$$U_f \cos\delta + X_d I_d = E_{0f} \qquad (1)$$

$$U_f \sin\delta = X_q I_q \qquad (2)$$

$$I_q = I_f \cos(\delta+\varphi) = I_f\cos\delta\cos\varphi - I_f\sin\delta\sin\varphi \qquad (3)$$

U njima znamo $U_f$, $X_d$, $X_q$, $I_f = I_{\mathrm{n}f}$ i $\varphi$; ne znamo $\delta$, $I_d$, $I_q$ i $E_{0f}$. Ali sistem nije težak: ubacivanjem (3) u (2) dobijamo jednačinu u kojoj je **jedina** nepoznata ugao $\delta$.

**Šta smo dobili:** zatvoren sistem jednačina — sledi čista algebra.

### Korak 6: Ugao opterećenja $\delta$ (zamena (3) u (2))

**Zašto ovaj korak:** bez $\delta$ ne znamo kako da razložimo struju na $I_d$ i $I_q$, pa ni da izračunamo $E_{0f}$.

Uvrstimo (3) u desnu stranu jednačine (2):

$$U_f \sin\delta = X_q I_f \cos\varphi\,\cos\delta - X_q I_f \sin\varphi\,\sin\delta.$$

Sa brojevima (prvo izračunajmo zajednički proizvod $X_q I_f = 0{,}6457 \cdot 8513{,}8 = 5497{,}4\ \mathrm{V}$):

$$7967{,}4\,\sin\delta = 5497{,}4\cdot 0{,}85\,\cos\delta - 5497{,}4\cdot 0{,}5268\,\sin\delta$$

$$7967{,}4\,\sin\delta = 4672{,}8\,\cos\delta - 2896{,}0\,\sin\delta.$$

Prebacimo član sa $\sin\delta$ sa desne strane na levu (menja znak):

$$7967{,}4\,\sin\delta + 2896{,}0\,\sin\delta = 4672{,}8\,\cos\delta$$

$$10\,863{,}4\,\sin\delta = 4672{,}8\,\cos\delta.$$

Podelimo obe strane sa $10\,863{,}4\,\cos\delta$ (smemo, jer $\cos\delta \neq 0$ za realne uglove opterećenja) i iskoristimo $\sin\delta/\cos\delta = \tan\delta$:

$$\tan\delta = \frac{4672{,}8}{10\,863{,}4} = 0{,}4301 \quad\Rightarrow\quad \delta = \arctan 0{,}4301 = 23{,}27°.$$

**Šta smo dobili:** ugao opterećenja od $23{,}27°$ — tipična vrednost za sinhroni generator pod punim opterećenjem (daleko od granice stabilnosti od 90°, kako i treba u normalnom pogonu).

### Korak 7: Ems praznog hoda $E_{0f}$ (iz jednačine (1))

**Zašto ovaj korak:** $E_{0f}$ je upravo napon koji će se pojaviti na krajevima posle isključenja (mini-lekcija 6) — ovo je srce zadatka.

Prvo d-komponenta struje. Struja zaklapa ugao $\delta + \varphi$ sa q-osom, pa je (mini-lekcija 4):

$$I_d = I_f \sin(\delta+\varphi) = 8513{,}8 \cdot \sin(23{,}27° + 31{,}79°) = 8513{,}8\cdot\sin 55{,}06° = 8513{,}8 \cdot 0{,}8198 = 6979{,}6\ \mathrm{A}.$$

Sada iz jednačine (1):

$$E_{0f} = U_f\cos\delta + X_d I_d = \frac{13\,800}{\sqrt{3}}\cdot\cos 23{,}27° + 0{,}9826\cdot 8513{,}8\cdot\sin(31{,}79°+23{,}27°)$$

$$E_{0f} = 7967{,}4\cdot 0{,}9187 + 0{,}9826\cdot 6979{,}6 = 7319{,}6 + 6858{,}2 = 14\,177{,}8 \approx 14\,178\ \mathrm{V}.$$

> **Napomena o originalu:** u zbirci je u ovoj formuli prvi činilac uz $13\,800/\sqrt{3}$ odštampan kao $0{,}9826$ — to je očigledna štamparska greška (slučajno je prepisana vrednost $X_d = 0{,}9826\ \mathrm{\Omega}$), jer na tom mestu mora stajati $\cos\delta = \cos 23{,}27° = 0{,}9187$. Da je zaista množeno sa $0{,}9826$, izašlo bi $14\,687\ \mathrm{V}$; konačni rezultat zbirke, $14\,178\ \mathrm{V}$, odgovara upravo ispravnoj vrednosti $\cos 23{,}27°$, pa je konačan broj u zbirci tačan.

**Šta smo dobili:** ems praznog hoda po fazi od oko $14{,}2\ \mathrm{kV}$ — skoro **dvostruko** veća od faznog napona ($7{,}97\ \mathrm{kV}$). Tolika "rezerva" emsa je bila potrebna da pokrije velike padove na reaktansama pri nazivnoj struji (seti se: $x_d = 1{,}05$, dakle pad na $X_d$ pri nazivnoj struji je reda samog nazivnog napona!).

### Korak 8: Porast napona neposredno nakon isključenja

**Zašto ovaj korak:** ovo je direktan odgovor na pitanje zadatka. Posle isključenja je $I_f = 0$, pa na krajevima ostane $U_f' = E_{0f}$ (mini-lekcija 6); porast je odnos tog novog napona i napona pre isključenja.

$$\text{porast} = \frac{E_{0f}}{U_{\mathrm{n}f}} = \frac{E_{0f}}{U_{\mathrm{n}}/\sqrt{3}} = \frac{14\,178}{13\,800/\sqrt{3}} = \frac{14\,178}{13\,800}\cdot\sqrt{3} = 1{,}0274\cdot 1{,}7321 = 1{,}78 \approx 1{,}8.$$

(Zapis $\dfrac{14\,178}{13\,800}\cdot\sqrt{3}$ je samo algebarski preuređen isti razlomak: deljenje sa $13\,800/\sqrt{3}$ isto je što i množenje sa $\sqrt{3}/13\,800$ — tako je napisano i u zbirci.)

**Šta smo dobili:** napon generatora neposredno nakon isključenja prekidača skoči na približno **1,8 puta nazivnu vrednost** — porast od oko 78–80%. Zato posle naglog rasterećenja regulator pobude mora što brže da obori pobudnu struju (tzv. razbuđivanje), a oprema na sabirnicama generatora mora biti dimenzionisana da ovakav privremeni prenapon izdrži.

## Česte greške i zamke

1. **Mešanje linijskog i faznog napona.** U jednačinama fazorskog dijagrama figuriše **fazni** napon $U_f = 13\,800/\sqrt{3} = 7967{,}4\ \mathrm{V}$, a ne linijski $13\,800\ \mathrm{V}$. Ako uvrstiš linijski, i $\delta$ i $E_{0f}$ ispadnu potpuno pogrešni. Ista zamka vreba i na kraju: $E_{0f}$ je fazna veličina, pa se porast računa prema **faznom** nazivnom naponu — ko izračuna $14\,178/13\,800 = 1{,}03$ i zaključi "porast je zanemarljiv, svega 3%", promašio je suštinu za faktor $\sqrt{3}$.
2. **Pogrešan ugao struje prema osama.** Komponente struje su $I_q = I_f\cos(\delta+\varphi)$ i $I_d = I_f\sin(\delta+\varphi)$ — ugao struje prema q-osi je $\delta+\varphi$, a **ne** samo $\varphi$ (jer $\varphi$ struja zaklapa sa naponom, a napon je već zarotiran za $\delta$ od q-ose). Ko napiše $I_q = I_f\cos\varphi$, dobija pogrešan $\delta$ i pogrešnu $E_{0f}$.
3. **Zamena uloga $X_d$ i $X_q$.** U jednačini po d-osi (2) stoji $X_q$ (jer pad $\mathrm{j}X_q I_q$ leži na d-osi), a u jednačini po q-osi (1) stoji $X_d$ (jer pad $\mathrm{j}X_d I_d$ leži na q-osi). Deluje "obrnuto" od očekivanog i baš zato se često pogreši — vrati se na mini-lekciju 4: množenje sa $\mathrm{j}$ zaokreće fazor za 90°, pa pad "preskoči" na suprotnu osu od svoje struje.
4. **Kalkulator u pogrešnom režimu.** Uglovi su ovde u stepenima ($31{,}79°$, $23{,}27°$, $55{,}06°$); kalkulator podešen na radijane daje besmislene sinuse i kosinuse, a greška se lako previdi jer brojevi "liče" na razumne.
5. **Slepo prepisivanje iz zbirke.** U originalu je u formuli za $E_{0f}$ odštampano $0{,}9826$ umesto $\cos 23{,}27° = 0{,}9187$ (videti napomenu u Koraku 7). Ko mehanički prepiše, dobiće $14\,687\ \mathrm{V}$ i neće moći da reprodukuje konačan rezultat zbirke. Pouka: svaki broj u formuli mora imati jasno poreklo.

## Rezime rezultata

| Veličina | Oznaka | Vrednost |
|---|---|---|
| Bazna impedansa | $Z_b$ | $0{,}9358\ \mathrm{\Omega}$ |
| Sinhrona reaktansa po d-osi | $X_d$ | $0{,}9826\ \mathrm{\Omega}$ |
| Sinhrona reaktansa po q-osi | $X_q$ | $0{,}6457\ \mathrm{\Omega}$ |
| Nazivna fazna struja | $I_{\mathrm{n}f}$ | $8513{,}8\ \mathrm{A}$ |
| Ugao faktora snage | $\varphi$ | $31{,}79°$ ($\sin\varphi = 0{,}5268$) |
| Ugao opterećenja | $\delta$ | $23{,}27°$ |
| Ems praznog hoda (fazna) | $E_{0f}$ | $14\,178\ \mathrm{V}$ |
| **Porast napona nakon isključenja** | $E_{0f}/U_{\mathrm{n}f}$ | $\mathbf{\approx 1{,}8}$ (tačnije $1{,}78$) |

## Provera smisla

1. **Dimenziona provera bazne impedanse.** $Z_b = U_{\mathrm{n}}^2/S_{\mathrm{n}}$: jedinica je $\mathrm{V^2/VA} = \mathrm{V^2 \cdot (V\cdot A)^{-1}} = \mathrm{V/A} = \Omega$ — impedansa, kako i treba. A uvrštavanje u $\mathrm{kV}$ i $\mathrm{MVA}$ je korektno jer je $\mathrm{(10^3\,V)^2/(10^6\,VA)} = \mathrm{10^6\,V^2/10^6\,VA} = \Omega$.
2. **Granični slučaj — prazan hod.** Da je generator pre isključenja bio neopterećen ($I_f = 0$), jednačina (2) bi dala $U_f\sin\delta = 0 \Rightarrow \delta = 0$, a jednačina (1) $E_{0f} = U_f$ — porast bi bio tačno 1 (nema skoka). Naše formule se, dakle, u graničnom slučaju svode na očekivani rezultat: skok napona postoji samo zato što je mašina bila opterećena (i to sa jakom pobudom zbog induktivnog $\cos\varphi$).
3. **Nezavisna gruba procena drugim modelom.** Zanemarimo isturenost polova i tretirajmo mašinu kao da ima samo jednu reaktansu $X_d$ (model valjkastog rotora): tada je $E \approx \left|\underline{U}_f + \mathrm{j}X_d\underline{I}_f\right| = \sqrt{(U_f + X_d I_f\sin\varphi)^2 + (X_d I_f\cos\varphi)^2}$. Sa brojevima: $X_d I_f = 0{,}9826\cdot 8513{,}8 = 8365{,}7\ \mathrm{V}$, pa je $E \approx \sqrt{(7967{,}4 + 8365{,}7\cdot 0{,}5268)^2 + (8365{,}7\cdot 0{,}85)^2} = \sqrt{12\,374{,}5^2 + 7110{,}8^2} \approx 14\,272\ \mathrm{V}$, tj. odnos $14\,272/7967{,}4 \approx 1{,}79$. Tačan dvoosni proračun dao je $1{,}78$ — dva nezavisna puta daju praktično isti skok, što jako učvršćuje poverenje u rezultat ($\approx 1{,}8$).
4. **Poređenje sa iskustvom.** Za sinhrone generatore sa $x_d$ oko 1 i induktivnim nazivnim $\cos\varphi$, ems praznog hoda pri punoj pobudi tipično iznosi 1,5–2 nazivna napona — naš rezultat od $1{,}78$ pada tačno u taj opseg. Upravo zbog ovakvih skokova hidrogeneratori imaju brzo razbuđivanje i prenaponsku zaštitu na sabirnicama.
