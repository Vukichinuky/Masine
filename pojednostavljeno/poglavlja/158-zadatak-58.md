# Zadatak 58 — Monofazni kondenzatorski motor: kompletna teorija monofaznog motora i proračun startnog kondenzatora

## Postavka

Monofazni kondenzatorski motor snage $2{,}5\ \mathrm{kW}$, napona $220\ \mathrm{V}$, učestanosti $50\ \mathrm{Hz}$, ima sledeće impedanse namotaja pri startu (pri zakočenom rotoru):

- glavna faza: $\underline{Z}_g = R_g + jX_g = 15{,}1 + j\,12{,}4\ \mathrm{\Omega}$,
- pomoćna faza: $\underline{Z}_p = R_p + jX_p = 31{,}9 + j\,11{,}7\ \mathrm{\Omega}$.

Kolika je kapacitivnost kondenzatora koji treba vezati na red (redno) sa pomoćnom fazom da bi se pri startu imao fazni pomeraj između struja glavne i pomoćne faze od $90^\circ$ (da bi se dobilo približno simetrično obrtno polje)?

> **Prevod na običan jezik:** Imamo mali motor koji se priključuje na običnu kućnu monofaznu mrežu (220 V, 50 Hz). Takav motor ima **dva namotaja na statoru**: glavni i pomoćni. Problem monofaznih motora je što sami od sebe **ne mogu da krenu** — zato se u pomoćni namotaj dodaje kondenzator, koji "zakrivi" struju pomoćnog namotaja tako da ona vremenski prednjači. Ako struje kroz dva namotaja budu pomerene za tačno $90^\circ$ jedna prema drugoj, u motoru nastaje obrtno polje slično onome u trofaznom motoru, i motor kreće sam. Za oba namotaja nam je izmereno koliko "koče" struju (impedansa) dok rotor još stoji. Treba da izračunamo **koliki kondenzator** (koliko mikrofarada) da stavimo na red sa pomoćnim namotajem pa da se ta razlika od $90^\circ$ zaista dobije u trenutku starta.

Šemu veze ovakvog motora prikazuje slika 58.1: sa mreže napona $\underline{U}$ uzima se ukupna struja $\underline{I}$, koja se grana na struju glavne faze $\underline{I}_g$ (kroz impedansu $\underline{Z}_g$) i struju pomoćne faze $\underline{I}_p$; u granu pomoćne faze redno su vezani prekidač, kondenzator $C$ i namotaj pomoćne faze $\underline{Z}_p$, pa je struja kroz namotaj pomoćne faze označena sa $\underline{I}_{p,C}$ (ista struja teče kroz kondenzator i kroz namotaj, jer su redno vezani).

![Šema veze jednofaznog motora sa glavnom fazom Zg i pomoćnom fazom Zp sa rednim kondenzatorom C](../slike/fig-58.1.png)

**Slika 58.1 —** Šema veze jednofaznog motora: paralelno na mrežni napon $\underline{U}$ vezane su glavna faza ($\underline{Z}_g$) i pomoćna faza ($\underline{Z}_p$) sa redno vezanim kondenzatorom $C$ i prekidačem.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna snaga | $P_{\mathrm{n}}$ | $2{,}5\ \mathrm{kW}$ | Mehanička snaga koju motor trajno daje na vratilu; ovde služi samo za orijentaciju o "veličini" motora. |
| Nazivni napon | $U$ | $220\ \mathrm{V}$ | Efektivna vrednost monofaznog mrežnog napona na koji se motor priključuje. |
| Učestanost mreže | $f$ | $50\ \mathrm{Hz}$ | Broj perioda naizmeničnog napona u sekundi; određuje kružnu učestanost $\omega = 2\pi f$. |
| Impedansa glavne faze (zakočen rotor) | $\underline{Z}_g = R_g + jX_g$ | $15{,}1 + j\,12{,}4\ \mathrm{\Omega}$ | Ukupno "protivljenje" glavnog namotaja proticanju naizmenične struje u trenutku starta: $R_g = 15{,}1\ \mathrm{\Omega}$ je aktivna (omska) otpornost, $X_g = 12{,}4\ \mathrm{\Omega}$ induktivna reaktansa. |
| Impedansa pomoćne faze (zakočen rotor) | $\underline{Z}_p = R_p + jX_p$ | $31{,}9 + j\,11{,}7\ \mathrm{\Omega}$ | Isto to za pomoćni namotaj: $R_p = 31{,}9\ \mathrm{\Omega}$, $X_p = 11{,}7\ \mathrm{\Omega}$. Pomoćni namotaj je namerno "otporniji" (tanja žica, više navojaka). |
| Traženi fazni pomeraj struja | $\varphi_{gp}$ | $90^\circ$ | Ugao za koji struja pomoćne faze treba vremenski da prednjači struji glavne faze pri startu, da bi polje bilo približno kružno (simetrično). |

**Traži se:** kapacitivnost $C$ kondenzatora u rednoj vezi sa pomoćnom fazom.

Napomena o oznakama: crta ispod slova ($\underline{Z}$, $\underline{I}$, $\underline{U}$) označava **kompleksnu veličinu** (fazor ili kompleksnu impedansu). Impedanse su date "pri zakočenom rotoru" — to je upravo stanje u trenutku starta, jer rotor još ne rotira; zato ove vrednosti smemo da koristimo direktno za proračun startnog kondenzatora.

## Šta se traži i zašto

Traži se samo jedna veličina, ali je put do nje popločan celokupnom teorijom monofaznog asinhronog motora, koju ćemo zato detaljno izložiti.

**Kapacitivnost kondenzatora $C$.** Zašto bi to inženjera zanimalo? Monofazni motor bez pomoćne faze **nema polazni moment** — priključen na mrežu, zuji i stoji u mestu. Kondenzator u pomoćnoj fazi je najjeftiniji i najčešći način da se motor "prevari" da vidi obrtno polje i krene sam (mašina za veš, frižider, mala pumpa, ventilator — svi oni imaju ovakav kondenzator). Ako kondenzator izaberemo pogrešno, motor kreće slabo, trza ili uopšte ne kreće, a kondenzator može i da pregori. Dakle, dimenzionisanje kondenzatora je standardan, praktičan inženjerski zadatak.

**Plan rešavanja (4 koraka):**

1. Iz impedanse glavne faze izračunamo ugao $\varphi_g$ za koji struja glavne faze **kasni** za naponom (jer je glavni namotaj otporno-induktivan).
2. Iz uslova simetričnog polja ($\varphi_{gp} = \varphi_g - \varphi_p = 90^\circ$) izračunamo koliki mora biti fazni stav $\varphi_p$ struje pomoćne faze — ispašće negativan, tj. struja pomoćne faze mora da **prednjači** naponu.
3. Napišemo ukupnu impedansu pomoćne grane sa kondenzatorom, $\underline{Z}_u = R_p + j(X_p + X_C)$, i iz zahtevanog ugla $\varphi_p$ izračunamo potrebnu reaktansu kondenzatora $X_C$ (biće negativna — kapacitivna).
4. Iz $X_C$ i poznate učestanosti mreže izračunamo kapacitivnost $C = -1/(\omega X_C)$.

