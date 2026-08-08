# Teorijske osnove sinhronih mašina — sve što ti treba da pratiš zadatke 1–27

Ovo poglavlje je napisano za čitaoca koji o sinhronim mašinama ne zna ništa, a želi da samostalno
isprati svih 27 rešenih zadataka iz sinhronih mašina. Svaki pojam koji se u zadacima koristi ovde je
definisan, svaka formula koja se u zadacima "pojavi niotkuda" ovde je izvedena, a na kraju poglavlja
nalazi se **Rečnik oznaka** — tabela svih simbola koji se u zadacima 1–27 sreću. Čitaj redom: sekcije
se nadovezuju jedna na drugu i ništa se ne koristi pre nego što je objašnjeno.

> **Kako da koristiš ovo poglavlje:** prvo ga pročitaj celo, bez žurbe. Zatim, dok rešavaš zadatke,
> vraćaj se na konkretne sekcije — na početku svakog zadatka u zbirci prepoznaćeš koja "alatka"
> odavde ti treba: fazorski dijagram (§4), MPS dijagram (§5), ugaone karakteristike (§8, §10),
> pogonska karta (§11), relativne jedinice (§12), motor i V-krive (§13) ili PMSM (§14).

---

## 1. Šta je sinhrona mašina i kako je građena

### 1.1 Osnovni delovi

**Sinhrona mašina** je električna mašina naizmenične struje kod koje se rotor u ustaljenom radu
obrće **tačno** istom brzinom kojom rotira magnetno polje statora — otuda ime "sinhrona"
(grčki: *syn-chronos* = u istom vremenu, uskladjeno). Ista mašina može da radi kao **generator**
(mehaničku snagu pretvara u električnu — tako se proizvodi preko 95 % električne energije u
elektroenergetskim sistemima) ili kao **motor** (obrnuto).

Dva su ključna dela:

- **Stator (indukt)** — nepomični deo. U žlebovima statora smešten je **trofazni namotaj**
  (tri fazna namotaja prostorno pomerena za po 120°), identičan statoru asinhrone mašine. U
  ovom namotaju se **indukuje** elektromotorna sila (zato "indukt") i kroz njega teče struja
  opterećenja. Krajevi namotaja se vezuju u zvezdu (oznaka Y) ili trougao (D); u zadacima 1–27
  gotovo uvek je sprega **zvezda**, pa je fazni napon $U_f = U/\sqrt{3}$, gde je $U$ linijski
  (međufazni) napon.
- **Rotor (induktor, pobudni deo)** — obrtni deo. Na rotoru je **pobudni namotaj** kroz koji teče
  **jednosmerna** struja, tzv. **struja pobude** $I_p$. Ona pravi stalno magnetno polje rotora —
  rotor je, praktično, elektromagnet koji se obrće (zato "induktor" — on izaziva indukciju u
  statoru). Kod mašina sa stalnim magnetima (§14) ulogu pobudnog namotaja preuzimaju
  permanentni magneti.

**Intuicija:** zamisli rotor kao veliki magnet u obliku kazaljke. Kada se ta kazaljka obrće,
njeno magnetno polje "prelazi" preko statorskih provodnika i u njima indukuje naizmenični napon —
kao dinamo na biciklu, samo trofazno i mnogo veće.

### 1.2 Dve konstrukcije: turbogenerator i hidrogenerator

Brzina obrtanja i vrsta pogonske mašine (turbine) diktiraju oblik rotora, pa postoje dve
karakteristične izvedbe:

| Osobina | **Turbogenerator** | **Hidrogenerator** |
|---|---|---|
| Rotor | **cilindričan** (gladak, valjkast) | sa **istaknutim (isturenim) polovima** |
| Pogonska mašina | parna ili gasna turbina | vodna turbina |
| Brzina | velika (3000 ili 1500 min⁻¹ pri 50 Hz) | mala (od ~750 do ispod 100 min⁻¹) |
| Broj pari polova $p$ | mali (1 ili 2) | veliki (i po nekoliko desetina) |
| Oblik mašine | dugačka i uskog prečnika (leži) | kratka i velikog prečnika (često stoji) |
| Vazdušni zazor | **ravnomeran** po obimu | **neravnomeran** (mali pod polom, veliki između polova) |
| Model | jedna sinhrona reaktansa $X_s$ (§4) | dve reaktanse $X_d$ i $X_q$ (§10) |

Zašto je ovo bitno za zadatke: kod cilindričnog rotora magnetni otpor za fluks je **isti u svim
pravcima**, pa je mašina opisana jednom sinhronom reaktansom $X_s$ (zadaci 1–6, 10–18, 22–26).
Kod istaknutih polova magnetni otpor zavisi od pravca — pod polom je gvožđe blizu, između polova
je "rupa" od vazduha — pa se moraju koristiti **dve** reaktanse, $X_d$ i $X_q$ (zadaci 7–9,
19–21), a u ugaonoj karakteristici se pojavljuje dodatna, **reluktantna** komponenta momenta
(§10). PMSM iz Zadatka 27 je specijalan slučaj mašine sa dve različite reaktanse.

### 1.3 Pobudni sistem

**Pobudni sistem** je sklop koji obezbeđuje i reguliše jednosmernu struju pobude $I_p$ u rotorskom
namotaju. Tri su tipične izvedbe:

1. **Klasična (sa četkicama):** jednosmerni izvor (nekada mala jednosmerna mašina — "budilica",
   danas regulisani ispravljač) dovodi struju u rotor preko **kliznih prstenova i četkica**.
2. **Beskontaktna (bezčetkasta):** na istom vratilu je pomoćni naizmenični generator čiji je
   indukt na rotoru; njegov napon se ispravlja **rotirajućim diodama** i direktno napaja pobudni
   namotaj — nema četkica, nema varničenja, manje održavanja.
3. **Statička pobuda:** tiristorski ispravljač napajan sa krajeva samog generatora; brz i pogodan
   za regulaciju, ali zahteva prstenove i četkice.

Za zadatke je ključno samo ovo: **struja pobude $I_p$ je "dugme" kojim podešavamo jačinu magneta
rotora**, a time i elektromotornu silu $E_0$ (§3). U zadacima se često kaže "pobuda se poveća /
smanji / drži konstantnom" — to uvek znači manipulaciju strujom $I_p$.

> **Pažnja na oznake u ovoj zbirci:** oznaka $I_f$ u zadacima gotovo uvek znači **faznu struju
> statora** (indeks "f" = fazna!), a struja **pobude** se označava sa $I_p$ (ili $I_P$). Izuzetak
> je Zadatak 7, gde je u tabeli karakteristike praznog hoda pobudna struja obeležena sa $I_f$ —
> uvek proveri kontekst. U ovom poglavlju pobudnu struju doslovno svuda pišemo $I_p$.

---

## 2. Princip rada i sinhrona brzina

### 2.1 Obrtno magnetno polje statora

Kada kroz tri fazna namotaja statora (prostorno pomerena za 120°) poteku tri naizmenične struje
(vremenski pomerene za 120°), njihova zajednička magnetopobudna sila daje **obrtno magnetno
polje** konstantne amplitude — Teslino obrtno polje. Polje napravi jedan pun **električni** obrtaj
za jednu periodu struje. Ako mašina ima $p$ pari polova, jedan električni obrtaj odgovara
$1/p$ **mehaničkog** obrtaja (kod četvoropolne mašine, $p=2$, polje "slika" sever–jug–sever–jug po
obimu, pa se mehanički pomeri samo pola kruga za jednu periodu).

### 2.2 Sinhrona brzina — formula i intuicija

Iz gornjeg zaključka direktno sledi **sinhrona brzina** — brzina obrtnog polja, a u ustaljenom
stanju i brzina rotora:

$$n_s = \frac{60 \cdot f}{p}\ \left[\mathrm{min^{-1}}\right]$$

gde je:
- $n_s$ — sinhrona brzina u obrtajima u minuti ($\mathrm{min^{-1}}$, isto što i o/min),
- $f$ — učestanost (frekvencija) napona mreže u $\mathrm{Hz}$ (kod nas 50 Hz),
- $p$ — broj **pari** polova (dvopolna mašina ima $p=1$, četvoropolna $p=2$ itd.),
- broj 60 pretvara sekunde u minute ($f$ obrtaja u sekundi $\Rightarrow 60f$ u minuti, pa podeljeno sa $p$).

Iste veličine u uglovnom obliku, koje ćemo stalno sretati:

$$\omega_s = 2\pi f \ \left[\mathrm{rad/s}\right] \qquad \Omega_{sm} = \frac{\omega_s}{p} = \frac{2\pi f}{p} = \frac{2\pi n_s}{60}\ \left[\mathrm{rad/s}\right]$$

- $\omega_s$ — **električna** ugaona učestanost (koliko radijana faznog ugla struja "pređe" u sekundi),
- $\Omega_{sm}$ (u zadacima pisano i $\omega_{sm}$) — **mehanička** sinhrona ugaona brzina vratila; njome
  se deli snaga da bi se dobio moment (§8).

Provera na brojevima (za $f = 50\ \mathrm{Hz}$):

$$p=1:\ n_s = \frac{60\cdot 50}{1}=3000\ \mathrm{min^{-1}};\qquad p=2:\ n_s=1500\ \mathrm{min^{-1}};\qquad p=3:\ n_s=1000\ \mathrm{min^{-1}};\qquad p=24:\ n_s=125\ \mathrm{min^{-1}}.$$

Zato turbogeneratori (parna turbina voli velike brzine) imaju $p=1$ ili $p=2$, a hidrogeneratori
(spora vodna turbina) imaju mnogo polova.

**Zašto rotor mora ići baš sinhrono?** Rotor je magnet. Obrtno polje statora je drugi,
"nevidljivi" magnet koji kruži sinhronom brzinom. Dva magneta stvaraju koristan, vremenski
konstantan moment samo ako **miruju jedan prema drugom** — dakle rotor mora da se obrće istom
brzinom kao polje. Ako bi rotor išao sporije ili brže, privlačenje i odbijanje bi se naizmenično
smenjivali i srednji moment bio bi nula. Ovo je i razlog zašto sinhroni motor **ne može sam da
krene** iz mirovanja (detaljno u §13.2).

### 2.3 Generator i motor — ista mašina, dva smera snage

- **Generator:** pogonska mašina (turbina) gura rotor napred; rotor "vuče" polje za sobom,
  mehanička snaga ulazi kroz vratilo, električna izlazi kroz stator u mrežu.
- **Motor:** mreža kroz stator "vuče" rotor; električna snaga ulazi, mehanička izlazi na vratilo.

Formalna razlika u jednačinama je samo u smeru struje (znaku), što ćemo videti kod naponskih
jednačina (§4.4). Brzina je u oba slučaja ista — sinhrona.

### 2.4 Bilans snage i gubici (potrebno za Zadatak 17)

Realna mašina ima gubitke. Kod **generatora** se mehanička snaga koju daje pogonska mašina
$P_{pog}$ troši na korisnu električnu snagu $P$ i na gubitke:

$$P_{pog} = P + P_{Cu\,s} + P_{Fe} + P_{tr,v} + P_{pob}$$

gde je:
- $P = 3\,U_f I_f \cos\varphi$ — aktivna (korisna) električna snaga na krajevima
  ($U_f$, $I_f$ — fazni napon i struja, $\cos\varphi$ — faktor snage, videti §4),
- $P_{Cu\,s} = 3\,R_s I_f^2$ — **gubici u bakru statora** (Džulovo grejanje sva tri fazna
  namotaja otpornosti $R_s$),
- $P_{Fe}$ — **gubici u gvožđu** (histerezis i vihorne struje u magnetnom kolu statora),
- $P_{tr,v}$ — **mehanički gubici** (trenje u ležajevima i ventilacija),
- $P_{pob}$ — gubici u pobudnom kolu (obično svega ~1 % nazivne snage, pa se u zadacima
  najčešće zanemaruju).