## Potrebna teorija — mini-lekcije

Originalna zbirka u okviru ovog zadatka izlaže celu teoriju monofaznog asinhronog motora. Prenosimo je u celini, pojednostavljenu, jer bez nje ni uslov "$90^\circ$ između struja" ni sam smisao kondenzatora nisu jasni.

### Mini-lekcija 1: Fazori, impedansa i fazni stav struje

U kolu naizmenične struje učestanosti $f$ sve struje i naponi su sinusoide iste učestanosti, pa se svaka veličina može opisati sa samo dva podatka: **amplitudom** (odnosno efektivnom vrednošću) i **početnom fazom** (uglom). Takav zapis se zove **fazor** i piše se kao kompleksan broj, npr. $\underline{I} = I e^{j\alpha}$, gde je $I$ efektivna vrednost, a $\alpha$ fazni ugao.

**Impedansa** rednog kola sa otpornikom $R$ i reaktansom $X$ je kompleksan broj

$$\underline{Z} = R + jX,$$

gde je $R$ aktivna (omska) otpornost (troši energiju, pretvara je u toplotu), a $X$ **reaktansa** — "protivljenje" koje potiče od magnetnog polja kalema ($X_L = \omega L > 0$, induktivna) ili od električnog polja kondenzatora ($X_C = -1/(\omega C) < 0$, kapacitivna; znak minus je stvar konvencije koju ovde dosledno koristimo — kapacitivna reaktansa se u zbir $X$ unosi kao negativan broj).

Struja kroz impedansu priključenu na napon $\underline{U}$ je $\underline{I} = \underline{U}/\underline{Z}$. Ako napon uzmemo za referencu (fazni ugao nula), onda struja ima fazni ugao $-\varphi$, gde je

$$\varphi = \arctan\!\frac{X}{R}$$

ugao (argument) impedanse. Tumačenje koje ćemo stalno koristiti:

- $X > 0$ (pretežno induktivno kolo) $\Rightarrow \varphi > 0 \Rightarrow$ struja **kasni** za naponom za ugao $\varphi$;
- $X < 0$ (pretežno kapacitivno kolo) $\Rightarrow \varphi < 0 \Rightarrow$ struja **prednjači** naponu za ugao $|\varphi|$.

Intuicija: kalem se "opire" promeni struje, pa struja kroz njega uvek "zaostaje" za naponom; kondenzator mora prvo da se napuni strujom da bi se na njemu pojavio napon, pa struja kroz njega "žuri" ispred napona. Upravo tu osobinu kondenzatora ćemo iskoristiti: dodavanjem dovoljno velike kapacitivne reaktanse u pomoćnu granu, njena struja će iz "kasni" preći u "prednjači".

### Mini-lekcija 2: Pulsirajuće polje i Leblanova teorema — zašto čist monofazni motor ne kreće sam

Krenimo od najprostijeg slučaja: motor koji na statoru ima **samo jedan** namotaj, priključen na monofazni napon. Takav "čist" jednofazni asinhroni motor prikazuje slika 58.2: levo je električna šema (namotaj statora između faznog provodnika i nule, kroz njega struja $I_1$), a desno poprečni presek statora. Na desnom crtežu čitaj ovako: sivi vertikalni vektor $\theta_1$ je trenutna magnetopobudna sila (mps) namotaja — ona **pulsira** duž jedne jedine ose (raste, opada, menja znak, ali ne menja pravac); plavi vektor $\theta_d$ i ružičasti vektor $\theta_i$ su dve **obrtne** komponente na koje se pulsirajuća mps može razložiti — obe rotiraju sinhronom brzinom $\Omega_s$, ali u **suprotnim smerovima** (strelice pokazuju smerove), i u svakom trenutku njihov zbir daje pulsirajući vektor $\theta_1$.

![Principijelna šema čistog jednofaznog asinhronog motora i razlaganje pulsirajuće mps na dve obrtne komponente](../slike/fig-58.2.png)

**Slika 58.2 —** Principijelna šema čistog jednofaznog asinhronog motora: jedan statorski namotaj stvara pulsirajuću mps $\theta_1$, koja se razlaže na direktnu ($\theta_d$) i inverznu ($\theta_i$) obrtnu komponentu, svaka upola manje amplitude, koje rotiraju brzinom $\Omega_s$ u suprotnim smerovima.

To razlaganje je **Leblanova teorema** i nije nikakva magija, nego obična trigonometrija. Mps jednog namotaja raspoređena je duž vazdušnog zazora kao $\cos x$ (gde je $x$ električni ugao položaja duž obima), a u vremenu pulsira kao $\cos\omega t$, dakle:

$$\Theta(x,t) = \Theta_m \cos(\omega t)\cos(x).$$

Primenimo identitet za proizvod kosinusa, $\cos a \cos b = \tfrac{1}{2}\big[\cos(a-b) + \cos(a+b)\big]$:

$$\Theta(x,t) = \underbrace{\frac{\Theta_m}{2}\cos(x - \omega t)}_{\text{direktni talas}} + \underbrace{\frac{\Theta_m}{2}\cos(x + \omega t)}_{\text{inverzni talas}}.$$

Prvi sabirak je talas koji putuje u smeru porasta $x$ (**direktno polje**), drugi talas putuje u suprotnom smeru (**inverzno polje**); oba imaju **polovinu** amplitude prvobitnog pulsirajućeg polja i rotiraju sinhronom brzinom. Ovaj faktor $\tfrac{1}{2}$ zapamti — pojaviće se u ekvivalentnoj šemi (Mini-lekcija 4).

**Zašto motor ne kreće?** Svako od ta dva obrtna polja "vuče" rotor za sobom kao kod običnog asinhronog motora, ali u suprotnim smerovima. Dok rotor **stoji**, on je prema oba polja u potpuno istom položaju (oba klize preko njega istom relativnom brzinom), pa su momenti jednaki po intenzitetu i suprotni po smeru — rezultantni moment je **nula**. Motor zuji i stoji.

**Zašto nastavi da se okreće ako ga gurnemo?** Ako rotor mehanički pokrenemo u jednu stranu, situacija prestaje da bude simetrična. Za polje koje rotira u istom smeru kao rotor (**direktno polje**) relativna brzina klizanja rotora opada, pa opada i učestanost struja koje to polje indukuje u rotoru; sa manjom učestanošću opada induktivna otpornost rotorskog kola, pa raste **aktivna komponenta** rotorske struje — a baš ta komponenta pravi moment. Za polje suprotnog smera (**inverzno polje**) dešava se sve obrnuto: učestanost rotorskih struja raste, induktivna otpornost raste, aktivna komponenta struje opada, moment slabi. Zaključak: čim se rotor pokrene, direktno polje "pobedi", javlja se neto moment u smeru pokretanja, motor ubrzava i može da savlada opterećenje. Problem je, dakle, samo **polazak** — i ceo ostatak ovog zadatka bavi se time kako polazak obezbediti.

### Mini-lekcija 3: Monofazni motor kao dva trofazna motora na istom vratilu; klizanje prema direktnom i inverznom polju

Prethodna slika sugeriše korisnu misaonu konstrukciju: pošto u monofaznom motoru istovremeno postoje **dva** obrtna polja suprotnih smerova, monofazni motor se može predstaviti kao **dva trofazna motora čiji su rotori kruto spojeni istim vratilom**, a statorski namotaji su priključeni na trofaznu mrežu sa **različitim redosledom faza** (zamena redosleda dve faze obrće smer obrtnog polja). To prikazuje slika 58.3: gore su tri fazna provodnika $L_1, L_2, L_3$; levi motor je priključen jednim redosledom i stvara polje $n_d$ (plava strelica, jedan smer), desni motor je priključen izmenjenim redosledom i stvara polje $n_i$ (ružičasta strelica, suprotan smer); oba rotora su spojena sivim vratilom i obrću se zajedničkom brzinom $n$.

![Predstavljanje monofaznog asinhronog motora pomoću dva trofazna motora sa zajedničkim vratilom i suprotnim redosledom faza](../slike/fig-58.3.png)

**Slika 58.3 —** Predstavljanje monofaznog asinhronog motora sa dva trofazna: rotori su mehanički spojeni vratilom (zajednička brzina $n$), a statori su priključeni na mrežu sa suprotnim redosledom faza, pa jedan stvara direktno polje ($n_d$), a drugi inverzno ($n_i$). Pri mirovanju su njihovi momenti jednaki i suprotni, pa se sklop ne može sam pokrenuti.

Za svaki od ta dva fiktivna motora definiše se **klizanje** — relativna razlika brzine polja i brzine rotora. Podsetnik: klizanje je mera "koliko rotor zaostaje za poljem"; za polje brzine $n_s$ i rotor brzine $n$ klizanje je $(n_s - n)/n_s$.

**Klizanje prema direktnom polju** (polje brzine $+n_s$, isti smer kao usvojeni pozitivan smer obrtanja rotora):

$$s_d = \frac{n_s - n}{n_s} = s.$$

To je obično, "školsko" klizanje $s$, isto kao kod trofaznog motora.

**Klizanje prema inverznom polju** (polje brzine $-n_s$, suprotan smer): u istu definiciju uvrstimo $-n_s$ umesto $n_s$:

$$s_i = \frac{-n_s - n}{-n_s}.$$

Izvedimo dokle god se ne pojavi $s$. Podelimo brojilac i imenilac sa $-n_s$:

$$s_i = \frac{-n_s - n}{-n_s} = \frac{n_s + n}{n_s} = 1 + \frac{n}{n_s}.$$

Iz definicije direktnog klizanja je $n = n_s(1-s)$, pa je $n/n_s = 1-s$, i konačno:

$$s_i = 1 + (1 - s) = 2 - s.$$

Provera na dva granična slučaja: pri mirovanju ($n=0$, tj. $s=1$) oba klizanja su jednaka, $s_d = s_i = 1$ — rotor je prema oba polja u istom položaju, što je tačno slika situacije "motor ne može sam da krene". Pri sinhronoj brzini direktnog polja ($s=0$) inverzno klizanje je $s_i = 2$ — rotor "seče" inverzno polje dvostrukom sinhronom brzinom, pa su učestanosti struja koje inverzno polje indukuje u rotoru veoma visoke (blizu $2f$), njihova aktivna komponenta mala, i inverzno polje tada pravi samo mali kočioni moment i dodatne gubitke.

### Mini-lekcija 4: Ekvivalentna šema monofaznog asinhronog motora

Kod trofaznog asinhronog motora jedna faza se predstavlja poznatom ekvivalentnom šemom: redno statorska otpornost $R_s$ i statorska rasipna reaktansa $X_{\gamma s}$, zatim paralelna magnetizaciona grana $X_\mu$ (grana koja "pravi" obrtno polje), i rotorska grana sa svedenom rasipnom reaktansom $X'_{\gamma r}$ i svedenom otpornošću $R'_r/s$ (kroz koju se modeluju i gubici u bakru rotora i mehanička snaga; apostrof označava da su rotorske veličine svedene na statorsku stranu).

Pošto smo monofazni motor predstavili kao **redno vezana dva trofazna motora** — jedan koji kliže prema direktnom polju sa klizanjem $s$, i jedan koji kliže prema inverznom polju sa klizanjem $2-s$ — njegova ekvivalentna šema se dobija **rednim vezivanjem dve trofazne ekvivalentne šeme**, s tim što svaka od njih nosi faktor $\tfrac{1}{2}$: svako od dva obrtna polja ima po **polovinu** amplitude ukupnog pulsirajućeg polja (Leblanova teorema iz Mini-lekcije 2), pa se svakom polju pripisuje po polovina parametara.

To prikazuje slika 58.4, koju čitaj ovako. **Leva polovina slike:** dva pod-kola vezana na red, kroz oba teče ista statorska struja $\underline{I}_1$. Gornje pod-kolo je "direktna mašina": redno $\tfrac{1}{2}R_s$ i $\tfrac{1}{2}X_{\gamma s}$, paralelna magnetizaciona grana $\tfrac{1}{2}X_\mu$ (kroz nju struja $\underline{I}_{\mu d}$), rotorska grana $\tfrac{1}{2}X'_{\gamma r}$ i $\tfrac{1}{2}\dfrac{R'_r}{s}$ (kroz nju struja $\underline{I}'_{rd}$); napon na ovom pod-kolu je $\underline{U}_{1d} = \tfrac{1}{2}\underline{Z}_d\,\underline{I}_1$, gde je $\underline{Z}_d$ ukupna impedansa trofazne šeme pri klizanju $s$. Donje pod-kolo je "inverzna mašina": identično, samo je u rotorskoj grani $\tfrac{1}{2}\dfrac{R'_r}{2-s}$ (klizanje $2-s$), struje su $\underline{I}_{\mu i}$ i $\underline{I}'_{ri}$, napon $\underline{U}_{1i} = \tfrac{1}{2}\underline{Z}_i\,\underline{I}_1$. **Desna polovina slike:** ista stvar, samo su statorski elementi sabrani ($\tfrac{1}{2}R_s + \tfrac{1}{2}R_s = R_s$, isto za $X_{\gamma s}$), pa je ukupan napon na motoru

$$\underline{U}_1 = \underline{U}_{1d} + \underline{U}_{1i} = \frac{1}{2}\big(\underline{Z}_d + \underline{Z}_i\big)\,\underline{I}_1.$$

![Ekvivalentna šema jednofaznog asinhronog motora: redna veza direktne i inverzne polušeme](../slike/fig-58.4.png)

**Slika 58.4 —** Ekvivalentna šema jednofaznog asinhronog motora: redna veza polovina ekvivalentnih šema dva trofazna motora — direktnog (rotorska otpornost $\tfrac{1}{2}R'_r/s$) i inverznog (rotorska otpornost $\tfrac{1}{2}R'_r/(2-s)$). Levo: razdvojeno na dva pod-kola sa naponima $\underline{U}_{1d}$ i $\underline{U}_{1i}$; desno: sažeta šema sa objedinjenim statorskim elementima $R_s$, $X_{\gamma s}$.