Moment koji pogonska mašina mora da razvije je $M_{pog} = P_{pog}/\Omega_{sm}$, a stepen
iskorišćenja $\eta = P / P_{pog}$. Kod motora je smer obrnut: iz mreže ulazi $P_{el}$, na vratilo
izlazi $P_m = P_{el} - (\text{gubici})$.

---

## 3. EMS praznog hoda $E_0$ i karakteristika praznog hoda

### 3.1 Odakle potiče $E_0$

Neka se rotor obrće sinhronom brzinom, pobuđen strujom $I_p$, a stator neka je **otvoren** (nema
struje statora — otuda "prazan hod"). Fluks pobude $\Phi_0$ rotira zajedno sa rotorom i kroz svaki
fazni namotaj statora prolazi naizmenično — po Faradejevom zakonu elektromagnetne indukcije u
namotaju se indukuje naizmenična elektromotorna sila (EMS). Njena efektivna vrednost po fazi je:

$$E_{0f} = 4{,}44 \cdot f \cdot N \cdot k_{n} \cdot \Phi_0$$

gde je:
- $E_{0f}$ — **fazna EMS praznog hoda** (indeks 0 = prazan hod, f = fazna vrednost); u
  zadacima se sreće i kao $E_0$, $E_{0sf}$, a linijska vrednost je $E_{0l}=\sqrt{3}\,E_{0f}$,
- $f$ — učestanost ($f = p\,n/60$, direktno srazmerna brzini obrtanja $n$),
- $N$ — broj zavojaka po fazi, $k_n$ — navojni sačinilac (broj nešto manji od 1 koji uvažava
  raspodeljenost namotaja po žlebovima),
- $\Phi_0$ — fluks po polu koji pravi pobudna struja,
- $4{,}44 = \sqrt{2}\,\pi$ — konstanta koja potiče iz prelaska sa maksimalne na efektivnu
  vrednost sinusne EMS ($\pi/\sqrt2 \cdot 2 \approx 4{,}44$; ne moraš je pamtiti, dolazi iz
  Faradejevog zakona $e=-\mathrm{d}\Psi/\mathrm{d}t$ primenjenog na sinusni fluks).

Za zadatke su ključne dve **proporcionalnosti** koje odavde slede:

1. $E_0 \propto \Phi_0$ — a fluks zavisi od struje pobude $I_p$. Dok magnetno kolo nije
   zasićeno, važi približno $E_0 \propto I_p$. Na ovome počivaju zadaci 2, 13, 14 i 18
   ("pobuda se udvostruči" $\Rightarrow$ $E_0$ se udvostruči; "fluks se smanji 5 %"
   $\Rightarrow$ $E_0$ padne 5 %).
2. $E_0 \propto f \propto n$ — EMS je srazmerna brzini obrtanja. Na ovome počiva Zadatak 24
   (generator uspori sa 1500 na 1300 min⁻¹ $\Rightarrow$ i učestanost i EMS padnu u istom
   odnosu; nova učestanost je $f = p\,n/60 = 2\cdot 1300/60 = 43{,}33\ \mathrm{Hz}$).

### 3.2 Karakteristika praznog hoda i zasićenje

**Karakteristika praznog hoda** (karakteristika magnećenja) je zavisnost $E_0(I_p)$ snimljena pri
konstantnoj (sinhronoj) brzini. Njen oblik:

- **linearni deo** za male $I_p$: fluksu se na putu suprotstavlja praktično samo vazdušni zazor
  (gvožđe je "magnetno provodno"), pa $E_0$ raste srazmerno $I_p$ — produžetak ovog dela zove se
  **vazdušna linija**;
- **koleno**: gvožđe počinje da se zasićuje;
- **zasićeni deo**: dalji porast $I_p$ donosi sve manji porast fluksa i $E_0$ — magnetno kolo
  "ne može više da primi" fluks.

U zadacima se karakteristika zadaje **tabelom**. Primer iz Zadatka 3:

| $I_p\ [\mathrm{A}]$ | 20 | 50 | 80 | 100 | 120 | 140 | 160 | 180 | 200 |
|---|---|---|---|---|---|---|---|---|---|
| $E_{0f}\ [\mathrm{kV}]$ | 1,73 | 8,53 | 16,90 | 18,48 | 20,13 | 21,46 | 22,53 | 23,33 | 24 |

Pogledaj zasićenje na brojevima: sa 80 A na 160 A pobuda se **udvostruči** (+100 %), a EMS
poraste sa 16,90 kV na samo 22,53 kV (+33 %); da je kolo linearno, dobili bismo 33,8 kV. Zato se
proporcija $E_0\propto I_p$ sme koristiti samo u linearnom delu ili kada zadatak izričito kaže
"magnetno kolo je linearno".

### 3.3 Linearna interpolacija po tabeli

Kada izračunamo neku vrednost $E_{0f}$ koja "upadne" između dve tabelarne tačke
$(I_{p1}, E_1)$ i $(I_{p2}, E_2)$, potrebnu struju pobude nalazimo **linearnom interpolacijom** —
između dve susedne tačke krivu zamenimo pravom linijom (secantom):

$$\frac{E_{0f}-E_1}{I_p - I_{p1}} = \frac{E_2 - E_1}{I_{p2}-I_{p1}} \quad\Longrightarrow\quad I_p = I_{p1} + \frac{E_{0f}-E_1}{E_2-E_1}\,\bigl(I_{p2}-I_{p1}\bigr)$$

Logika: nagib prave kroz dve susedne tačke je poznat, pa iz zahtevane EMS "očitamo" struju.
Ovako se rešava kraj Zadatka 3 (traženo $E_{0f}=13{,}64\ \mathrm{kV}$ pada između 8,53 i
16,9 kV, pa $I_p = 68{,}32\ \mathrm{A}$) i kraj Zadatka 7 ($E_{0f}=3881\ \mathrm{V}$ između
3660 i 3920 V daje $I_p = 117\ \mathrm{A}$).

---

## 4. Model statorskog kola: sinhrona reaktansa i fazorski dijagram

### 4.1 Ekvivalentna šema i naponska jednačina

Čim generator opteretimo, kroz stator poteče struja $I_f$ i dve stvari se dese:

1. struja pravi padove napona na **otporu namotaja** $R_s$ i na **rasipnoj reaktansi**
   $X_{\gamma s}$ (deo fluksa statora koji se "rasipa" i ne stigne do rotora),
2. struja statora pravi i **sopstvenu magnetopobudnu silu** koja se meša sa poljem rotora —
   tzv. **reakcija indukta** (detaljno u §5). U linearnom magnetnom kolu njen uticaj na napon
   se može predstaviti kao pad na još jednoj reaktansi — **reaktansi reakcije indukta** $X_a$.

Oba efekta zajedno pakujemo u jednu veličinu — **sinhronu reaktansu**:

$$X_s = X_{\gamma s} + X_a$$

Time statorsko kolo (po jednoj fazi) postaje prosto redno kolo: izvor $E_{0f}$, otpornik $R_s$,
reaktansa $X_s$, i na kraju priključci sa naponom $U_f$. Za **generator** (struja izlazi iz
izvora ka mreži) po drugom Kirhofovom zakonu, u kompleksnom (fazorskom) zapisu:

$$\boxed{\;\mathbf{E}_{0f} = \mathbf{U}_f + R_s\,\mathbf{I}_f + \mathrm{j}\,X_s\,\mathbf{I}_f\;}$$

gde je (podebljano = kompleksni fazor, obično slovo = efektivna vrednost):
- $\mathbf{E}_{0f}$ — fazna EMS praznog hoda (posledica **samo** pobude; "unutrašnji napon" mašine),
- $\mathbf{U}_f$ — fazni napon na priključcima (kod sprege Y: $U_f=U/\sqrt3$),
- $\mathbf{I}_f$ — fazna struja statora,
- $R_s$ — otpor statorskog namotaja po fazi $[\Omega]$,
- $X_s$ — sinhrona reaktansa po fazi $[\Omega]$; $\mathrm{j}$ — imaginarna jedinica
  (množenje sa $\mathrm{j}$ = zaokret fazora za $+90^\circ$).

Kod većih mašina je $R_s \ll X_s$, pa se $R_s$ često zanemaruje:
$\mathbf{E}_{0f} = \mathbf{U}_f + \mathrm{j}X_s\mathbf{I}_f$.

**Intuicija:** sinhroni generator se prema mreži ponaša kao baterija sa unutrašnjom
"otpornošću" — samo što je ta unutrašnjost pretežno **induktivna** ($X_s$), a "napon baterije"
($E_{0f}$) podešavamo strujom pobude. Kad poteče struja, napon na priključcima se razlikuje od
$E_{0f}$ za pad na $R_s + \mathrm{j}X_s$.

### 4.2 Kako se crta fazorski dijagram (Potjeov dijagram napona)

**Fazorski (vektorski) dijagram** je grafički prikaz gornje jednačine: svaki sinusni napon/struju
predstavimo fazorom (strelicom) čija je dužina efektivna vrednost, a ugao fazni stav. Postupak
crtanja za generator (ovako izgledaju slike 1.1, 3.1, 4.1, 10.3, 11.1 u zbirci):

1. Nacrtaj $\mathbf{U}_f$ kao referentni fazor (recimo uspravno).
2. Nacrtaj $\mathbf{I}_f$ pod uglom $\varphi$ u odnosu na $\mathbf{U}_f$: kod **induktivnog**
   faktora snage struja **kasni** (rotirano od $\mathbf{U}_f$ unazad), kod kapacitivnog prednjači.
3. Na vrh $\mathbf{U}_f$ nadoveži $R_s\mathbf{I}_f$ (paralelno sa $\mathbf{I}_f$).
4. Na to nadoveži $\mathrm{j}X_s\mathbf{I}_f$ (normalno na $\mathbf{I}_f$, zaokrenuto $+90^\circ$).
5. Strelica od koordinatnog početka do kraja tog lanca je $\mathbf{E}_{0f}$.

Ugao između $\mathbf{E}_{0f}$ i $\mathbf{U}_f$ zove se **ugao opterećenja** $\delta$ (delta) —
najvažniji ugao sinhrone mašine, detaljno u §8. Ugao između $\mathbf{U}_f$ i $\mathbf{I}_f$ je
poznati **fazni stav** $\varphi$ ($\cos\varphi$ = faktor snage).

### 4.3 Dve "zlatne" projekcione jednačine + kosinusna teorema

Iz fazorskog dijagrama se sve računa jednim od dva zanata: **projektovanjem** ili **kosinusnom
teoremom**. Oba se stalno koriste u zadacima, pa ih ovde izvodimo jednom zauvek.

**Projekcione jednačine.** Projektuj vektorsku jednačinu
$\mathbf{E}_{0f}=\mathbf{U}_f+R_s\mathbf{I}_f+\mathrm{j}X_s\mathbf{I}_f$ na pravac fazora
$\mathbf{U}_f$ i na pravac normalan na njega. Fazor $\mathbf{I}_f$ ima komponentu
$I_f\cos\varphi$ u pravcu $\mathbf{U}_f$ i $-I_f\sin\varphi$ normalno (kasni za induktivno
opterećenje); fazor $\mathrm{j}X_s\mathbf{I}_f$ je isti taj, samo zaokrenut za $90^\circ$, pa su
mu komponente $X_sI_f\sin\varphi$ (u pravcu $\mathbf{U}_f$) i $X_sI_f\cos\varphi$ (normalno).
Leva strana $\mathbf{E}_{0f}$ ima komponente $E_{0f}\cos\delta$ i $E_{0f}\sin\delta$. Dakle:

$$\begin{aligned}
E_{0f}\cos\delta &= U_f + R_s I_f\cos\varphi + X_s I_f \sin\varphi \\
E_{0f}\sin\delta &= X_s I_f\cos\varphi - R_s I_f \sin\varphi
\end{aligned}$$

Uz zanemaren otpor ($R_s \approx 0$) ostaju dve jednačine koje ćeš koristiti bezbroj puta:

$$\boxed{\;E_{0f}\cos\delta = U_f + X_s I_f\sin\varphi\;}\qquad\boxed{\;E_{0f}\sin\delta = X_s I_f\cos\varphi\;}$$

Prva kaže: projekcija $E_{0f}$ na pravac napona premašuje $U_f$ za "reaktivni" pad
$X_sI_f\sin\varphi$. Druga kaže: "visina" trougla, $E_{0f}\sin\delta$, jednaka je "aktivnom"
padu $X_sI_f\cos\varphi$ — iz nje će u §8 ispasti ugaona karakteristika snage. Verzije **sa**
$R_s$ koristi Zadatak 4, verzije **bez** $R_s$ zadaci 3, 8, 9, 10 itd.

**Kosinusna teorema.** U trouglu koji obrazuju fazori $\mathbf{U}_f$, ukupni pad napona
$\mathbf{Z}_s\mathbf{I}_f$ (gde je $Z_s=\sqrt{R_s^2+X_s^2}$ modul impedanse statora) i
$\mathbf{E}_{0f}$, važi kosinusna teorema (uopštena Pitagorina teorema za trougao sa uglom
$\alpha$ između dve poznate stranice):

$$E_{0f} = \sqrt{U_f^2 + \bigl(Z_s I_f\bigr)^2 - 2\,U_f \,Z_s I_f\cdot \cos\alpha}$$

pri čemu je $\alpha$ **unutrašnji ugao trougla** između stranice $U_f$ i stranice $Z_sI_f$.
Odakle $\alpha$? Vektor pada $\mathbf{Z}_s\mathbf{I}_f$ prednjači struji za ugao
$\mathrm{arctg}(X_s/R_s)$ (jer je to ugao impedanse), a struja kasni za naponom za $\varphi$;
znači pravac pada zaklapa sa pravcem $\mathbf{U}_f$ ugao $\mathrm{arctg}(X_s/R_s)-\varphi$. Pošto
se u trouglu pad **nadovezuje** na vrh $\mathbf{U}_f$ (glava-na-rep), unutrašnji ugao je
suplement:

$$\alpha = 180^\circ - \mathrm{arctg}\frac{X_s}{R_s} + \varphi$$

**Mini-primer (brojevi iz Zadatka 1).** Generator: $S_n=1{,}5\ \mathrm{MVA}$,
$P_n=1{,}2\ \mathrm{MW}$, $U_n=2{,}3\ \mathrm{kV}$ (Y), $R_s=0{,}2\ \Omega$,
$X_s=1{,}95\ \Omega$, nazivno opterećenje. Redom:

$$I_n=\frac{S_n}{\sqrt3\,U_n}=\frac{1{,}5\cdot10^6}{\sqrt3\cdot 2300}=376{,}5\ \mathrm{A};\qquad \cos\varphi_n=\frac{P_n}{S_n}=\frac{1{,}2}{1{,}5}=0{,}8\ \Rightarrow\ \varphi_n=36{,}87^\circ$$

$$\alpha = 180^\circ - \mathrm{arctg}\frac{1{,}95}{0{,}2}+36{,}87^\circ = 180^\circ - 84{,}14^\circ + 36{,}87^\circ = 132{,}7^\circ$$

$$E_{0f}=\sqrt{\frac{2300^2}{3}+\bigl(0{,}2^2+1{,}95^2\bigr)\cdot 376{,}5^2 - 2\cdot\frac{2300}{\sqrt3}\cdot 376{,}5\cdot\sqrt{0{,}2^2+1{,}95^2}\cdot\cos 132{,}7^\circ}\approx 1907\ \mathrm{V}$$

(u zbirci $1907{,}2\ \mathrm{V}$ — sitna razlika potiče od zaokruživanja međurezultata).
Uoči: $E_{0f}=1907\ \mathrm{V} > U_f = 2300/\sqrt3 = 1328\ \mathrm{V}$ — mašina je
**nadpobuđena** (§6), što je i logično jer daje struju koja kasni.

### 4.4 Motorska naponska jednačina

Kod **motora** je prirodnije strelicu struje okrenuti ka mašini (struja ulazi). Ista fizika,
samo se pad napona premešta na drugu stranu jednačine (koristi se u zadacima 10, 12, 14, 19):

$$\mathbf{U}_f = \mathbf{E}_{0f} + R_s\mathbf{I}_f+\mathrm{j}\,X_s\,\mathbf{I}_f \qquad\Longleftrightarrow\qquad \mathbf{E}_{0f} = \mathbf{U}_f - R_s\mathbf{I}_f - \mathrm{j}\,X_s\,\mathbf{I}_f$$

Kod motora fazor $\mathbf{E}_{0f}$ **kasni** za $\mathbf{U}_f$ za ugao $\delta$ (rotor "vučen"
poljem zaostaje), dok kod generatora prednjači (rotor "vuče" polje).

---

## 5. Dijagram magnetopobudnih sila (MPS)

Ovaj aparat treba za zadatke 5 i 6, a daje i dublju sliku onoga što $X_s$ "sakriva".

### 5.1 Šta je magnetopobudna sila

**Magnetopobudna sila (MPS)** namotaja je proizvod broja zavojaka i struje:

$$F = N\cdot I \ \ [\mathrm{Az}]$$

Jedinica je **amper-zavojak** ($\mathrm{Az}$). MPS je "pokretačka snaga" magnetnog fluksa —
analogija sa električnim kolom: MPS $\leftrightarrow$ EMS, fluks $\leftrightarrow$ struja,
magnetni otpor kola $\leftrightarrow$ električni otpor ("Omov zakon za magnetno kolo":
$\Phi = F/R_m$). Veća MPS $\Rightarrow$ veći fluks (dok se gvožđe ne zasiti).

### 5.2 Tri MPS i njihovo sabiranje

U opterećenoj sinhronoj mašini postoje **dve** MPS koje se vrte istom (sinhronom) brzinom:

- $\overline{F}_r$ — MPS **rotora** (pobude): pravi je jednosmerna struja $I_p$; rotira zato što
  rotor fizički rotira;
- $\overline{F}_s$ — MPS **statora** (**reakcija indukta**): pravi je trofazna struja statora;
  rotira kao Teslino obrtno polje. Fazor $\overline{F}_s$ je **kolinearan sa fazorom struje**
  $\mathbf{I}_{sf}$ i srazmeran joj po amplitudi (crtaju se u istom dijagramu, pa se MPS i
  električni fazori smeju kombinovati — to je konvencija svih slika 5.1, 6.1–6.3 u zbirci).

Pošto obe rotiraju istom brzinom, **miruju jedna prema drugoj** i smemo ih sabrati kao vektore.
Zbir je **rezultantna MPS**, koja stvarno magneti mašinu:

$$\overline{F}_{rez} = \overline{F}_r + \overline{F}_s \qquad\Longleftrightarrow\qquad \boxed{\;\overline{F}_r = \overline{F}_{rez}-\overline{F}_s\;}$$

Desni oblik je "radni" oblik iz zadataka 5 i 6: kada odredimo $\overline{F}_{rez}$ i
$\overline{F}_s$, pobudu rotora dobijamo oduzimanjem.

### 5.3 Veza MPS ↔ naponi: rezultantna EMS $E_{sf}$

Rezultantni fluks (posledica $\overline{F}_{rez}$) indukuje u statoru **rezultantnu (unutrašnju)
EMS** $\mathbf{E}_{sf}$ (u zadacima i $\overline{E}_f$). Pravila koja povezuju dijagram MPS i
naponski dijagram:

1. **EMS kasni za "svojom" MPS tačno $90^\circ$** ($\mathrm{j}$-pravilo). To sledi iz Faradejevog
   zakona: EMS je izvod fluksa, a izvod sinusa je kosinus — pomak od $90^\circ$. Važi za svaki
   par: $\mathbf{E}_{sf}$ kasni za $\overline{F}_{rez}$, a $\mathbf{E}_{0f}$ kasni za
   $\overline{F}_r$ (obrnutim rečnikom: MPS **prednjači** EMS za $90^\circ$, pa se u zadacima 5–6
   piše $\overline{F}_{rez} = \mathrm{j}\,(\mathbf{E}_{sf}/E_{sf})\cdot F_{rez}$).