Fizičko čitanje šeme: pri mirovanju ($s=1$) obe rotorske otpornosti su jednake ($R'_r/1 = R'_r/(2-1)$), obe polušeme su identične — potpuna simetrija, nula momenta. Kako motor ubrzava ($s \to 0$), otpornost direktne grane $\tfrac{1}{2}R'_r/s$ raste (velika aktivna snaga se "predaje" mehanici), a inverzne $\tfrac{1}{2}R'_r/(2-s) \to \tfrac{1}{2}R'_r/2$ postaje mala — inverzna polušema se ponaša skoro kao kratak spoj koji samo pravi gubitke i mali kočioni moment.

### Mini-lekcija 5: Mehanička (momentna) karakteristika monofaznog motora

Elektromagnetni moment monofaznog motora dobija se **sabiranjem** momenata koje prave direktno i inverzno polje:

$$M(s) = M_d(s) + M_i(s),$$

za ceo opseg klizanja od $s=0$ (rotor na sinhronoj brzini direktnog polja) do $s=2$ (rotor na sinhronoj brzini inverznog polja, tj. obrće se "unazad" punom brzinom). $M_d(s)$ je obična momentna karakteristika trofaznog motora; $M_i(s)$ je ista takva karakteristika, ali za polje suprotnog smera, pa deluje suprotnim (negativnim) momentom.

Rezultat prikazuje slika 58.5, koju čitaj ovako: horizontalna osa je brzina $n$ (od $-n_s$ levo do $+n_s$ desno; ispod ose su upisane odgovarajuće vrednosti klizanja: $s=2$ pri $n=-n_s$, $s=1$ pri $n=0$, $s=0$ pri $n=n_s$), vertikalna osa je moment $M$. Crvena kriva je $M_d(s)$ (moment direktnog polja), zelena je $M_i(s)$ (moment inverznog polja, negativan), a siva isprekidana kriva je njihov zbir $M(s) = M_d(s) + M_i(s)$ — stvarna karakteristika monofaznog motora. Desno na slici je podsetnik da se radi o čistom monofaznom motoru (jedan namotaj na mreži).

![Mehanička karakteristika jednofaznog asinhronog motora kao zbir direktne i inverzne komponente momenta](../slike/fig-58.5.png)

**Slika 58.5 —** Mehanička karakteristika jednofaznog asinhronog motora: $M(s) = M_d(s) + M_i(s)$. U tački $n=0$ ($s=1$) rezultantni moment je nula — **motor nema polazni moment**; čim se zavrti u bilo koju stranu, javlja se neto moment u tom smeru.

Dva ključna zapažanja sa slike (oba iz originala):

1. **Odsustvo polaznog momenta**: siva kriva prolazi kroz nulu baš pri $n=0$ ($s=1$), jer su tamo $M_d$ i $M_i$ jednaki i suprotni. To je grafička potvrda zaključka iz Mini-lekcije 2.
2. **Veće nazivno klizanje nego kod trofaznog motora iste snage**: primeti da rezultantna kriva seče nulu momenta **pre** sinhrone brzine — pri $s=0$ direktno polje više ne pravi moment ($M_d = 0$), ali inverzno i dalje koči ($M_i < 0$), pa je ukupan moment negativan. Radna tačka sa pozitivnim momentom mora zato biti na nešto nižoj brzini (većem klizanju) nego kod trofaznog motora; uz to inverzno polje stalno pravi dodatne gubitke, pa je i stepen iskorišćenja manji.

### Mini-lekcija 6: Pomoćna faza — kako se pravi obrtno polje iz monofazne mreže

Monofazni motor će moći sam da krene ako u njemu pri startu nastane **rezultantno obrtno polje** (a ne čisto pulsirajuće). Da se motor ne bi pokretao mehanički (rukom!), na stator se, pored glavnog, postavlja **pomoćni namotaj (pomoćna faza)**, koji je **prostorno pomeren** u odnosu na glavni (tipično za $90^\circ$ električnih — smešten je u žlebove "između" glavnog namotaja). Ali prostorni pomeraj sam po sebi nije dovoljan: da bi dva namotaja napravila obrtno polje, njihove struje moraju biti pomerene i **vremenski** (fazno). Pošto su oba namotaja priključena na isti napon, fazna razlika struja se pravi tako što se u pomoćnu fazu redno doda element drugačijeg karaktera — **otpornik, kondenzator ili prigušnica** (zajednički naziv: **predspojna naprava**).

To prikazuje slika 58.6: glavni namotaj je vezan direktno na mrežu ($L_1$–$N$, kroz njega struja $I_1$), a pomoćni namotaj (crveno) na istu mrežu, ali preko jednog od tri moguća redna elementa: otpornika $R_p$, kondenzatora $C_p$ ili prigušnice $L_p$ (na slici su nacrtane sve tri varijante, u praksi se bira jedna). Plavi blok označen "$n>$" je **centrifugalni prekidač**: kada brzina pređe zadatu vrednost, on automatski isključuje pomoćnu granu (o tome više u Mini-lekciji 7).

![Jednofazni motor sa pomoćnom fazom i predspojnom napravom: otpornik, kondenzator ili prigušnica](../slike/fig-58.6.png)

**Slika 58.6 —** Jednofazni asinhroni motor sa dodatim otpornikom ($R_p$), kondenzatorom ($C_p$) ili prigušnicom ($L_p$) u kolu pomoćne faze; "$n>$" je centrifugalni prekidač koji pomoćnu granu isključuje po zaletu.

Od tri mogućnosti kondenzator je ubedljivo najbolji: samo on može da struju pomoćne faze pomeri tako da ona **prednjači** naponu, pa se između struja dve faze može postići razlika do punih $90^\circ$. Otpornik i prigušnica samo *smanjuju* zaostajanje pomoćne struje (razlika ostaje znatno manja od $90^\circ$), daju slabije polazno polje, a otpornik uz to i greje. Zato se u praksi (i u ovom zadatku) koristi **kondenzatorski motor**.

**Šta se dobije kad struje nisu baš "idealne"?** Struje glavnog i pomoćnog namotaja koje su međusobno fazno pomerene (za bilo koji ugao različit od $0^\circ$ i $180^\circ$) proizvode **elipsoidno (eliptično) polje**: rezultantni vektor polja rotira, ali mu se pri rotaciji menja intenzitet — vrh vektora opisuje elipsu umesto kružnice. Elipsoidno polje je i dalje *obrtno* polje: ono se može razložiti na kružnu (direktnu) i inverznu komponentu, i njegova kružna komponenta obrće rotor — dakle motor sa pomoćnom fazom **kreće sam**, samo slabije nego da je polje idealno kružno. To prikazuje slika 58.7: crveni horizontalni vektor $H_g$ je polje glavnog namotaja (spoljašnji, crveni navojci), plavi vertikalni vektor $H_p$ je polje pomoćnog namotaja (unutrašnji, plavi navojci, prostorno pomeren za $90^\circ$); ružičasta isprekidana elipsa je putanja vrha rezultantnog vektora (elipsoidno polje), a svetloplava kružnica u sredini je njegova kružna komponenta — ona koja pravi polazni moment.

![Stvaranje rezultantnog elipsoidnog polja iz polja glavnog i pomoćnog namotaja](../slike/fig-58.7.png)

**Slika 58.7 —** Stvaranje rezultantnog elipsoidnog polja kod jednofaznog asinhronog motora: prostorno upravna polja glavnog ($H_g$) i pomoćnog ($H_p$) namotaja, sa fazno pomerenim strujama, daju obrtno polje promenljivog intenziteta (elipsa) koje sadrži kružnu komponentu.

**Kada je polje savršeno kružno (simetrično)?** Mala računica koja objašnjava ceo zadatak. Neka je glavni namotaj postavljen duž ose $x$, pomoćni duž ose $y$ (prostorni pomeraj $90^\circ$), i neka su im mps jednakih amplituda, a struje pomerene za $90^\circ$ u vremenu:

$$\Theta_x(t) = \Theta_m \cos(\omega t), \qquad \Theta_y(t) = \Theta_m \cos(\omega t - 90^\circ) = \Theta_m \sin(\omega t).$$

Intenzitet rezultantnog vektora je

$$\sqrt{\Theta_x^2 + \Theta_y^2} = \Theta_m\sqrt{\cos^2\omega t + \sin^2\omega t} = \Theta_m = \mathrm{const},$$

a njegov ugao prema osi $x$ je $\arctan(\Theta_y/\Theta_x) = \omega t$ — vektor konstantne dužine koji rotira ugaonom brzinom $\omega$: **kružno obrtno polje**, potpuno isto kao u trofaznom motoru. Dakle, uslovi savršene simetrije su: (1) prostorni pomeraj namotaja $90^\circ$, (2) **vremenski pomeraj struja $90^\circ$**, (3) jednake amplitude mps oba namotaja. Uslov (1) je stvar konstrukcije; uslov (2) je ono što u ovom zadatku podešavamo kondenzatorom; uslov (3) se podešava brojem navojaka i u ovom zadatku nije obuhvaćen — zato postavka kaže "**približno** simetrično polje".

Dakle: strujno kolo pomoćnog namotaja mora imati **drugačiji karakter impedanse** od glavnog, i to takav da fazna razlika struja bude što bliža $90^\circ$. Fazorski dijagram struja kondenzatorskog motora prikazuje slika 58.8: levo je dijagram — vertikalni sivi fazor je mrežni napon $\underline{U}_1$; crveni fazor $\underline{I}_{1g}$ (desno od napona) je struja glavne faze, koja **kasni** za naponom za ugao $\varphi_{1g}$; crveni fazor $\underline{I}_{1p}$ (levo od napona) je struja pomoćne faze sa kondenzatorom, koja **prednjači** naponu za ugao $\varphi_{1p}$; ugao između dve struje je zbir $\varphi_{1g} + \varphi_{1p}$ i njega kondenzatorom teramo na $90^\circ$. Desno na slici je šema veze sa obeleženim krajevima namotaja (U–V glavni, Z–W pomoćni sa kondenzatorom $C_p$).

![Fazorski dijagram struja kondenzatorskog motora: glavna struja kasni, pomoćna prednjači naponu](../slike/fig-58.8.png)

**Slika 58.8 —** Fazorski dijagram struja kondenzatorskog motora: struja glavne faze $\underline{I}_{1g}$ kasni za naponom $\underline{U}_1$ (induktivan karakter), struja pomoćne faze $\underline{I}_{1p}$ prednjači (kapacitivan karakter); ukupan međusobni ugao struja je $\varphi_{1g}+\varphi_{1p}$.

### Mini-lekcija 7: Startni i pogonski kondenzator; poređenje sa trofaznim motorom

Pomoćna faza može da radi na dva načina:

- **Startni (polazni) kondenzator i startna pomoćna faza:** pomoćni namotaj sa kondenzatorom je uključen samo tokom zaleta, a zatim ga centrifugalni prekidač ("$n>$" sa slike 58.6) isključi. Kondenzator se tada bira da dâ simetrično polje **pri startu** ($s=1$, zakočen rotor) — **upravo to se traži u ovom zadatku.** Pomoćni namotaj tada ne mora biti dimenzionisan za trajan rad (sme da bude tanji).
- **Pogonski (radni) kondenzator i pomoćna radna faza:** kondenzator je trajno uključen; tada popravlja i radne (ne samo polazne) karakteristike i približava ih trofaznom motoru. Kapacitivnost se tada bira da polje bude simetrično **pri nazivnom opterećenju**.

Šta se dešava sa momentnom karakteristikom, prikazuje slika 58.9. Čitaj je ovako: levo je šema (pomoćna grana sa $C_p$ i centrifugalnim prekidačem "$n>$"), desno grafik relativnog momenta $M/M_n$ u funkciji relativne brzine $n/n_s$. Puna crvena kriva je karakteristika **sa uključenom** pomoćnom fazom i kondenzatorom: počinje iz tačke **1** pri $n=0$ sa velikim polaznim momentom (oko $2M_n$ — motor sigurno kreće i pod opterećenjem). Kada brzina dostigne oko $0{,}8\,n_s$, prekidač isključi pomoćnu granu — crvena vertikalna strelica ("Isključenje pomoćne faze") označava skok sa kondenzatorske karakteristike na isprekidanu zelenu krivu, koja je karakteristika **čistog monofaznog** motora (bez pomoćne faze; uporedi sa slikom 58.5 — ona pri $n=0$ daje nulu). Motor dalje radi po zelenoj krivoj i ustali se u tački **2**, gde se moment motora izjednači sa momentom tereta $M_T$ (horizontalna siva linija).

![Mehanička karakteristika jednofaznog motora sa startnim kondenzatorom i prelazom na karakteristiku bez pomoćne faze](../slike/fig-58.9.png)

**Slika 58.9 —** Mehanička karakteristika jednofaznog motora sa dodatnim kondenzatorom u pomoćnoj fazi: zalet po kondenzatorskoj karakteristici od tačke 1, isključenje pomoćne faze pri oko $0{,}8\,n_s$, nastavak rada po karakteristici čistog monofaznog motora do radne tačke 2 (presek sa momentom tereta $M_T$).

Koliko se kondenzatorski motor približi trofaznom, pokazuje uporedni prikaz na slici 58.10: sve tri krive su $M/M_n$ u funkciji $n/n_s$. Zelena kriva je **standardni trofazni motor** — polazni moment oko $2M_n$, prevalni preko $3M_n$. Ružičasta je **jednofazni kondenzatorski motor** — ima pristojan polazni moment (kreće sam) i oblik karakteristike sličan trofaznom, ali sa nižim vrednostima. Crvena je **jednofazni motor bez pomoćne faze** — polazni moment tačno nula (kriva kreće iz koordinatnog početka), pa sam ne može da krene. Redosled krivih lepo sumira celu priču: kondenzator "podiže" monofazni motor od neupotrebljivog (crvena) ka skoro-trofaznom (ružičasta), ali trofazni (zelena) ostaje najbolji.

![Poređenje mehaničkih karakteristika trofaznog motora, jednofaznog kondenzatorskog i jednofaznog bez pomoćne faze](../slike/fig-58.10.png)