2. **Amplituda EMS je srazmerna amplitudi MPS** (za linearno magnetno kolo):
   $E \propto F$. Na ovome počiva korak u Zadatku 6: $F''_{rez} = (E''_{sf}/E'_{sf})\cdot F'_{rez}$.

Pošto $\mathbf{E}_{sf}$ već sadrži i uticaj reakcije indukta (kroz $\overline{F}_{rez}$), od nje
do napona na priključcima ostaju samo omski pad i pad na **rasipnoj** reaktansi:

$$\boxed{\;\mathbf{E}_{sf} = \mathbf{U}_{sf} + R_s\,\mathbf{I}_{sf} + \mathrm{j}\,X_{\gamma s}\,\mathbf{I}_{sf}\;}$$

Uporedi sa §4.1: tamo smo pošli od $\mathbf{E}_{0f}$ (samo rotor) i reakciju indukta "naplatili"
kroz $X_a$ unutar $X_s = X_{\gamma s}+X_a$; ovde polazimo od $\mathbf{E}_{sf}$ (rotor + stator
zajedno) pa ostaje samo $X_{\gamma s}$. **Dva ravnopravna pogleda na istu mašinu.**

Ugao za koji $\mathbf{E}_{sf}$ prednjači naponu $\mathbf{U}_{sf}$ obeležava se u zadacima 5 i 6
sa $\gamma$ (ne mešati sa uglom $\gamma$ kod PMSM u §14!).

### 5.4 Kratki spoj i konstanta $K_K$ (Zadatak 6)

U trajnom **kratkom spoju** je $U_{sf}=0$, pa je cela EMS "potrošena" na sopstvenu impedansu:
$\mathbf{E}_{sf} = \mathbf{I}_{sfk}(R_s + \mathrm{j}X_{\gamma s})$. Kako su $R_s$ i
$X_{\gamma s}$ mali, mala je i $E_{sf}$, dakle i $F_{rez}$ — stator svojom reakcijom skoro
potpuno **poništava** pobudu ($\overline{F}_s \approx -\overline{F}_r$). Struja kratkog spoja je
zato približno **srazmerna pobudi** (karakteristika kratkog spoja je prava linija!), pa se u
Zadatku 6 uvodi konstanta proporcionalnosti između struje kratkog spoja i MPS rotora:

$$K_K = \frac{I_K}{F_r}\ \left[\mathrm{A/Az}\right]$$

odredi se iz jednog poznatog režima, a onda primeni u drugom.

---

## 6. Nadpobuđen i podpobuđen režim — proizvodnja i potrošnja reaktivne snage

**Reaktivna snaga** $Q = 3\,U_f I_f\sin\varphi$ je snaga koja se periodično "ljulja" između
izvora i magnetnih/električnih polja potrošača — ne vrši koristan rad, ali je neophodna svim
motorima i transformatorima da bi se namagnetisali. Sinhrona mašina je jedinstvena po tome što
strujom pobude biramo da li ćemo reaktivnu snagu **davati** mreži ili je **uzimati** iz nje.

Kriterijum čitamo direktno iz prve projekcione jednačine (§4.3, $R_s\approx0$):

$$E_{0f}\cos\delta = U_f + X_s I_f\sin\varphi \quad\Longrightarrow\quad I_f\sin\varphi = \frac{E_{0f}\cos\delta-U_f}{X_s} \quad\Longrightarrow\quad Q = \frac{3\,U_f\bigl(E_{0f}\cos\delta - U_f\bigr)}{X_s}$$

Dakle znak reaktivne snage zavisi samo od toga da li je $E_{0f}\cos\delta$ veće ili manje od
$U_f$ (a kako je $\delta$ obično mali, grubo: da li je $E_{0f}$ veće ili manje od $U_f$):

| Režim | Uslov | Generator (predaje $P$) | Motor (uzima $P$) |
|---|---|---|---|
| **Nadpobuđen** (jaka pobuda) | $E_{0f}\cos\delta > U_f$ | **daje** $Q$ mreži; struja **kasni** za naponom (ind.) | **daje** $Q$ mreži; struja **prednjači** (kap.) |
| Normalno pobuđen | $E_{0f}\cos\delta = U_f$ | $Q=0$, $\cos\varphi=1$ | $Q=0$, $\cos\varphi=1$ |
| **Podpobuđen** (slaba pobuda) | $E_{0f}\cos\delta < U_f$ | **uzima** $Q$ iz mreže; struja prednjači (kap.) | **uzima** $Q$; struja kasni (ind.) |

**Intuicija:** pobuda je "pumpa za magnećenje". Nadpobuđena mašina proizvodi više magnetnog
"pritiska" nego što joj treba, pa višak (reaktivnu snagu) šalje u mrežu i magneti druge uređaje.
Podpobuđena nema dovoljno, pa se do-magnetiše iz mreže. Pazi na jezik: "generator radi sa
**induktivnim** faktorom snage" znači da mreži izgleda kao izvor koji napaja induktivne
potrošače — tj. da je **nadpobuđen** i **daje** $Q$ (tako u zadacima 1, 3, 5, 6, 13). Za motor je
obrnuto: induktivni $\cos\varphi$ znači podpobuđen motor koji $Q$ **uzima** (Zadatak 14).

---

## 7. Rad na krutoj mreži i ostrvski rad

### 7.1 Kruta mreža: ko određuje šta

**Kruta mreža** je idealizacija velikog elektroenergetskog sistema: njen napon $U$ i učestanost
$f$ su **konstantni** i naša mašina, ma šta radila, ne može da ih promeni (premala je prema
sistemu). Analogija: solo pevač (generator) uz ogroman hor (mreža) — ton (frekvenciju) i jačinu
(napon) diktira hor.

Posledice, koje su tihi "aksiomi" većine zadataka (2, 3, 9, 11, 12, 18, 20–23):

- brzina je **zakovana** na sinhronu ($n_s = 60f/p$) — mašina ne može da uspori/ubrza trajno;
- $U_f$ je zadat; jedine dve "ručice" kojima raspolažemo su:
  1. **snaga pogonske mašine** (dovod pare/vode) → menja **aktivnu snagu** $P$ i ugao $\delta$ (§8);
  2. **struja pobude** $I_p$ → menja $E_{0f}$, a time **reaktivnu snagu** $Q$ (§6).

Da bi se generator uopšte priključio ("sinhronizovao") na mrežu, u trenutku uklapanja moraju biti
jednaki: efektivna vrednost napona, učestanost, redosled faza i fazni stav — inače poteku veliki
izjednačujući udari struje.

### 7.2 Naglo rasterećenje (Zadatak 8)

Ako zaštita naglo odvoji opterećeni generator od mreže, struja statora padne na nulu, pa nestaju
padovi $R_sI_f$ i $X_sI_f$: napon na priključcima **skoči** sa $U_f$ na $E_{0f}$ (pobuda ne može
trenutno da se promeni). Kod nadpobuđene mašine ($E_{0f}>U_f$) to je opasan **porast napona** —
u Zadatku 8 čak na 1,8-struku vrednost nazivnog. Zato posle rasterećenja regulator brzo obara pobudu.

### 7.3 Ostrvski (samostalni) rad (zadaci 24–26)

Kada generator napaja **sopstvenu, pasivnu mrežu** (ostrvo — npr. brodska mreža, agregat),
nema krute mreže da diktira uslove, pa važi suprotno od §7.1:

- **učestanost** određuje brzina pogonske mašine: $f = p\,n/60$ — koliko se vrti, tolika je frekvencija;
- **napon** se uspostavlja sam iz jednačine $\mathbf{U}_f=\mathbf{E}_{0f}-\mathrm{j}X_s\mathbf{I}_f$
  u sprezi sa impedansom potrošača: promena opterećenja menja i napon i (preko momenta na vratilu)
  brzinu, dakle i frekvenciju;
- ravnotežna radna tačka se nalazi iz **bilansa**: snaga koju daje pogonska mašina = snaga koju
  troši potrošač (+ gubici), uz $E_0$ srazmerno brzini i pobudi (§3.1).

To je svet zadataka 24–26: generator uspori pa se promene i $f$ i $E_0$ i sve reaktanse
($X = \omega L$ — i one su srazmerne učestanosti!); ili se potrošač promeni pa "otpluta" cela
radna tačka. Nema tu ničeg novog — samo iste jednačine, ali bez fiksiranog $U$ i $f$.

---

## 8. Ugao opterećenja $\delta$ i ugaone karakteristike $P(\delta)$ i $M(\delta)$ — cilindrični rotor

### 8.1 Šta je ugao opterećenja

**Ugao opterećenja** $\delta$ je ugao između fazora $\mathbf{E}_{0f}$ i $\mathbf{U}_f$. Fizički:
$\mathbf{E}_{0f}$ "pokazuje" gde je magnetna osa **rotora**, a $\mathbf{U}_f$ je vezan za obrtno
polje **mreže** — dakle $\delta$ je (električni) ugao za koji rotor prednjači polju (generator)
ili zaostaje za njim (motor).

**Analogija koja sve objašnjava:** rotor i obrtno polje su dva magneta vezana **oprugom**. U
praznom hodu opruga je opuštena ($\delta=0$, $P=0$). Što više turbina gura rotor, opruga se
više zateže — $\delta$ raste i kroz "oprugu" se prenosi sve veća snaga. Ali opruga ima granicu:
pretegneš li je preko $90^\circ$, "pukne" — mašina **ispada iz sinhronizma** (§9).

### 8.2 Izvođenje ugaone karakteristike snage $P(\delta)$

Ovo izvođenje je u zbirci dato unutar Zadatka 10; ovde ga ponavljamo korak po korak.
Pretpostavke: cilindričan rotor (jedna reaktansa $X_s$), zanemareni svi gubici ($R_s\approx0$),
mašina na krutoj mreži.

**Korak 1.** Aktivna snaga trofazne mašine (definicija, važi uvek):

$$P = 3\,U_f\,I_f\cos\varphi$$

(tri faze, svaka daje $U_fI_f\cos\varphi$).

**Korak 2.** Nezgodno je što tu figurišu i $I_f$ i $\varphi$, koje ne kontrolišemo direktno.
Zato posežemo za drugom projekcionom jednačinom iz §4.3:

$$E_{0f}\sin\delta = X_s\,I_f\cos\varphi \quad\Longrightarrow\quad I_f\cos\varphi = \frac{E_{0f}\sin\delta}{X_s}$$

**Korak 3.** Uvrstimo u definiciju snage:

$$\boxed{\;P = \frac{3\,U_f\,E_{0f}}{X_s}\,\sin\delta\;}$$

To je **ugaona karakteristika aktivne snage**: pri zadatim $U_f$ (mreža), $E_{0f}$ (pobuda) i
$X_s$ (konstrukcija), snaga zavisi **samo od ugla $\delta$**, i to sinusno.

### 8.3 Moment $M(\delta)$, grafik i prevalni moment

Moment je količnik snage i **mehaničke** ugaone brzine. Kako su gubici zanemareni, a brzina
sinhrona:

$$M = \frac{P}{\Omega_{sm}} \quad\Longrightarrow\quad \boxed{\;M = \frac{3\,U_f\,E_{0f}}{\Omega_{sm}\,X_s}\,\sin\delta\;}$$

$M(\delta)$ i $P(\delta)$ su, dakle, iste sinusoide (razlikuju se samo za konstantu
$\Omega_{sm}$): nula u $\delta=0$, maksimum u $\delta=\pi/2$, ponovo nula u $\delta=\pi$
(tako izgleda slika 10.2 u zbirci). Maksimalne vrednosti su:

$$P_{max}=\frac{3\,U_f\,E_{0f}}{X_s},\qquad M_{max}=\frac{3\,U_f\,E_{0f}}{\Omega_{sm}X_s}\qquad(\text{pri }\delta=90^\circ)$$

$M_{max}$ se zove **prevalni moment** ($M_{pr}$): najveći moment koji mašina može da prenese
ne ispadajući iz sinhronizma (poreklo imena: tu se mašina "prevali" preko vrha karakteristike).
Uoči da je prevalni moment **srazmeran pobudi** ($E_{0f}$) i **obrnuto srazmeran** reaktansi $X_s$
— jača pobuda = "jača opruga".

**Mini-primer (Zadatak 10).** Motor 5 MVA, 11 kV (Y), 50 Hz, šestopolni ($p=3$),
$\cos\varphi_n=0{,}8$, $X_s=14{,}5\ \Omega$, pobuda nazivna. Nazivna struja
$I_{fn}=5\cdot10^6/(\sqrt3\cdot11000)=262{,}4\ \mathrm{A}$; iz kosinusne teoreme (§4.3, ugao
između $U_{fn}$ i $X_sI_{fn}$ je $90^\circ+\varphi_n$):

$$E_{0fn}=\sqrt{U_{fn}^2+(X_sI_{fn})^2+2\,U_{fn}X_sI_{fn}\sin\varphi_n}=\sqrt{\Bigl(\tfrac{11000}{\sqrt3}\Bigr)^2+(14{,}5\cdot262{,}4)^2+2\cdot\tfrac{11000}{\sqrt3}\cdot14{,}5\cdot262{,}4\cdot0{,}6}\approx9155\ \mathrm{V}$$

pa je, uz $\Omega_{sm}=2\pi\cdot50/3=104{,}7\ \mathrm{rad/s}$:

$$M_{max}=\frac{3\cdot\frac{11000}{\sqrt3}\cdot 9155}{104{,}7\cdot14{,}5}\approx114{,}9\ \mathrm{kNm}$$

U tom režimu ($\delta=90^\circ$) fazori $U_{fn}$ i $E_{0fn}$ su pod pravim uglom pa je (Pitagora)
struja $I=\sqrt{E_{0fn}^2+U_{fn}^2}/X_s = 768{,}4\ \mathrm{A}$ — skoro **3 puta veća od
nazivne**: mašina sme tu samo kratkotrajno.

### 8.4 Ugaona karakteristika reaktivne snage $Q(\delta)$

Za potpunost (koristi se u zadacima 12, 20, 21 i kod pogonske karte §11), iz prve projekcione
jednačine (§6) već imamo:

$$Q = \frac{3\,U_f\,E_{0f}\cos\delta}{X_s} - \frac{3\,U_f^2}{X_s}$$

Pri maloj snazi ($\delta\to0$): $Q \to 3U_f(E_{0f}-U_f)/X_s$ — čist "§6 kriterijum" nadpobuđenosti.

---

## 9. Sinhronizirajući moment i statička stabilnost

### 9.1 Statička stabilnost

Neka mašina radi u tački $\delta_0$ i neka se moment turbine malo poveća. Ako je mašina na
**rastućem** delu karakteristike ($\delta_0<90^\circ$), porast $\delta$ donosi porast
elektromagnetnog momenta koji se odupre poremećaju — mašina nađe novu ravnotežu: **stabilan** rad.
Na opadajućem delu ($\delta_0>90^\circ$) porast $\delta$ **smanji** moment mašine, rotor dalje
ubrzava, $\delta$ dalje raste — lavina: mašina **ispada iz sinhronizma**. Uslov **statičke
stabilnosti** je dakle:

$$\frac{\mathrm{d}P}{\mathrm{d}\delta} > 0 \qquad\text{(za cilindrični rotor: } \delta<90^\circ\text{)}$$

Teorijska granica je $\delta=90^\circ$; u praksi se drži rezerva (radi se sa
$\delta\approx20^\circ$–$30^\circ$ nazivno), a "praktična granica stabilnosti" na pogonskoj
karti definiše se sa određenom sigurnosnom marginom (§11).

### 9.2 Sinhronizirajući moment (zadaci 15 i 16)

**Sinhronizirajući moment** $M_{sin}$ je mera "krutosti opruge" iz analogije u §8.1 — kaže
koliki dodatni moment mašina razvije po jedinici dodatnog ugla:

$$M_{sin} = \frac{\mathrm{d}M}{\mathrm{d}\delta} = \frac{\mathrm{d}}{\mathrm{d}\delta}\left[\frac{3\,U_fE_{0f}}{\Omega_{sm}X_s}\sin\delta\right] = \boxed{\;\frac{3\,U_f\,E_{0f}}{\Omega_{sm}\,X_s}\,\cos\delta\;}\ \left[\mathrm{Nm/rad}\right]$$

(izvod sinusa je kosinus — zato $\cos\delta$). Za mali poremećaj: $\Delta M \approx M_{sin}\cdot\Delta\delta$.
Što je $M_{sin}$ veći, mašina se čvršće drži sinhronizma i posle poremećaja se brže vraća
(uz oscilacije — "njihanje" rotora). Na granici stabilnosti ($\delta=90^\circ$) je $M_{sin}=0$:
opruga više ne vraća. Uoči i praktičnu posledicu iz Zadatka 16: mašina koja daje samo reaktivnu
snagu ($\delta=0$, $\cos\delta=1$) ima **veći** sinhronizirajući moment od one koja nosi aktivnu
snagu — aktivno opterećenje "troši" rezervu krutosti.

---

## 10. Mašina sa istaknutim polovima: $d$- i $q$-osa, $X_d$, $X_q$ i reluktantni moment

### 10.1 Zašto dve ose i dve reaktanse

Kod istaknutih polova vazdušni zazor nije ravnomeran, pa razlikujemo dva karakteristična pravca
(gledano iz rotora, koji rotira zajedno sa njima):

- **$d$-osa (direktna, podužna)** — osa pola rotora (pravac pobudnog fluksa). Zazor mali,
  magnetni otpor mali, fluks "lako" prolazi;
- **$q$-osa (kvadraturna, poprečna)** — osa **između** polova, pomerena $90^\circ$ električnih.
  Zazor veliki (međupolni prostor), magnetni otpor veliki.

Reakcija indukta zato zavisi od pravca: ista struja statora napravi **veći** fluks ako deluje u
$d$-osi nego u $q$-osi. Umesto jedne reaktanse reakcije indukta imamo dve, i ukupno:

$$X_d = X_{\gamma} + X_{ad} \qquad X_q = X_{\gamma} + X_{aq} \qquad\bigl(X_d > X_q\ \text{kod klasične mašine}\bigr)$$

gde je $X_\gamma$ (isto što i $X_{\gamma s}$) rasipna reaktansa statora, a $X_{ad}$, $X_{aq}$ su
reaktanse reakcije indukta po podužnoj odnosno poprečnoj osi (ova sabiranja radi Zadatak 9;
u zadacima 7, 8, 20, 21 zadaju se direktno $x_d$, $x_q$ u relativnim jedinicama, §12).
Cilindrični rotor je specijalan slučaj $X_d = X_q = X_s$.

### 10.2 Dvoreakcijska teorija: razlaganje struje i naponske jednačine

Ideja (Blondelova dvoreakcijska teorija): struju statora razložimo na komponentu koja magnetno
deluje u $d$-osi i komponentu u $q$-osi, pa svaku "naplatimo" njenom reaktansom:

$$\mathbf{I}_f = \mathbf{I}_d + \mathbf{I}_q, \qquad \boxed{\;\mathbf{E}_{0f} = \mathbf{U}_f + \mathrm{j}X_d\,\mathbf{I}_d + \mathrm{j}X_q\,\mathbf{I}_q\;}\quad (R_s\approx0)$$

U fazorskom dijagramu (slike 7.1, 8.1, 9. u zbirci) $q$-osa se poklapa sa pravcem
$\mathbf{E}_{0f}$ (EMS kasni $90^\circ$ za pobudnim fluksom koji je u $d$-osi), $\mathbf{U}_f$
zaklapa ugao $\delta$ sa $q$-osom, a struja ugao $\varphi$ sa naponom, tj. $\varphi+\delta$ sa
$q$-osom (nadpobuđen generator). Projekcije vektorske jednačine na $q$- i $d$-osu (isti zanat kao
u §4.3 — pad $\mathrm{j}X_d\mathbf{I}_d$ je normalan na $d$-osu tj. leži u $q$-osi, i obrnuto):

$$\begin{aligned}
\text{na } q\text{-osu:}\quad & U_f\cos\delta = E_{0f} - X_d\,I_d \\
\text{na } d\text{-osu:}\quad & U_f\sin\delta = X_q\,I_q
\end{aligned}$$

a komponente struje su (geometrija: ugao struje prema $q$-osi je $\varphi+\delta$):

$$I_d = I_f\sin(\varphi+\delta) \qquad I_q = I_f\cos(\varphi+\delta)$$

(Za podpobuđen režim, gde struja prednjači, u Zadatku 9 ove definicije glase
$I_d = I_f\sin(\varphi-\delta)$, $I_q=I_f\cos(\varphi-\delta)$ — ista geometrija, drugi znak
ugla.) Ove tri jednačine su ceo "mašinski park" zadataka 7, 8 i 9: dve nepoznate
($\delta$ i $E_{0f}$) iz dve projekcije, uz eliminaciju $I_d$, $I_q$.

### 10.3 Izvođenje ugaone karakteristike sa reluktantnom komponentom

**Korak 1.** Polazimo opet od $P = 3U_fI_f\cos\varphi$. Razložimo $\cos\varphi$ preko ugla prema
$q$-osi: $\varphi = (\varphi+\delta)-\delta$, pa po adicionoj formuli kosinusa
($\cos(A-B)=\cos A\cos B+\sin A\sin B$):

$$\cos\varphi = \cos(\varphi+\delta)\cos\delta + \sin(\varphi+\delta)\sin\delta$$

**Korak 2.** Pomnožimo sa $3U_fI_f$ i prepoznamo komponente struje iz §10.2:

$$P = 3U_f\bigl[\underbrace{I_f\cos(\varphi+\delta)}_{I_q}\cos\delta + \underbrace{I_f\sin(\varphi+\delta)}_{I_d}\sin\delta\bigr] = 3U_f\bigl(I_q\cos\delta + I_d\sin\delta\bigr)$$

**Korak 3.** Iz projekcionih jednačina izrazimo struje:

$$I_q = \frac{U_f\sin\delta}{X_q}, \qquad I_d = \frac{E_{0f}-U_f\cos\delta}{X_d}$$

**Korak 4.** Uvrstimo i sredimo, član po član:

$$P = 3U_f\left[\frac{U_f\sin\delta\cos\delta}{X_q} + \frac{E_{0f}\sin\delta}{X_d} - \frac{U_f\cos\delta\sin\delta}{X_d}\right]$$

$$P = \frac{3U_fE_{0f}}{X_d}\sin\delta + 3U_f^2\sin\delta\cos\delta\left(\frac{1}{X_q}-\frac{1}{X_d}\right)$$

**Korak 5.** Iskoristimo trigonometrijski identitet $\sin\delta\cos\delta = \tfrac12\sin 2\delta$:

$$\boxed{\;P(\delta) = \underbrace{\frac{3\,U_f\,E_{0f}}{X_d}\,\sin\delta}_{\text{osnovna (sinhrona) komp.}} + \underbrace{\frac{3\,U_f^2}{2}\left(\frac{1}{X_q}-\frac{1}{X_d}\right)\sin 2\delta}_{\text{reluktantna komponenta}}\;}\qquad M(\delta)=\frac{P(\delta)}{\Omega_{sm}}$$

**Tumačenje.** Prvi sabirak je stara poznata sinusna karakteristika (samo sa $X_d$ umesto
$X_s$). Drugi sabirak je **reluktantna komponenta**: postoji **i bez pobude** ($E_{0f}=0$!),
a potiče isključivo od razlike magnetnih otpora po osama ($X_d\neq X_q$); menja se sa
$\sin2\delta$ (period dvostruko kraći). Kod cilindričnog rotora ($X_d=X_q$) zagrada je nula i
formula se svodi na §8.

**Intuicija za reluktantni moment:** gvozdena igla kompasa nema sopstveni magnet, pa se ipak
okreće da legne u pravac polja — jer time minimizuje magnetni otpor na putu fluksa. Isto tako
polje mreže "namešta" istaknute polove rotora u povoljan položaj: to je moment bez ikakve pobude.
Baš na tome rade zadaci 20 i 21 (rad generatora sa **prekinutom pobudom**: $E_{0f}=0$, ostaje
samo reluktantni član, maksimalan pri $\delta=45^\circ$ jer je tada $\sin2\delta=1$).

**Stabilnost:** zbog $\sin2\delta$ člana maksimum ukupne karakteristike (prevalni ugao) je kod
mašine sa istaknutim polovima **manji od $90^\circ$** (tipično $60^\circ$–$80^\circ$); uslov
stabilnosti je i dalje $\mathrm{d}P/\mathrm{d}\delta>0$, granica je tamo gde je taj izvod nula
(traži se u Zadatku 19 rešavanjem $\mathrm{d}P/\mathrm{d}\delta=0$).

---

## 11. Pogonska karta sinhronog generatora

### 11.1 Šta je i odakle nastaje

**Pogonska karta** (dijagram snage, engl. *capability chart*) je "mapa dozvoljene teritorije"
generatora u ravni snaga: prikazuje sve parove $(Q, P)$ u kojima generator sme **trajno** da
radi. U ovoj zbirci (zadaci 22 i 23) konvencija je: **apscisa = reaktivna snaga $q$, ordinata =
aktivna snaga $p$**, sve u relativnim jedinicama (§12) i obično za nazivni napon $u=1$.
Radna tačka generatora u pogonu se prati upravo na ovoj karti; proizvođač garantuje rad unutar
ucrtanih granica.

Nastanak iz fazorskog dijagrama (konstrukcija sa slike 22.1 u zbirci) — tri koraka:

1. Uzmi naponski fazorski dijagram $\mathbf{E}_{0f}=\mathbf{U}_f+\mathrm{j}X_s\mathbf{I}_f$
   i **podeli sve stranice sa $X_s$**: dobija se "strujni trougao" sa stranicama $E_{0f}/X_s$,
   $U_f/X_s$ i $I_f$.
2. **Zarotiraj ga za $90^\circ$** (da pad $\mathrm{j}X_s\mathbf{I}_f/X_s$, tj. sama struja,
   legne u koordinatne ose).
3. **Pomnoži sve sa $3U_f$** (u r.j. sa $u$): stranice postaju snage, jer je
   $3U_fI_f\cos\varphi = P$ i $3U_fI_f\sin\varphi=Q$.

Analitički, isto to (u relativnim jedinicama, §12, gde nestaje trojka) — iz §8.2 i §8.4:

$$p = \frac{u\,e_0}{x_s}\sin\delta, \qquad q = \frac{u\,e_0}{x_s}\cos\delta - \frac{u^2}{x_s}$$

Kvadriranjem i sabiranjem (da eliminišemo $\delta$; $\sin^2+\cos^2=1$):

$$p^2 + \left(q+\frac{u^2}{x_s}\right)^2 = \left(\frac{u\,e_0}{x_s}\right)^2$$

Radna tačka, dakle, za **fiksnu pobudu** ($e_0=\mathrm{const}$) leži na **kružnici** sa centrom
u tački $(q,p)=\bigl(-u^2/x_s,\ 0\bigr)$ i poluprečnikom $u\,e_0/x_s$. Menjanjem pobude menja se
poluprečnik; menjanjem snage turbine tačka klizi po kružnici (menja se $\delta$). Centar
$(-u^2/x_s,\,0)$ je "prirodni koordinatni početak" karte — tačka u kojoj bi mašina bila sa
$e_0=0$.

### 11.2 Svih šest ograničenja

Granice dozvoljene oblasti (spisak iz Zadatka 22, jednačine za $u=1$):

1. **Zagrevanje statorskog namotaja** (maksimalna trajna struja statora $i\le i_n$): iz
   $s=u\cdot i$ i $s^2=p^2+q^2$ sledi **kružnica prividne snage** oko koordinatnog početka:
   $$p^2+q^2 \le (u\,i_n)^2 = 1$$
2. **Zagrevanje rotorskog (pobudnog) namotaja** (maksimalna pobudna struja, tj. $e_0\le e_{0n}$):
   kružnica iz §11.1 sa maksimalnim poluprečnikom:
   $$p^2+\left(q+\frac{u^2}{x_s}\right)^2 \le \left(\frac{e_{0n}\,u}{x_s}\right)^2$$
3. **Minimalna struja pobude** ($e_0\ge e_{0min}$; pobuda se nikad ne obara na nulu): ista
   familija kružnica, sad kao **donja** granica poluprečnika:
   $$p^2+\left(q+\frac{u^2}{x_s}\right)^2 \ge \left(\frac{e_{0min}\,u}{x_s}\right)^2$$
4. **Maksimalna snaga turbine:** horizontalna prava $p \le p_{max}$ (ako nije zadata, uzima se
   $p_{max}=p_n=s_n\cos\varphi_n$).
5. **Minimalna snaga turbine:** $p \ge p_{min}$ (tehnološki minimum turbine; kod Peltonove
   turbine ograničenja praktično nema, kod Kaplanove/Francisove tipično 5–30 % nazivne snage).
6. **Statička stabilnost:** teorijski $\delta\le90^\circ$, što je na karti **vertikala kroz
   centar kružnica**, $q = -u^2/x_s$ (za $\delta=90^\circ$ je $q$-koordinata tačke na kružnici
   upravo $-u^2/x_s$). **Praktična** granica uzima marginu: u Zadatku 22 uslov je da pri svakoj
   pobudi aktivna snaga sme biti najviše $p_{max}(e_0)-0{,}1\,s_n$, gde je $p_{max}(e_0)=e_0u/x_s$
   vrh odgovarajuće kružnice — dobija se kriva malo "uvučena" u odnosu na teorijsku vertikalu.

Dozvoljena oblast je presek svega navedenog. Desna polovina karte ($q>0$) je **nadpobuđen** rad
(daje $Q$), leva ($q<0$) **podpobuđen** (uzima $Q$) — leva strana je tipično "opasnija" jer se
tamo sustižu ograničenja 3 i 6.

**Mini-primer (Zadatak 22):** $x_s=1{,}4$ r.j., $\cos\varphi_n=0{,}8$ ⟹ nazivna tačka
$p_n=0{,}8$, $q_n=0{,}6$. Nazivna EMS iz uslova da nazivna tačka leži na rotorskoj kružnici:

$$e_{0n}=\frac{x_s}{u_n}\sqrt{p_n^2+\left(q_n+\frac{u_n^2}{x_s}\right)^2} = 1{,}4\cdot\sqrt{0{,}8^2+\Bigl(0{,}6+\frac{1}{1{,}4}\Bigr)^2}=2{,}154\ \mathrm{r.j.}$$

pa je rotorska kružnica: centar $(-1/1{,}4,\,0)=(-0{,}714,\,0)$, poluprečnik
$e_{0n}/x_s = 2{,}154/1{,}4 = 1{,}539$ r.j.; statorska kružnica: centar $(0,0)$, poluprečnik 1.

### 11.3 Čemu karta služi

Operater elektrane u svakom trenutku vidi gde mu je radna tačka i koliko sme da "dogura" pobudu
ili turbinu a da ništa ne pregreje i ne ugrozi stabilnost. Za zadatke: kad se traži "nacrtaj
pogonsku kartu", redosled je uvek isti — statorska kružnica → prave $p_{max}$, $p_{min}$ →
rotorske kružnice ($e_{0n}$ i $e_{0min}$) → granica stabilnosti.

---

## 12. Relativne (per-unit) jedinice

### 12.1 Ideja i bazne veličine

**Relativne jedinice (r.j.**, engl. *per-unit, p.u.*) izražavaju svaku veličinu kao **udeo njene
bazne vrednosti** — "koliko puta nazivna". Prednosti: brojevi postanu mali i uporedivi među
mašinama svih veličina (svaka zdrava mašina ima $x_s$ između ~0,5 i ~2,5 r.j.), nestaju
$\sqrt3$ i faktor 3, i odmah se vidi preopterećenje ($i=1{,}367$ r.j. = 36,7 % preko nazivne
struje — tako u Zadatku 11b).

Standardni izbor baznih veličina (Zadatak 11; velika slova = apsolutne, mala = relativne):

$$U_b = U_{fn}\ (\text{nazivni fazni napon}),\qquad I_b = I_{fn}\ (\text{nazivna fazna struja}),\qquad S_b = S_n = 3\,U_{fn}I_{fn},\qquad \Omega_b = \Omega_{smn}$$

$$u = \frac{U}{U_b},\quad i = \frac{I}{I_b},\quad s=\frac{S}{S_b},\quad p=\frac{P}{S_b},\quad q=\frac{Q}{S_b},\quad e_0=\frac{E_{0f}}{U_b},\quad m=\frac{M}{M_b}$$

**Bazna impedansa** — izvedimo je pažljivo, jer se formula stalno koristi (zadaci 7, 8, 9, 18, 26):

$$Z_b = \frac{U_b}{I_b} = \frac{U_{fn}}{I_{fn}} = \frac{U_n/\sqrt3}{S_n/(\sqrt3\,U_n)} = \boxed{\;\frac{U_n^2}{S_n}\;}$$

— pazi: iako su baze **fazne**, u krajnjoj formuli figurišu **linijski** napon $U_n$ i
**trofazna** snaga $S_n$ ($\sqrt3$ se pokrati!). Provere:
$Z_b = 5{,}5^2/6{,}5 = 4{,}65\ \Omega$ (Zadatak 7); $Z_b = 6{,}6^2/5=8{,}712\ \Omega$ (Zadatak 9);
$Z_b = 13{,}8^2/203{,}5 = 0{,}9358\ \Omega$ (Zadatak 8). Reaktansa zadata u procentima ili r.j.
pretvara se u ome kao:

$$X = \frac{x[\%]}{100}\cdot Z_b = x[\mathrm{r.j.}]\cdot Z_b$$

**Bazni moment** se bira kao $M_b = S_b/\Omega_b$ — baš zato da bi i u r.j. važilo
"moment = snaga / brzina" bez ikakvog dodatnog koeficijenta.

### 12.2 U per-unit domenu nestaje trojka

Pokažimo tvrđenje koje Zadatak 11 detaljno izvodi. Trofazna prividna snaga je
$S = 3U_fI_f$. Podelimo sa $S_b=3U_{fn}I_{fn}$:

$$s = \frac{S}{S_b} = \frac{3\,U_f I_f}{3\,U_{fn}I_{fn}} = \frac{U_f}{U_{fn}}\cdot\frac{I_f}{I_{fn}} = u\cdot i$$

Trojka se pokratila! Isto važi za sve izraze, pa ugaone karakteristike u r.j. glase:

$$p = \frac{u\,e_0}{x_s}\sin\delta, \qquad m = \frac{u\,e_0}{\omega_{sm}\,x_s}\sin\delta \qquad(\omega_{sm}\ \text{u r.j.};\ \text{pri nazivnoj brzini } \omega_{sm}=1\ \Rightarrow\ p=m)$$

**Mini-primer (Zadatak 11a).** Turbogenerator 16 MVA, $\cos\varphi_n=0{,}8$, 3000 min⁻¹,
$x_s=2$ r.j. U nazivnom režimu je $u_{fn}=1$, $i_{fn}=1$, $\omega_{sm}=1$, pa kosinusna teorema
(ista kao u §8.3, samo r.j.) daje:

$$e_{0fn}=\sqrt{u_{fn}^2+(x_s i_{fn})^2+2\,u_{fn}x_s i_{fn}\sin\varphi_n} = \sqrt{1+(2\cdot1)^2+2\cdot1\cdot2\cdot1\cdot0{,}6}=2{,}72\ \mathrm{r.j.}$$

$$m_{pr}=\frac{u_{fn}\,e_{0fn}}{\omega_{sm}\,x_s}=\frac{1\cdot2{,}72}{1\cdot2}=1{,}36\ \mathrm{r.j.}$$

Vraćanje u apsolutne jedinice množenjem baznom vrednošću:

$$M_{pr}=m_{pr}\cdot M_b = m_{pr}\cdot\frac{S_n}{\Omega_b}=1{,}36\cdot\frac{16\cdot10^6}{\frac{2\pi}{60}\cdot3000}=69{,}26\ \mathrm{kNm}$$

---

## 13. Sinhroni motor

### 13.1 Jednačina i fazorski dijagram

Sve iz §4–§10 važi i za motor; razlike su samo: naponska jednačina
$\mathbf{U}_f=\mathbf{E}_{0f}+\mathrm{j}X_s\mathbf{I}_f$ (§4.4), $\mathbf{E}_{0f}$ **kasni** za
$\mathbf{U}_f$ (ugao $\delta$ na drugu stranu), a snaga i moment "ulaze" u mašinu. Ugaone
karakteristike $P(\delta)$, $M(\delta)$ su identične (zadaci 10, 12, 19). Ključna prednost
sinhronog motora nad asinhronim: brzina mu je **konstantna** nezavisno od opterećenja i faktor
snage mu se **podešava pobudom** (može čak da popravlja $\cos\varphi$ celog postrojenja).

### 13.2 Pokretanje

Sinhroni motor **nije samopokretljiv**: pri stojećem rotoru obrtno polje "protrčava" pored njega
50 puta u sekundi, moment menja znak svake poluperiode i srednja vrednost mu je nula (rotor od
inercije ne stigne ni da krene — kao da hvataš ringišpil u punoj brzini). Tri praktična rešenja:

1. **Asinhrono pokretanje** (najčešće): na rotor se ugradi kavezni, tzv. **prigušni (amortizerski)
   namotaj**, pa motor krene kao asinhroni (pobudni namotaj je za to vreme kratko spojen preko
   otpornika — da se u njemu ne indukuje opasan napon). Kad se brzina približi sinhronoj,
   uključi se pobuda i rotor "uskoči" u sinhronizam.
2. **Pomoćni (zaletni) motor** dotera mašinu do sinhrone brzine, pa se ona sinhronizuje na mrežu
   kao generator i onda optereti.
3. **Frekventno pokretanje**: napajanje iz pretvarača učestanosti koji $f$ (a time i $n_s$)
   podiže postepeno od nule — ovako rade i savremeni PMSM pogoni (§14).

### 13.3 V-krive i sinhroni kompenzator (koncept za Zadatak 14)

Posmatraj motor koji nosi **konstantno aktivno opterećenje** ($P=\mathrm{const}$, $U_f$ mrežni),
dok mu menjamo **samo pobudu** $I_p$. Iz dve ugaone jednakosti slede dva "koloseka" po kojima se
fazori smeju kretati:

$$P = 3U_fI_f\cos\varphi = \mathrm{const} \ \Rightarrow\ I_f\cos\varphi = \mathrm{const} \qquad\text{i}\qquad P=\frac{3U_fE_{0f}}{X_s}\sin\delta=\mathrm{const} \ \Rightarrow\ E_{0f}\sin\delta = \mathrm{const}$$

— vrh fazora struje klizi po pravoj normalnoj na $U_f$ (konstantna aktivna komponenta struje),
a vrh fazora $E_{0f}$ po pravoj paralelnoj $U_f$ (konstantna "visina"). Ovo je ceo trik
Zadatka 14: iz starog režima nađeš $E_{0f}'\sin\delta'$ i $I'\cos\varphi'$, u novom režimu su
te dve veličine iste, pa iz novog $\cos\varphi$ sve izračunaš.

Nacrtaš li zavisnost struje statora od struje pobude, $I_f(I_p)$, pri $P=\mathrm{const}$, dobijaš
krivu oblika slova **V** — otuda **V-krive**:

- levo (mala pobuda, podpobuđen): motor uzima $Q$, struja velika i induktivna;
- dno V-a: $\cos\varphi=1$, struja **minimalna** (čisto aktivna);
- desno (nadpobuđen): motor daje $Q$, struja opet raste ali kapacitivna.

Za svako opterećenje postoji po jedna V-kriva (veće $P$ = viša kriva). Nadpobuđen sinhroni motor
bez mehaničkog tereta, koji radi samo da bi davao reaktivnu snagu, zove se **sinhroni
kompenzator** — "fabrika reaktivne snage" za popravku faktora snage mreže.

---

## 14. Sinhroni motor sa stalnim magnetima (PMSM) i vektorsko upravljanje (za Zadatak 27)

### 14.1 Šta je PMSM i po čemu je poseban

**PMSM** (*Permanent Magnet Synchronous Motor*, sinhroni motor sa stalnim magnetima) umesto
pobudnog namotaja ima **permanentne magnete** na rotoru: nema pobudne struje, nema kliznih
prstenova, nema gubitaka pobude — zato dominira u savremenim regulisanim pogonima (roboti,
električna vozila). EMS $e$ je fiksirana fluksom magneta (ne može se "odvrnuti" pobudom).

Ključna konstruktivna posledica za mašine sa **ugrađenim** (utopljenim) magnetima: magnet se
magnetno ponaša **kao vazduh** (relativna permeabilnost ~1), a nalazi se u $d$-osi. Zato je
magnetni otpor u $d$-osi **veći** nego u $q$-osi, pa je:

$$x_d < x_q \qquad\text{(obrnuto nego kod klasične mašine sa istaknutim polovima!)}$$

U Zadatku 27: $x_d = x_{ad}+x_\gamma = 0{,}3+0{,}1=0{,}4$ r.j.,
$x_q = x_{aq}+x_\gamma = 0{,}8+0{,}1=0{,}9$ r.j.

### 14.2 $dq$ koordinatni sistem i vektorsko upravljanje

Savremeni pogon napaja motor iz **strujno regulisanog invertora**. Mere se fazne struje i
**položaj rotora**, pa se struje trigonometrijskim transformacijama preračunaju u koordinatni
sistem **vezan za rotor** (rotira zajedno sa njim):

- $d$-osa = pravac fluksa magneta rotora;
- $q$-osa = $90^\circ$ ispred; u njoj leži fazor EMS $e$ (EMS kasni za fluksom $90^\circ$... i
  zato se poklapa sa $q$-osom — isto pravilo kao u §5.3).

U ustaljenom stanju su $d$- i $q$-komponente struje ($i_d$, $i_q$) **konstantne** (jednosmerne!)
veličine. **Vektorsko upravljanje** znači: dva nezavisna regulatora drže $i_d$ i $i_q$ na
zadatim vrednostima —

- $i_d$ leži u osi fluksa rotora → njome se utiče na **ukupan fluks** mašine (negativno $i_d$
  **razmagnetiše**, "slabljenje polja");
- $i_q$ je normalna na fluks → ona pravi **moment** (kao sila na provodnik pod pravim uglom u polju).

Naponske jednačine u $dq$ sistemu, u relativnim jedinicama, ustaljeno stanje (motor; pri
$\omega=1$ r.j.; ovo su jednačine iza fazorskih dijagrama 27.2 i 27.3 u zbirci):

$$u_d = r_s\,i_d - x_q\,i_q \qquad u_q = r_s\,i_q + x_d\,i_d + e \qquad u=\sqrt{u_d^2+u_q^2}$$

($r_s$ — otpor statora u r.j.; članovi $\mp x\,i$ su "rotacioni" padovi: struja u jednoj osi
pravi pad napona u drugoj, jer je pad na reaktansi zaokrenut za $90^\circ$).

### 14.3 Moment PMSM — izvođenje

**Korak 1.** Električna ulazna snaga preko $dq$ komponenti (snagu prave komponente napona i
struje "u istoj osi"):

$$p_{el} = u_d\,i_d + u_q\,i_q$$

**Korak 2.** Uvrstimo naponske jednačine iz §14.2:

$$p_{el} = (r_s i_d - x_q i_q)\,i_d + (r_s i_q + x_d i_d + e)\,i_q = r_s\underbrace{(i_d^2+i_q^2)}_{i^2} + (x_d - x_q)\,i_d\,i_q + e\,i_q$$

**Korak 3.** Mehanička snaga = električna minus gubici u bakru ($p_{Cu}=r_si^2$; gubici u
gvožđu i mehanički zanemareni), a moment = snaga / brzina ($\omega_{sm}=1$ pri nazivnoj
učestanosti):

$$\boxed{\;m = \frac{p_m}{\omega_{sm}} = e\,i_q + (x_d-x_q)\,i_d\,i_q\;}$$

Prvi član je **osnovna** (elektromagnetna) komponenta — fluks magneta × struja momenta. Drugi je
**reluktantna** komponenta — rođeni brat $\sin2\delta$ člana iz §10.3, sada izražen strujama.

**Korak 4 — parametrizacija uglom $\gamma$.** Neka je $i$ amplituda strujnog vektora, a
$\gamma$ ugao za koji je on zakrenut od $q$-ose **ka negativnoj $d$-osi** (demagnetišuća
strana):

$$i_d = -\,i\sin\gamma \qquad i_q = i\cos\gamma$$

Uvrštavanjem u izraz za moment i korišćenjem $\sin\gamma\cos\gamma=\tfrac12\sin2\gamma$:

$$m(\gamma) = e\,i\cos\gamma + (x_d-x_q)\,(-i\sin\gamma)(i\cos\gamma) = \boxed{\;e\,i\cos\gamma + \tfrac12\,(x_q-x_d)\,i^2\sin 2\gamma\;}$$

Pošto je kod PMSM $x_q>x_d$, reluktantni član je **pozitivan** za $0<\gamma<90^\circ$: guranjem
struje na demagnetišuću stranu dobijamo reluktantni "bonus" momenta.

### 14.4 Strategija $i_d=0$ i maksimalni moment (MTPA) — brojevi Zadatka 27

**(a) Strategija $i_d=0$** ("guraj ljuljašku tačno pod pravim uglom"): sav strujni kapacitet u
$q$-osu, $\gamma=0$. Za podatke Zadatka 27 ($e=1$, $r_s=0{,}03$, $x_d=0{,}4$, $x_q=0{,}9$,
$i_q=i=1$ r.j.): moment $m = e\,i = 1$ r.j.; napon
$u=\sqrt{(e+r_si_q)^2+(x_qi_q)^2}=\sqrt{1{,}03^2+0{,}9^2}=1{,}368$ r.j.; faktor snage
$\cos\varphi = p_{el}/(u\,i) = 1{,}03/1{,}368 = 0{,}753$.

**(b) Maksimalni moment po amperu (MTPA).** Pri ograničenoj amplitudi struje ($i=1$) tražimo
$\gamma$ koji maksimizuje $m(\gamma)$ — standardni recept: izvod pa nula.

$$\frac{\mathrm{d}m}{\mathrm{d}\gamma} = -e\,i\sin\gamma + (x_q-x_d)\,i^2\cos2\gamma = 0$$

Zamenom $\cos2\gamma = 1-2\sin^2\gamma$ dobijamo kvadratnu jednačinu po $\sin\gamma$:

$$2(x_q-x_d)\,i^2\sin^2\gamma + e\,i\,\sin\gamma - (x_q-x_d)\,i^2 = 0$$

Za brojeve Zadatka 27 ($e=i=1$, $x_q-x_d=0{,}5$): $\sin^2\gamma+\sin\gamma-0{,}5=0$, pa
$\sin\gamma = \frac{-1+\sqrt{1+2}}{2}=0{,}366$, tj.

$$\gamma = 21{,}47^\circ \qquad i_d = -\,i\sin\gamma=-0{,}366\ \mathrm{r.j.} \qquad i_q = i\cos\gamma = 0{,}931\ \mathrm{r.j.}$$

$$m_{max} = 1\cdot1\cdot\cos 21{,}47^\circ + \tfrac12\cdot0{,}5\cdot1^2\cdot\sin 42{,}94^\circ = 0{,}931+0{,}170 = 1{,}10\ \mathrm{r.j.}$$

Dakle **10 % više momenta** za istu struju nego sa $i_d=0$ — iako je i fluks manji i $i_q$
manji, reluktantni dobitak preteže. Potreban napon (jednačine §14.2 sa $i_d=-0{,}366$):

$$u=\sqrt{\bigl(e+r_si_q+x_di_d\bigr)^2+\bigl(x_qi_q-r_si_d\bigr)^2}=\sqrt{(1+0{,}028-0{,}146)^2+(0{,}838+0{,}011)^2}=1{,}223\ \mathrm{r.j.}$$

> **Napomena o originalu:** u zbirci je uz deo (b) Zadatka 27 komponenta $i_d$ ispisana kao
> $i_d = i\sin\gamma = 0{,}366$ r.j. (bez predznaka), a u formuli za napon stoji
> $(e+r_s i_q + x_d i_d)$; brojčani rezultat $u=1{,}223$ r.j. izlazi tačno onda kada se u tu
> formulu uvrsti **demagnetišuće**, dakle negativno $i_d=-0{,}366$ (provereno računom:
> $\sqrt{0{,}8815^2+0{,}8485^2}=1{,}223$). Fizika je nedvosmislena — struja se pomera na
> demagnetišuću stranu — pa smo ovde predznak pisali eksplicitno.

---

## 15. Minimalni komplet formula (pregled za ponavljanje)

| # | Formula | Šta daje | Sekcija |
|---|---|---|---|
| 1 | $n_s = 60f/p$; $\Omega_{sm}=2\pi f/p$ | sinhrona brzina | §2.2 |
| 2 | $I_n = S_n/(\sqrt3\,U_n)$; $U_f=U/\sqrt3$ (Y) | nazivna struja, fazni napon | §2, §4 |
| 3 | $\mathbf{E}_{0f}=\mathbf{U}_f+R_s\mathbf{I}_f+\mathrm{j}X_s\mathbf{I}_f$ | naponska jednačina generatora | §4.1 |
| 4 | $E_{0f}\cos\delta=U_f+X_sI_f\sin\varphi$; $E_{0f}\sin\delta=X_sI_f\cos\varphi$ | projekcije fazorskog dijagrama | §4.3 |
| 5 | $\overline{F}_r=\overline{F}_{rez}-\overline{F}_s$; $E\propto F$; EMS kasni $90^\circ$ za MPS | dijagram MPS | §5 |
| 6 | $P=3U_fE_{0f}\sin\delta/X_s$; $M=P/\Omega_{sm}$ | ugaona karakteristika (cilindrični) | §8 |
| 7 | $Q=3U_f(E_{0f}\cos\delta-U_f)/X_s$ | reaktivna snaga; znak = nad/podpobuđen | §6, §8.4 |
| 8 | $M_{sin}=3U_fE_{0f}\cos\delta/(\Omega_{sm}X_s)$ | sinhronizirajući moment | §9.2 |
| 9 | $P=\frac{3U_fE_{0f}}{X_d}\sin\delta+\frac{3U_f^2}{2}\bigl(\frac{1}{X_q}-\frac{1}{X_d}\bigr)\sin2\delta$ | istaknuti polovi | §10.3 |
| 10 | $U_f\cos\delta=E_{0f}-X_dI_d$; $U_f\sin\delta=X_qI_q$ | projekcije na $q$/$d$ osu | §10.2 |
| 11 | $p^2+(q+u^2/x_s)^2=(ue_0/x_s)^2$; $p^2+q^2=(ui)^2$ | kružnice pogonske karte | §11 |
| 12 | $Z_b=U_n^2/S_n$; $X=x[\mathrm{r.j.}]\cdot Z_b$; $s=u\,i$; $M_b=S_b/\Omega_b$ | relativne jedinice | §12 |
| 13 | $I\cos\varphi=\mathrm{const}$, $E_0\sin\delta=\mathrm{const}$ pri $P=\mathrm{const}$ | V-krive / promena pobude | §13.3 |
| 14 | $m=e\,i_q+(x_d-x_q)i_di_q$; MTPA: $2(x_q-x_d)i^2\sin^2\gamma+ei\sin\gamma-(x_q-x_d)i^2=0$ | PMSM moment | §14 |

---

## 16. Rečnik oznaka (svi simboli iz zadataka 1–27)

Napomena o indeksima: **n** = nazivna (nominalna) vrednost, **f** = fazna vrednost,
**b** = bazna vrednost, **0** = prazan hod, prim (′) i sekund (″) = prvi i drugi režim u
zadatku. Mala slova = relativne jedinice (r.j.), velika = apsolutne.

### Nazivni podaci i priključne veličine

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $S_n$ | nazivna prividna snaga | $\mathrm{VA}$ ($\mathrm{MVA}$) |
| $P_n$ | nazivna aktivna snaga | $\mathrm{W}$ ($\mathrm{MW}$) |
| $U_n$ | nazivni linijski (međufazni) napon | $\mathrm{V}$ |
| $U_{nf}$, $U_{fn}$ | nazivni fazni napon, $U_n/\sqrt3$ kod sprege Y | $\mathrm{V}$ |
| $I_n$, $I_{nf}$, $I_{fn}$ | nazivna (fazna) struja statora, $S_n/(\sqrt3 U_n)$ | $\mathrm{A}$ |
| $f$, $f_n$ | učestanost (nazivna) | $\mathrm{Hz}$ |
| $p$ | broj pari polova (pazi: malo $p$ je i aktivna snaga u r.j. — kontekst!) | – |
| $n$, $n_n$, $n_s$ | brzina obrtanja; nazivna; sinhrona | $\mathrm{min^{-1}}$ |
| $\cos\varphi$, $\cos\varphi_n$ | faktor snage (nazivni); "ind."= struja kasni, "kap."= prednjači | – |
| Y, D | sprega statora zvezda / trougao | – |
| $\mathrm{hp}$ | konjska snaga: $1\ \mathrm{hp}=735\ \mathrm{W}$ (Zadatak 19) | – |

### Naponi i elektromotorne sile

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $U$, $U_s$ | linijski napon mreže/statora | $\mathrm{V}$ |
| $U_f$, $U_{sf}$ | fazni napon statora | $\mathrm{V}$ |
| $E_0$, $E_{0f}$, $E_{0sf}$ | EMS praznog hoda po fazi (samo od pobudnog fluksa) | $\mathrm{V}$ |
| $E_{0fn}$ | EMS praznog hoda pri nazivnoj pobudi | $\mathrm{V}$ |
| $E_{0l}$ | linijska EMS praznog hoda, $\sqrt3\,E_{0f}$ | $\mathrm{V}$ |
| $E_f$, $E_{sf}$ | rezultantna (unutrašnja) EMS — od $F_{rez}$, "iza" $X_{\gamma s}$ | $\mathrm{V}$ |
| $E_1$, $E_2$ | EMS u prvom/drugom režimu (Zadatak 2) | $\mathrm{V}$ |
| $\Delta U_s$ | pad napona na impedansi statora | $\mathrm{V}$ |
| $U_{kon}$ | kontrolni napon pogonske mašine (Zadatak 25) | $\mathrm{V}$ |
| $u$, $u_d$, $u_q$ | napon u r.j.; njegove $d$- i $q$-komponente | r.j. |
| $e$, $e_0$, $e_{0f}$, $e_{0n}$, $e_{0min}$ | EMS u r.j. (kod PMSM $e$ = EMS stalnih magneta) | r.j. |

### Struje

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $I$, $I_f$, $I_{sf}$ | fazna struja statora (**ne** pobudna!) | $\mathrm{A}$ |
| $I_p$, $I_P$ | struja pobude (rotora); u tabeli Zadatka 7 označena $I_f$ | $\mathrm{A}$ |
| $I_d$, $I_q$ | komponente struje statora po $d$- i $q$-osi | $\mathrm{A}$ |
| $I_K$ | struja trajnog kratkog spoja | $\mathrm{A}$ |
| $I_1$, $I_2$ | struja u prvom/drugom režimu | $\mathrm{A}$ |
| $i$, $i_d$, $i_q$ | struja u r.j. i njene $dq$ komponente | r.j. |

### Otpornosti, reaktanse, impedanse

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $R_s$ | otpor statorskog namotaja po fazi | $\Omega$ |
| $X_s$ | sinhrona reaktansa (cilindrični rotor), $X_{\gamma s}+X_a$ | $\Omega$ |
| $X_{\gamma s}$, $X_\gamma$ | rasipna reaktansa statora | $\Omega$ |
| $X_{ad}$, $X_{aq}$ | reaktansa reakcije indukta po podužnoj / poprečnoj osi | $\Omega$ |
| $X_d$, $X_q$ | sinhrona reaktansa po $d$- / $q$-osi ($X_d=X_\gamma+X_{ad}$, $X_q=X_\gamma+X_{aq}$) | $\Omega$ |
| $Z_s$ | modul impedanse statora, $\sqrt{R_s^2+X_s^2}$ | $\Omega$ |
| $Z_b$ | bazna impedansa, $U_n^2/S_n$ | $\Omega$ |
| $R$, $L$ | otpornost i induktivnost potrošača (ostrvski rad, Zadatak 24) | $\Omega$, $\mathrm{H}$ |
| $r_s$, $x_s$, $x_\gamma$, $x_{ad}$, $x_{aq}$, $x_d$, $x_q$ | iste veličine u r.j. (ili u %: podeli sa 100) | r.j. |

### Snage i momenti

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $S$, $P$, $Q$ | prividna, aktivna, reaktivna snaga ($S^2=P^2+Q^2$) | $\mathrm{VA}$, $\mathrm{W}$, $\mathrm{var}$ |
| $P_{el}$, $P_m$ | električna snaga; mehanička snaga (na vratilu) | $\mathrm{W}$ |
| $P_{Cu\,s}$ | gubici u bakru statora, $3R_sI_f^2$ | $\mathrm{W}$ |
| $P_{Fe}$ | gubici u gvožđu | $\mathrm{W}$ |
| $P_{tr,v}$ | gubici trenja i ventilacije (mehanički) | $\mathrm{W}$ |
| $P_{max}$, $P_{pr}$ | maksimalna (prevalna) snaga | $\mathrm{W}$ |
| $M$, $M_{max}$, $M_{pr}$ | elektromagnetni moment; maksimalni = prevalni | $\mathrm{Nm}$ |
| $M_{sin}$ | sinhronizirajući moment, $\mathrm{d}M/\mathrm{d}\delta$ | $\mathrm{Nm/rad}$ |
| $M_{pog}$ | moment pogonske mašine | $\mathrm{Nm}$ |
| $M_b$ | bazni moment, $S_b/\Omega_b$ | $\mathrm{Nm}$ |
| $s$, $p$, $q$, $m$, $m_{pr}$, $m_{max}$ | snage i momenti u r.j. | r.j. |
| $p_{el}$, $p_m$, $p_{Cu}$ | električna, mehanička snaga i gubici u bakru u r.j. | r.j. |
| $p_{osn}$, $p_{rel}$ | osnovna i reluktantna komponenta snage (PMSM, Zadatak 27) | r.j. |
| $p_{max}$, $p_{min}$ | maks./min. snaga turbine (pogonska karta) | r.j. |

### Magnetopobudne sile (MPS)

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $F_r$ | MPS rotora (pobude) | $\mathrm{Az}$ |
| $F_s$ | MPS statora (reakcija indukta); kolinearna sa strujom statora | $\mathrm{Az}$ |
| $F_{rez}$ | rezultantna MPS, $\overline{F}_r+\overline{F}_s$ | $\mathrm{Az}$ |
| $F_1$, $F_2$ | pobuda u prvom/drugom režimu (Zadatak 2; tamo izražena u A) | $\mathrm{A}$ |
| $K_K$ | konstanta kratkog spoja, $I_K/F_r$ | $\mathrm{A/Az}$ |
| $\mathrm{Az}$ | amper-zavojak (jedinica MPS) | – |

### Uglovi

| Oznaka | Značenje |
|---|---|
| $\varphi$ | fazni stav struje prema naponu ($\cos\varphi$ = faktor snage) |
| $\delta$ | ugao opterećenja: između $\mathbf{E}_{0f}$ i $\mathbf{U}_f$ (tj. između $q$-ose i napona) |
| $\alpha$ | pomoćni ugao u trouglu $U_f$–$Z_sI_f$–$E_{0f}$ za kosinusnu teoremu (zadaci 1, 4) |
| $\beta$ | pomoćni ugao između $-\overline{F}_s$ i $\overline{F}_{rez}$ (Zadatak 5) |
| $\gamma$ | tri značenja: ugao $\mathbf{E}_{sf}$ prema $\mathbf{U}_{sf}$ (zadaci 5, 6); ugao strujnog vektora prema $q$-osi kod PMSM (Zadatak 27); kao **indeks** — "rasipno" ($X_\gamma$) |
| $\varphi_K$ | fazni stav struje u kratkom spoju ($\approx90^\circ$, Zadatak 6) |

### Brzine i ostalo

| Oznaka | Značenje | Jedinica |
|---|---|---|
| $\omega$, $\omega_s$ | (sinhrona) električna ugaona učestanost, $2\pi f$ | $\mathrm{rad/s}$ |
| $\Omega_{sm}$, $\omega_{sm}$ | mehanička sinhrona ugaona brzina, $\omega_s/p = 2\pi n_s/60$ | $\mathrm{rad/s}$ |
| $\Omega_b$ | bazna (mehanička) ugaona brzina, $\Omega_{smn}$ | $\mathrm{rad/s}$ |
| $\Phi_0$ | fluks pobude po polu | $\mathrm{Wb}$ |
| $N$, $k_n$ | broj zavojaka po fazi; navojni sačinilac | – |
| r.j. | relativne jedinice (per-unit): veličina / bazna vrednost | – |
| $U_b$, $I_b$, $S_b$ | bazne vrednosti: $U_{fn}$, $I_{fn}$, $S_n$ | $\mathrm{V}$, $\mathrm{A}$, $\mathrm{VA}$ |

---

Time je "kutija sa alatom" kompletna: sa ovim poglavljem u ruci, svaki od zadataka 1–27 je samo
kombinacija ovde izvedenih formula — fazorski dijagram + projekcije (§4, §10), ugaone
karakteristike (§8, §10), pogonska karta (§11), relativne jedinice (§12) i, za sam kraj, PMSM
(§14). Srećno!