**Slika 58.10 —** Uporedni prikaz mehaničkih karakteristika: standardni trofazni motor (najveći momenti), jednofazni kondenzatorski motor (srednja kriva), jednofazni motor bez pomoćne faze (bez polaznog momenta).

**Praktična pravila za izbor kondenzatora** (iz originala, vredna pamćenja):

- Kapacitivnost pogonskog (trajno uključenog) kondenzatora bira se tako da polje bude simetrično najčešće pri **nazivnom opterećenju**; pri svakom drugom opterećenju polje nije simetrično (javlja se inverzna komponenta i njeni gubici). Startni kondenzator se bira za simetriju **pri polasku** (zakočen rotor) — kao u ovom zadatku.
- Orijentaciona vrednost za trajan rad: oko $25\!-\!55\ \mathrm{\mu F}$ **po kilovatu** snage motora, za mrežu $230\ \mathrm{V}$.
- Kapacitivnost (uz odgovarajuće dimenzionisanje namotaja) treba da obezbedi: napone glavne i pomoćne faze međusobno pomerene za $90^\circ$; da struje obe faze prave **istu magnetopobudnu silu**; da struje u obe faze imaju isti fazni stav prema svojim naponima; i da obe faze budu dimenzionisane za jednaku snagu (za trajan rad).

### Mini-lekcija 8: Napon na kondenzatoru je veći od mrežnog!

Neočekivana, ali za praksu presudna činjenica: **napon na kondenzatoru je znatno veći od napona mreže**. Za motor priključnog napona $230\ \mathrm{V}$ mora se odabrati kondenzator nazivnog napona $450\!-\!550\ \mathrm{V}$ — ko ugradi kondenzator "na 230 V", brzo će ga proburiti proboj.

Zašto je to tako, vidi se iz fazorskog dijagrama napona i struja na slici 58.11. Čitaj je ovako: levo je šema (glavna grana sa strujom $I_{1g}$, pomoćna grana sa kondenzatorom $C_p$ i strujom $I_{1p}$); desno je fazorski dijagram. Napon mreže je ujedno napon na glavnom namotaju: $\underline{U}_{1g} = \underline{U}_1$ (sivi vertikalni fazor). Struja glavne faze $\underline{I}_{1g}$ (crveno, desno) kasni za njim za $\varphi_{1g}$; struja pomoćne grane $\underline{I}_{1p}$ (crveno, levo) prednjači; $\underline{I}_1$ je ukupna struja iz mreže (zbir). Mrežni napon se u pomoćnoj grani **deli** na napon namotaja pomoćne faze $\underline{U}_{1p}$ (ružičasti fazor, usmeren ulevo) i napon kondenzatora $\underline{U}_C$ (zeleni fazor, dugačak, ka gore-levo):

$$\underline{U}_1 = \underline{U}_{1p} + \underline{U}_C.$$

Pri simetričnom polju napon pomoćnog namotaja $\underline{U}_{1p}$ stoji pod $90^\circ$ prema $\underline{U}_{1g}$ (ugao $90^\circ$ je ucrtan na dijagramu). Pošto fazori $\underline{U}_{1p}$ i $\underline{U}_C$ sa fazorom $\underline{U}_1$ zatvaraju trougao u kome je $\underline{U}_C$ hipotenuzasta "duga" stranica, intenzitet $U_C$ ispada **veći od $U_1$** — na slici se jasno vidi da je zeleni fazor najduži na celom dijagramu. Fizički: kroz kondenzator teče cela struja pomoćne grane, a njegova reaktansa je velika (mora da "preokrene" karakter grane iz induktivnog u kapacitivni), pa je proizvod $U_C = I_{1p}\,|X_C|$ velik.

![Fazorski dijagram napona i struja jednofaznog motora sa kondenzatorom: napon kondenzatora veći od mrežnog](../slike/fig-58.11.png)

**Slika 58.11 —** Fazorski dijagram napona i struja jednofaznog motora sa kondenzatorom u pomoćnoj fazi: mrežni napon $\underline{U}_1 = \underline{U}_{1g}$ deli se na napon pomoćnog namotaja $\underline{U}_{1p}$ (pod $90^\circ$ prema $\underline{U}_{1g}$ pri simetriji) i napon kondenzatora $\underline{U}_C$, koji je po intenzitetu **veći** od mrežnog — zato se biraju kondenzatori nazivnog napona $450\!-\!550\ \mathrm{V}$ za mrežu $230\ \mathrm{V}$.

Time je teorijski uvod zaokružen i možemo na račun.

## Rešenje, korak po korak

### Korak 1: Fazni stav struje glavne faze pri startu

**Zašto ovaj korak:** Uslov zadatka je fazni pomeraj od $90^\circ$ **između struja** dve faze. Da bismo znali gde treba da "stoji" struja pomoćne faze, prvo moramo da utvrdimo gde stoji struja glavne faze — a nju određuje impedansa glavnog namotaja, jer je on vezan direktno na mrežni napon.

Glavna faza je otporno-induktivno kolo ($R_g$, $X_g > 0$), pa njena struja **kasni** za naponom (Mini-lekcija 1) za ugao jednak argumentu impedanse:

$$\varphi_g = \arctan\!\frac{X_g}{R_g}.$$

Ovde je $\varphi_g$ ugao kašnjenja struje glavne faze za naponom, $X_g$ induktivna reaktansa, a $R_g$ aktivna otpornost glavnog namotaja pri zakočenom rotoru. Uvrstimo brojeve:

$$\varphi_g = \arctan\!\left(\frac{12{,}4}{15{,}1}\right) = \arctan(0{,}82119) = 39{,}3925^\circ.$$

Međukorak za proveru: $12{,}4 / 15{,}1 = 0{,}82119$, a $\arctan(0{,}82119) = 39{,}3925^\circ$ (kalkulator u režimu stepeni!).

**Šta smo dobili:** Struja glavne faze pri startu kasni za mrežnim naponom za oko $39{,}4^\circ$. To je razuman broj: namotaj pri zakočenom rotoru ima $R_g$ i $X_g$ istog reda veličine, pa je ugao "negde između" $0^\circ$ (čist otpornik) i $90^\circ$ (čist kalem). Na slici 58.8 to je ugao $\varphi_{1g}$ kojim crveni fazor $\underline{I}_{1g}$ zaostaje za naponom.

### Korak 2: Potreban fazni stav struje pomoćne faze

**Zašto ovaj korak:** Sada uslov simetričnog polja prevodimo u konkretan broj — ugao koji struja pomoćne faze mora da ima prema naponu.

Dogovor o znaku (isti kao u Mini-lekciji 1): fazni stav $\varphi$ merimo kao ugao **kašnjenja struje za naponom** — pozitivan $\varphi$ znači da struja kasni, negativan da prednjači. Uslov zadatka, "fazni pomeraj između struja glavne i pomoćne faze pri startu iznosi $90^\circ$", tada glasi:

$$\varphi_{gp} = \varphi_g - \varphi_p = 90^\circ.$$

Zašto baš $\varphi_g - \varphi_p$, a ne obrnuto? Zato što struja pomoćne faze mora da **prednjači** struji glavne faze: pomoćni namotaj je prostorno postavljen "ispred" glavnog u smeru željenog obrtanja, pa njegova struja mora i vremenski da stigne "ranije" — tada polje rotira od pomoćne ka glavnoj osi i motor kreće u željenom smeru (to je i geometrija slike 58.8: $\underline{I}_{1p}$ je levo od napona, $\underline{I}_{1g}$ desno, a ukupni ugao između njih je $90^\circ$). Rešimo po $\varphi_p$: prebacimo $\varphi_g$ na desnu stranu sa promenom znaka... tačnije, iz $\varphi_g - \varphi_p = 90^\circ$ sledi $\varphi_p = \varphi_g - 90^\circ$:

$$\varphi_p = \varphi_g - 90^\circ = 39{,}3925^\circ - 90^\circ = -50{,}6074^\circ.$$

**Šta smo dobili:** Negativan ugao — struja pomoćne faze mora da **prednjači naponu** za $50{,}6^\circ$. To je ključni fizički zaključak: nikakav otpornik ni prigušnica ne mogu naterati struju da prednjači naponu (kod njih struja uvek kasni ili je u fazi); za ovo je **neophodan kondenzator**, i to dovoljno velik da "preokrene" karakter cele pomoćne grane iz induktivnog u kapacitivni.

### Korak 3: Impedansa pomoćne grane sa kondenzatorom i uslov na njen ugao

**Zašto ovaj korak:** Fazni stav struje pomoćne grane diktira ukupna impedansa te grane. Zato prvo zapišemo tu impedansu sa kondenzatorom, pa iz zahtevanog ugla izvučemo jednačinu za nepoznatu reaktansu kondenzatora.

Pomoćna grana je redna veza namotaja pomoćne faze ($R_p + jX_p$) i kondenzatora (reaktansa $X_C = -1/(\omega C) < 0$; podsetnik iz Mini-lekcije 1 — kapacitivnu reaktansu unosimo kao negativan broj). Kod redne veze impedanse se sabiraju, pa je ukupna impedansa pomoćnog kola:

$$\underline{Z}_u = R_p + j\big(X_p + X_C\big).$$

Ovde je $\underline{Z}_u$ ukupna impedansa pomoćne grane, $R_p$ i $X_p$ su otpornost i reaktansa pomoćnog namotaja, a $X_C$ (nepoznata, negativna) reaktansa dodatog kondenzatora. Struja ove grane, $\underline{I}_p = \underline{U}/\underline{Z}_u$, treba prema naponu da ima fazni stav izračunat u Koraku 2, tj. da **prednjači** za $50{,}6074^\circ$. Fazni stav struje jednak je (sa našim dogovorom o znaku) argumentu impedanse:

$$\varphi_p = \arctan\!\left(\frac{X_p + X_C}{R_p}\right) = -50{,}6074^\circ.$$

**Šta smo dobili:** Jednu jednačinu sa jednom nepoznatom $X_C$. Odmah vidimo i šta mora da ispadne: da bi arkus tangens bio negativan, mora biti $X_p + X_C < 0$, tj. $|X_C| > X_p = 11{,}7\ \mathrm{\Omega}$ — kondenzator mora ne samo da poništi induktivnost pomoćnog namotaja, nego i da je **prekompenzuje**.

### Korak 4: Potrebna reaktansa kondenzatora

**Zašto ovaj korak:** Rešavamo jednačinu iz Koraka 3 po $X_C$.

Primenimo tangens na obe strane jednačine (tangens i arkus tangens se poništavaju):

$$\frac{X_p + X_C}{R_p} = \tan(\varphi_p) = \tan(-50{,}6074^\circ) = -1{,}21774.$$

Broj $-1{,}21774$ je bezdimenzionalan (količnik dve reaktanse/otpornosti). Sada raspletimo jednačinu po $X_C$, korak po korak. Pomnožimo obe strane sa $R_p$:

$$X_p + X_C = R_p \cdot \tan(\varphi_p),$$

pa prebacimo $X_p$ na desnu stranu (oduzmemo $X_p$ od obe strane):

$$X_C = R_p \cdot \tan(\varphi_p) - X_p.$$

Uvrstimo brojeve, sa međukoracima:

$$X_C = 31{,}9 \cdot (-1{,}21774) - 11{,}7 = -38{,}8459 - 11{,}7 = -50{,}5459\ \mathrm{\Omega}.$$

**Šta smo dobili:** Reaktansa kondenzatora je negativna, kako i mora biti (kapacitivna), i po modulu ($50{,}5\ \mathrm{\Omega}$) znatno veća od reaktanse samog pomoćnog namotaja ($11{,}7\ \mathrm{\Omega}$) — kondenzator zaista prekompenzuje granu, tačno kako smo predvideli u Koraku 3. Ukupna reaktansa grane je $X_p + X_C = 11{,}7 - 50{,}5459 = -38{,}8459\ \mathrm{\Omega}$: grana je sada izrazito kapacitivna.

### Korak 5: Kapacitivnost kondenzatora

**Zašto ovaj korak:** Reaktansa je "otpor" kondenzatora na jednoj konkretnoj učestanosti; podatak koji se kupuje u prodavnici je kapacitivnost u mikrofaradima. Prevodimo $X_C$ u $C$ koristeći poznatu učestanost mreže.

Veza reaktanse i kapacitivnosti (Mini-lekcija 1, sa našom konvencijom znaka):

$$X_C = -\frac{1}{\omega C}, \qquad \omega = 2\pi f,$$

gde je $\omega$ kružna učestanost mreže u $\mathrm{rad/s}$, a $f = 50\ \mathrm{Hz}$. Rešimo po $C$: pomnožimo obe strane sa $C$ i podelimo sa $X_C$ (smemo, jer je $X_C \neq 0$):

$$C = -\frac{1}{\omega \, X_C} = -\frac{1}{2\pi f \, X_C}.$$

Minus ispred razlomka i negativno $X_C$ daju pozitivnu kapacitivnost, kako i mora biti. Uvrstimo brojeve, sa svim međukoracima:

$$C = -\frac{1}{2\pi \cdot 50 \cdot (-50{,}5459)} = \frac{1}{314{,}159 \cdot 50{,}5459} = \frac{1}{15879{,}5\ \mathrm{\Omega/s}}$$

$$C = 62{,}9743 \cdot 10^{-6}\ \mathrm{F} = 62{,}9743\ \mathrm{\mu F} \approx 63\ \mathrm{\mu F}.$$

**Šta smo dobili:** Kondenzator od oko $63\ \mathrm{\mu F}$ — sasvim uobičajena kataloška vrednost za motorske kondenzatore ovog reda snage (u praksi bi se uzela najbliža standardna vrednost). Ovim je zadatak rešen.

> **Napomena o originalu:** U štampanom rešenju u zbirci međukorak glasi $C = -\dfrac{1}{2\pi\, X_C}$ — u imeniocu je ispuštena učestanost $f = 50\ \mathrm{Hz}$ (štamparska greška: bez nje bi ispalo $C \approx 3149\ \mathrm{\mu F}$, što je besmisleno veliko). Konačan rezultat u zbirci, $62{,}9743\ \mathrm{\mu F}$, ipak je izračunat sa $f = 50\ \mathrm{Hz}$ i on je ispravan — greška je samo u zapisu međukoraka, ne u računu.

Za kraj, važna napomena iz originala o dometu ovakvog rešenja: izborom (jedne, fiksne) kapacitivnosti kondenzatora simetrično obrtno polje se može podesiti **samo u jednom režimu rada** — na primer u polaznom (kao ovde) ili u nazivnom. U svim ostalim režimima polje nije savršeno kružno: javlja se inverzna komponenta polja i pripadajući dodatni gubici i kočioni moment. Zato ozbiljniji kondenzatorski motori imaju i startni i pogonski kondenzator (startni, veći, isključi se po zaletu).

## Česte greške i zamke

1. **Pogrešan znak: $\varphi_p = \varphi_g + 90^\circ$ umesto $\varphi_g - 90^\circ$.** Ko sabere umesto da oduzme, dobije $\varphi_p = 129{,}39^\circ$ — a fazni stav pasivnog rednog $RLC$ kola ne može biti veći od $90^\circ$ (jednačina tada nema rešenje, ili se, uz slepo guranje brojeva, dobije besmislen kondenzator). Fizika je jednoznačna: struja pomoćne faze mora da **prednjači**, dakle njen ugao kašnjenja mora biti **manji** (negativan), pa se $90^\circ$ oduzima.
2. **Ispuštanje znaka kapacitivne reaktanse.** Ako se piše $\underline{Z}_u = R_p + j(X_p - X_C)$ sa "pozitivnim" $X_C$, ili $X_C = -1/(\omega C)$ pomeša sa $X_C = +1/(\omega C)$, lako se izgubi minus i dobije pogrešna vrednost (npr. $X_C = 27{,}1\ \mathrm{\Omega}$ umesto $-50{,}5\ \mathrm{\Omega}$). Najsigurnije je dosledno držati konvenciju iz ovog poglavlja: kapacitivna reaktansa je **negativan broj** koji se **sabira** sa induktivnom, a na kraju formula $C = -1/(\omega X_C)$ sama vrati pozitivnu kapacitivnost.
3. **Zaboravljena učestanost u prelasku sa $X_C$ na $C$** (baš kao u štamparskoj grešci originala): $C = 1/(2\pi |X_C|)$ umesto $C = 1/(2\pi f |X_C|)$ daje rezultat $50$ puta veći ($\approx 3149\ \mathrm{\mu F}$). Brza kontrola: motorski kondenzatori za male motore su reda desetina, najviše stotina mikrofarada.
4. **Kalkulator u radijanima.** $\arctan(0{,}82119)$ u radijanima iznosi $0{,}6875$ — ko to pročita kao stepene, sav dalji račun propada. Uvek proveri režim (DEG/RAD).
5. **Uverenje da $90^\circ$ između struja samo po sebi daje savršeno kružno polje.** Ne — potrebna je i jednakost magnetopobudnih sila oba namotaja (Mini-lekcija 6). Ovde su moduli struja različiti ($I_g \approx 11{,}3\ \mathrm{A}$, $I_p \approx 4{,}4\ \mathrm{A}$ — vidi Proveru smisla), pa jednakost mps mora da obezbedi različit broj navojaka; zato postavka govori o **približno** simetričnom polju.
6. **Korišćenje ovih impedansi van starta.** $\underline{Z}_g$ i $\underline{Z}_p$ su date **pri zakočenom rotoru** i važe samo za $s=1$. U radu (malo $s$) impedanse motora su bitno drugačije, pa isti kondenzator više ne daje simetriju — to je upravo poenta razlike između startnog i pogonskog kondenzatora.

## Rezime rezultata

| Tražena veličina | Oznaka | Vrednost |
|---|---|---|
| Fazni stav struje glavne faze pri startu (kašnjenje za naponom) | $\varphi_g$ | $39{,}3925^\circ$ |
| Potreban fazni stav struje pomoćne faze (negativno = prednjačenje) | $\varphi_p$ | $-50{,}6074^\circ$ |
| Potrebna reaktansa kondenzatora | $X_C$ | $-50{,}5459\ \mathrm{\Omega}$ |
| **Kapacitivnost startnog kondenzatora** | $C$ | $62{,}9743\ \mathrm{\mu F} \approx 63\ \mathrm{\mu F}$ |

## Provera smisla

**1. Dimenziona provera formule za $C$:** $\dfrac{1}{\omega X_C}$ ima jedinicu $\dfrac{1}{(\mathrm{rad/s}) \cdot \mathrm{\Omega}} = \dfrac{\mathrm{s}}{\mathrm{\Omega}} = \dfrac{\mathrm{s\cdot A}}{\mathrm{V}} = \dfrac{\mathrm{C}}{\mathrm{V}} = \mathrm{F}$ — farad, kako i treba (iskoristili smo $\Omega = \mathrm{V/A}$ i $\mathrm{A \cdot s} = \mathrm{C}$, kulon).

**2. Direktna kontrola ugla između struja.** Izračunajmo obe struje pri startu sa dobijenim kondenzatorom. Glavna faza: $|\underline{Z}_g| = \sqrt{15{,}1^2 + 12{,}4^2} = 19{,}54\ \mathrm{\Omega}$, pa je $I_g = 220/19{,}54 = 11{,}26\ \mathrm{A}$, sa faznim stavom $-39{,}39^\circ$ (kasni). Pomoćna grana: $\underline{Z}_u = 31{,}9 + j(11{,}7 - 50{,}5459) = 31{,}9 - j\,38{,}8459\ \mathrm{\Omega}$, $|\underline{Z}_u| = \sqrt{31{,}9^2 + 38{,}8459^2} = 50{,}27\ \mathrm{\Omega}$, pa je $I_p = 220/50{,}27 = 4{,}38\ \mathrm{A}$, sa faznim stavom $+50{,}61^\circ$ (prednjači). Ugao između struja: $50{,}61^\circ - (-39{,}39^\circ) = 90{,}00^\circ$ — **tačno traženih $90^\circ$**, dakle račun je zatvoren i iznutra konzistentan.

**3. Poređenje sa praktičnim pravilom iz Mini-lekcije 7:** pravilo "$25\!-\!55\ \mathrm{\mu F}$ po kilovatu za trajan rad" za motor od $2{,}5\ \mathrm{kW}$ daje opseg $62{,}5\!-\!137{,}5\ \mathrm{\mu F}$. Naš rezultat $63\ \mathrm{\mu F}$ upada tačno u taj opseg (uz njegovu donju ivicu) — red veličine je nesumnjivo pogođen.

**4. Napon na kondenzatoru (veza sa Mini-lekcijom 8):** $U_C = I_p \cdot |X_C| = 4{,}38 \cdot 50{,}55 \approx 221\ \mathrm{V}$ — već pri startu je napon na kondenzatoru praktično jednak punom mrežnom naponu (a fazorski se sa naponom namotaja slaže tako da grana ukupno "vidi" 220 V). Ovo lepo potvrđuje pouku sa slike 58.11: kondenzator se nikako ne bira na nazivni napon mreže, nego na $450\!-\!550\ \mathrm{V}$.
