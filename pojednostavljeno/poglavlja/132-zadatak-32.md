# Zadatak 32 — Bilans snaga asinhronog motora: od klizanja do stepena korisnog dejstva

## Postavka

Trofazni asinhroni motor, u spoju zvezda–zvezda (Yy), ima otpor po fazi rotora $0{,}016\ \mathrm{\Omega}$ i reaktansu rasipanja po fazi rotora (izračunatu na statorskoj frekvenciji) $0{,}256\ \mathrm{\Omega}$. Koeficijent transformacije (uz iste faktore namotaja, tj. navojne sačinioce) je $N_s : N_r = 7 : 4$. Motor je priključen na mrežu napona $380\ \mathrm{V}$ frekvencije $50\ \mathrm{Hz}$ i obrće se sa $950\ \mathrm{min^{-1}}$. U jednom pogonskom stanju motor ima statorske gubitke $2{,}2\ \mathrm{kW}$ i gubitke trenja i ventilacije $2\ \mathrm{kW}$.

Naći: klizanje, rotorsku frekvenciju, struju rotora, gubitke u bakru rotora, snagu obrtnog polja, proizvedenu mehaničku snagu (snagu konverzije), korisnu mehaničku snagu na vratilu i stepen korisnog dejstva za to pogonsko stanje.

> **Prevod na običan jezik:** Imamo običan trofazni asinhroni motor priključen na standardnu mrežu 380 V / 50 Hz. Znamo kakav mu je rotor (otpor i rasipna reaktansa jedne faze rotorskog namotaja), znamo odnos broja navojaka statora i rotora (kao kod transformatora: 7 prema 4), i znamo da se osovina okreće 950 obrtaja u minuti. Rečeno nam je i koliko snage "propadne" u statoru (2,2 kW — bakar + gvožđe statora zajedno) i koliko ode na trenje ležajeva i ventilator (2 kW). Zadatak od nas traži da "isprati­mo put snage" kroz motor: koliko snage pređe sa statora na rotor preko magnetnog polja, koliko se od toga pretvori u toplotu u rotorskim provodnicima, koliko se pretvori u mehaničku snagu, koliko od te mehaničke snage stvarno stigne na vratilo — i, na kraju, koliki je ukupni stepen iskorišćenja motora. Usput moramo da izračunamo i klizanje, frekvenciju rotorskih struja i samu struju rotora.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Otpor po fazi rotora | $R_r$ | $0{,}016\ \mathrm{\Omega}$ | Omski (aktivni) otpor jedne faze rotorskog namotaja — na njemu struja rotora pravi toplotu (Džulove gubitke). |
| Reaktansa rasipanja po fazi rotora (na statorskoj frekvenciji) | $X_{\gamma r}$ | $0{,}256\ \mathrm{\Omega}$ | Reaktansa od onog dela rotorskog fluksa koji se "rasipa" i ne spreže se sa statorom; data je preračunata za frekvenciju $50\ \mathrm{Hz}$, tj. $X_{\gamma r} = \omega_s L_{\gamma r}$. |
| Koeficijent transformacije | $N_s : N_r = 7:4$ | $m_t = 7/4 = 1{,}75$ | Odnos efektivnih brojeva navojaka statora i rotora (faktori namotaja su isti, pa se skraćuju); igra istu ulogu kao prenosni odnos kod transformatora. |
| Linijski (međufazni) napon mreže | $U_s$ | $380\ \mathrm{V}$ | Napon između dva fazna provodnika mreže na koju je motor priključen. |
| Frekvencija mreže (statorska frekvencija) | $f_s$ | $50\ \mathrm{Hz}$ | Frekvencija napona i struja statora; određuje brzinu obrtnog magnetnog polja. |
| Brzina obrtanja rotora | $n_r$ | $950\ \mathrm{min^{-1}}$ | Stvarna mehanička brzina osovine motora. |
| Ukupni gubici na statoru | $P_{st}$ | $2{,}2\ \mathrm{kW} = 2200\ \mathrm{W}$ | Zbir gubitaka u bakru statora (toplota u statorskom namotaju) i gubitaka u gvožđu statora (histerezis + vihorne struje u limovima). |
| Gubici trenja i ventilacije | $P_{trv}$ | $2\ \mathrm{kW} = 2000\ \mathrm{W}$ | Mehanički gubici: trenje u ležajevima i snaga koju troši ventilator/otpor vazduha. |
| Sprega namotaja | Yy | — | I stator i rotor su spregnuti u zvezdu; kod zvezde je fazni napon $\sqrt{3}$ puta manji od linijskog. |

## Šta se traži i zašto

1. **Klizanje $s$** — bezdimenziona mera koliko rotor "kasni" za obrtnim poljem. Inženjera zanima jer o klizanju zavisi bukvalno sve u asinhronoj mašini: rotorska frekvencija, struja rotora, raspodela snage, moment. Doći ćemo do njega tako što prvo prepoznamo sinhronu brzinu (iz date brzine 950 min⁻¹ zaključujemo da je motor šestopolni sa $n_s = 1000\ \mathrm{min^{-1}}$), pa uporedimo $n_s$ i $n_r$.

2. **Rotorska frekvencija $f_r$** — frekvencija napona i struja koje se indukuju u rotoru. Važna je jer rotorske veličine ne osciluju na 50 Hz nego mnogo sporije; direktno je srazmerna klizanju: $f_r = s \cdot f_s$.

3. **Struja rotora $I_{rf}$** — stvarna struja u jednoj fazi rotorskog namotaja. Ona pravi gubitke u bakru rotora i (zajedno sa poljem) moment. Do nje dolazimo preko ekvivalentnog kola rotora: prvo procenimo indukovanu elektromotornu silu statora ($E_{sf} \approx U_{sf}$), preračunamo je na rotorsku stranu koeficijentom transformacije, pa podelimo impedansom rotorskog kola u kojoj figuriše čuveni fiktivni otpor $R_r/s$.

4. **Gubici u bakru rotora $P_{Cur}$** — toplota koja se razvija u rotorskim provodnicima; ograničava zagrevanje mašine. Računamo ih klasično: $3 R_r I_{rf}^2$.

5. **Snaga obrtnog polja $P_\delta$** — snaga koja preko vazdušnog zazora "preskoči" sa statora na rotor. To je centralna veličina bilansa snaga; iz nje se momenat i sve rotorske snage izvode. Dobija se elegantno: $P_\delta = P_{Cur}/s$.

6. **Proizvedena mehanička snaga (snaga konverzije) $P_c$** — deo snage obrtnog polja koji se zaista pretvorio iz električnog u mehanički oblik: $P_c = P_\delta - P_{Cur}$.

7. **Korisna mehanička snaga na vratilu $P_m$** — ono što motor stvarno isporučuje opterećenju, kada se od $P_c$ oduzmu trenje i ventilacija: $P_m = P_c - P_{trv}$.

8. **Stepen korisnog dejstva $\eta$** — odnos onoga što izađe i onoga što uđe: $\eta = P_m / P_s$, gde je $P_s = P_\delta + P_{st}$ električna snaga uzeta iz mreže. Ovo je "ocena" motora — govori koliki deo plaćene električne energije završi kao koristan mehanički rad.

**Plan rešavanja u koracima:** (1) prepoznaj sinhronu brzinu i izračunaj klizanje; (2) izračunaj rotorsku frekvenciju; (3) proceni fazni napon i EMS statora; (4) svedi EMS na rotorsku stranu; (5) izračunaj struju rotora iz ekvivalentnog kola; (6) izračunaj gubitke u bakru rotora; (7) ispiši ceo bilans snaga: $P_\delta \to P_c \to P_m$ i $P_s$; (8) izračunaj $\eta$.

## Potrebna teorija — mini-lekcije

### 1. Obrtno polje, sinhrona brzina i broj polova

Kada se trofazni statorski namotaj priključi na simetričan trofazni napon, tri fazne struje (vremenski pomerene za trećinu periode, prostorno raspoređene po obimu) stvaraju **obrtno magnetno polje** — polje konstantne amplitude koje rotira po unutrašnjosti statora. Njegova brzina, **sinhrona brzina**, zavisi samo od frekvencije mreže $f_s$ i broja pari polova mašine $p$:

$$n_s = \frac{60 \cdot f_s}{p}\ \left[\mathrm{min^{-1}}\right]$$

Intuicija: za jednu periodu napona polje "pređe" jedan par polova; što više parova polova mašina ima, polju treba više perioda za pun krug, pa se obrće sporije. Za $f_s = 50\ \mathrm{Hz}$ moguće sinhrone brzine su: $3000$ ($p=1$), $1500$ ($p=2$), $1000$ ($p=3$), $750\ \mathrm{min^{-1}}$ ($p=4$) itd. Ovo je tabela koju vredi znati napamet — po njoj iz izmerene brzine odmah prepoznajemo broj polova motora.

### 2. Klizanje

Rotor asinhronog motora u motorskom režimu se **uvek obrće malo sporije od polja** — da bi se u rotorskim provodnicima uopšte indukovao napon (i potekla struja koja pravi moment), provodnici moraju da "seku" linije polja, tj. mora postojati relativna brzina između polja i rotora. Ta relativna zaostalost, izražena u odnosu na sinhronu brzinu, zove se **klizanje**:

$$s = \frac{n_s - n_r}{n_s}\ \left[\,\right]$$

Klizanje je bezdimenzioni broj (često se izražava i u procentima). U normalnom pogonu asinhronog motora klizanje je **malo**, tipično $0{,}01$ do $0{,}06$ (1–6 %). Upravo ta činjenica nam u ovom zadatku omogućava da prepoznamo sinhronu brzinu: rotor na $950\ \mathrm{min^{-1}}$ mora "kaskati" tik ispod neke od standardnih sinhronih brzina — a jedina koja je malo iznad 950 jeste 1000 min⁻¹.

### 3. Rotorska frekvencija

Napon se u rotoru indukuje zbog relativnog kretanja polja u odnosu na rotor. Polje se okreće brzinom $n_s$, rotor brzinom $n_r$, pa polje "promiče" pored rotorskih provodnika relativnom brzinom $n_s - n_r$. Frekvencija indukovanog rotorskog napona srazmerna je toj relativnoj brzini, dok je statorska frekvencija srazmerna punoj brzini polja $n_s$. Odnos te dve frekvencije je tačno klizanje:

$$f_r = \frac{n_s - n_r}{n_s}\cdot f_s = s \cdot f_s$$

Intuicija: kad bi rotor stajao ($s=1$), video bi polje punom brzinom i rotorska frekvencija bila bi jednaka mrežnoj ($f_r = f_s$). Kad bi se rotor obrtao tačno sinhrono ($s=0$), polje bi za njega mirovalo i ništa se ne bi indukovalo ($f_r = 0$). U normalnom pogonu, sa malim klizanjem, rotorske struje osciluju vrlo sporo — svega nekoliko herca.

### 4. Sprega u zvezdu i fazni napon; aproksimacija $E_{sf} \approx U_{sf}$

Kod sprege u **zvezdu** (Y) svaki fazni namotaj je vezan između jednog faznog provodnika i zvezdišta, pa na njemu nije pun linijski napon, već fazni napon:

$$U_{sf} = \frac{U_s}{\sqrt{3}}$$

gde je $U_s$ linijski (međufazni) napon. Faktor $\sqrt{3}$ potiče iz geometrije: linijski napon je fazorska razlika dva fazna napona pomerena za $120^\circ$, a takva razlika je $\sqrt{3}$ puta duža od samog faznog fazora.

Dovedeni fazni napon $U_{sf}$ se u statorskom namotaju delom "potroši" na padove napona na otporu statora $R_s$ i rasipnoj reaktansi statora $X_{\gamma s}$, a ostatak je **indukovana elektromotorna sila (EMS)** statora $E_{sf}$ — napon koji glavni (korisni) fluks indukuje u statorskom namotaju. Pošto su ti padovi napona u normalnom pogonu mali (nekoliko procenata), a u ovom zadatku podaci o $R_s$ i $X_{\gamma s}$ **nisu ni dati**, opravdano usvajamo:

$$E_{sf} \approx U_{sf}$$

Ovo je standardna inženjerska aproksimacija kad nedostaju podaci o statorskoj impedansi (ili kad nije zadat, recimo, procentualni pad napona na statoru).

### 5. Koeficijent transformacije i EMS ukočenog rotora

Asinhroni motor sa **ukočenim (zakočenim) rotorom** ponaša se kao transformator: isti obrtni fluks prolazi i kroz statorski i kroz rotorski namotaj i u oba indukuje napon iste frekvencije. Odnos indukovanih EMS jednak je odnosu **efektivnih brojeva navojaka** (broj navojaka pomnožen navojnim sačiniocem $k_n$, koji uzima u obzir raspodeljenost i skraćenje namotaja):

$$E_{rfk} = \frac{E_{sf}}{\dfrac{N_s \cdot k_{ns}}{N_r \cdot k_{nr}}}$$

gde je $E_{rfk}$ EMS po fazi **ukočenog** rotora (indeks "k" = "kod ukočenog rotora", tj. pri $s=1$), $N_s$ i $N_r$ brojevi navojaka statora i rotora, a $k_{ns}$ i $k_{nr}$ njihovi navojni sačinioci. U ovom zadatku je rečeno da su faktori namotaja isti ($k_{ns} = k_{nr}$), pa se skraćuju i ostaje čist odnos $N_s/N_r = 7/4$. Rotor ima manje navojaka od statora, pa je rotorska EMS **manja** od statorske — delimo, ne množimo.

Zašto baš EMS *ukočenog* rotora? Zato što je to "referentna" vrednost: pri ukočenom rotoru ($s=1$) fluks prolazi pored rotorskih provodnika punom sinhronom brzinom, pa je indukovana EMS najveća i ima mrežnu frekvenciju. Pri obrtanju sa klizanjem $s$ i amplituda i frekvencija rotorske EMS smanjuju se $s$ puta: EMS obrtnog rotora je $s \cdot E_{rfk}$, frekvencije $s\cdot f_s$.

### 6. Ekvivalentno kolo rotora i fiktivni otpor $R_r/s$ (ključno izvođenje)

Sada najvažniji teorijski korak celog zadatka. Rotorsko kolo pri obrtanju sa klizanjem $s$ je prosto redno R–X kolo napajano rotorskom EMS. Ali pažnja: pri klizanju $s$ rotorske veličine imaju frekvenciju $f_r = s f_s$, pa je:

- EMS rotora: $s \cdot E_{rfk}$ (smanjena $s$ puta u odnosu na ukočeni rotor),
- otpor rotora: $R_r$ (otpor ne zavisi od frekvencije),
- reaktansa rotora: $s \cdot X_{\gamma r}$ (reaktansa je $2\pi f L$, pa je na frekvenciji $s f_s$ ona $s$ puta manja od date vrednosti $X_{\gamma r}$, koja je izračunata na statorskoj frekvenciji).

Efektivna vrednost struje rotora je tada:

$$I_{rf} = \frac{s \cdot E_{rfk}}{\sqrt{R_r^2 + \left(s \cdot X_{\gamma r}\right)^2}}$$

Podelimo i brojilac i imenilac sa $s$ (time se vrednost razlomka ne menja; deljenje pod korenom znači deljenje sa $s^2$):

$$I_{rf} = \frac{E_{rfk}}{\sqrt{\dfrac{R_r^2 + s^2 X_{\gamma r}^2}{s^2}}} = \frac{E_{rfk}}{\sqrt{\left(\dfrac{R_r}{s}\right)^2 + X_{\gamma r}^2}}$$

Ovo je matematički identična, ali fizički vrlo rečita forma: struja obrtnog rotora ista je kao struja **fiktivnog ukočenog rotora** koji ima punu EMS $E_{rfk}$, punu reaktansu $X_{\gamma r}$ (obe na statorskoj frekvenciji!) — ali uvećani, fiktivni otpor $R_r/s$. Time smo obrtni rotor zamenili mirnim kolom na mrežnoj frekvenciji, što je osnova celog ekvivalentnog kola asinhrone mašine. Fiktivni otpor $R_r/s$ nije izmišljotina bez pokrića: snaga koja se na njemu "razvija" ima duboko fizičko značenje, o čemu govori sledeća lekcija.

### 7. Bilans snaga asinhronog motora

Put snage kroz motor, od utičnice do vratila, izgleda ovako:

$$P_s \;\xrightarrow{\ -P_{st}\ }\; P_\delta \;\xrightarrow{\ -P_{Cur}\ }\; P_c \;\xrightarrow{\ -P_{trv}\ }\; P_m$$

Redom:

- $P_s$ — **primljena (ulazna) električna snaga**: aktivna snaga koju motor uzima iz mreže.
- $P_{st}$ — **ukupni statorski gubici**: gubici u bakru statora + gubici u gvožđu statora. (Gubici u gvožđu rotora se zanemaruju jer je rotorska frekvencija mala — svega par herca — a gubici u gvožđu rastu sa frekvencijom.)
- $P_\delta$ — **snaga obrtnog polja** (snaga vazdušnog zazora): ono što od ulazne snage preostane posle statorskih gubitaka prelazi preko vazdušnog zazora, posredstvom obrtnog polja, na rotor: $P_\delta = P_s - P_{st}$.
- $P_{Cur}$ — **gubici u bakru rotora**: $P_{Cur} = 3 R_r I_{rf}^2$ (tri faze, svaka sa otporom $R_r$ i strujom $I_{rf}$).
- $P_c$ — **proizvedena mehanička snaga (snaga konverzije)**: deo snage polja koji se zaista pretvorio u mehaničku snagu: $P_c = P_\delta - P_{Cur}$.
- $P_m$ — **korisna mehanička snaga na vratilu**: $P_m = P_c - P_{trv}$.

**Zlatna veza sa klizanjem.** U ekvivalentnom kolu rotora sva snaga koja pređe na rotor razvija se na fiktivnom otporu $R_r/s$ (reaktansa ne troši aktivnu snagu):

$$P_\delta = 3 \cdot \frac{R_r}{s} \cdot I_{rf}^2$$

Ako ovaj izraz uporedimo sa $P_{Cur} = 3 R_r I_{rf}^2$, vidimo da se razlikuju tačno za faktor $1/s$:

$$P_{Cur} = s \cdot P_\delta, \qquad P_c = P_\delta - P_{Cur} = (1-s)\cdot P_\delta$$

Rečima: **od snage koja pređe na rotor, deo $s$ ode u toplotu rotorskog bakra, a deo $(1-s)$ postane mehanička snaga.** Zato je malo klizanje uslov dobrog stepena iskorišćenja — pri $s = 0{,}05$ rotor "baca" samo 5 % primljene snage u toplotu.

- $\eta$ — **stepen korisnog dejstva**: odnos izlaza i ulaza, $\eta = P_m / P_s$. Kod dobrih motora ovog reda snage iznosi 0,85–0,95.

## Rešenje, korak po korak

### Korak 1: Prepoznavanje sinhrone brzine i broja polova

**Zašto ovaj korak:** Klizanje ne možemo izračunati dok ne znamo sinhronu brzinu $n_s$, a ona nije direktno zadata — moramo je prepoznati iz date brzine obrtanja.

Sinhrona brzina zavisi od broja pari polova:

$$n_s = \frac{60 \cdot f_s}{p}$$

- $n_s$ — sinhrona brzina (brzina obrtnog polja) u $\mathrm{min^{-1}}$,
- $f_s = 50\ \mathrm{Hz}$ — frekvencija mreže,
- $p$ — broj pari polova (ceo broj: 1, 2, 3, …).

Moguće vrednosti za 50 Hz: $3000,\ 1500,\ 1000,\ 750\ \mathrm{min^{-1}}$ za $p = 1, 2, 3, 4$. Znamo da je u normalnom pogonu klizanje asinhronog motora **mala** veličina (nekoliko procenata), tj. rotor se obrće tik ispod sinhrone brzine. Data brzina $n_r = 950\ \mathrm{min^{-1}}$ je malo ispod $1000\ \mathrm{min^{-1}}$ — dakle:

$$n_s = \frac{60 \cdot 50}{3} = 1000\ \mathrm{min^{-1}}$$

**Šta smo dobili:** Motor je šestopolni ($p = 3$ para polova, tj. $2p = 6$ polova) sa sinhronom brzinom $1000\ \mathrm{min^{-1}}$. Da smo probali $n_s = 1500$, klizanje bi ispalo $s = (1500-950)/1500 \approx 0{,}37$ — potpuno nerealno za normalan pogon; $n_s = 750$ je nemoguće jer bi rotor bio brži od polja (to bi bio generatorski režim, a zadatak kaže "motor").

### Korak 2: Klizanje

**Zašto ovaj korak:** Klizanje je prva tražena veličina i ključ za sve dalje — od njega zavise rotorska frekvencija, struja rotora i cela raspodela snaga.

$$s = \frac{n_s - n_r}{n_s}$$

- $n_r = 950\ \mathrm{min^{-1}}$ — stvarna brzina rotora.

Uvrštavamo:

$$s = \frac{1000 - 950}{1000} = \frac{50}{1000} = 0{,}05\ \left[\,\right]$$

**Šta smo dobili:** Klizanje je $0{,}05$, tj. 5 % — rotor kaska za poljem za 50 obrtaja u minuti. To je sasvim uobičajena vrednost za asinhroni motor pod opterećenjem, što potvrđuje da smo dobro pogodili sinhronu brzinu.

### Korak 3: Rotorska frekvencija

**Zašto ovaj korak:** Tražena je frekvencija rotorskih indukovanih napona i struja; ona pokazuje koliko se sporo menjaju rotorske veličine i opravdava zanemarivanje gubitaka u gvožđu rotora.

Frekvencija rotorskog indukovanog napona i struja srazmerna je klizanju (mini-lekcija 3):

$$f_r = s \cdot f_s = 0{,}05 \cdot 50\ \mathrm{Hz} = 2{,}5\ \mathrm{Hz}$$

**Šta smo dobili:** Rotorske struje osciluju sa svega $2{,}5\ \mathrm{Hz}$ — dvadeset puta sporije od mrežnih. Zato su gubici u gvožđu rotora zanemarljivi i zato ih bilans snaga ne sadrži.

### Korak 4: Fazni napon statora i procena statorske EMS

**Zašto ovaj korak:** Da bismo došli do struje rotora, treba nam rotorska EMS; do nje dolazimo preko statorske EMS, koju procenjujemo iz napona mreže.

Stator je spregnut u zvezdu, pa je na svakom faznom namotaju fazni napon (mini-lekcija 4):

$$U_{sf} = \frac{U_s}{\sqrt{3}} = \frac{380\ \mathrm{V}}{\sqrt{3}} \approx 220\ \mathrm{V}$$

Podaci o otporu i rasipnoj reaktansi statora nisu dati (niti je dat, recimo, procentualni pad napona na statoru), pa usvajamo da je indukovana EMS po fazi statora približno jednaka dovedenom faznom naponu:

$$E_{sf} \approx U_{sf} \approx 220\ \mathrm{V}$$

**Šta smo dobili:** Statorska EMS je oko $220\ \mathrm{V}$ po fazi. Ova aproksimacija greši za onoliko koliki je pad napona na statorskoj impedansi — u normalnom pogonu svega nekoliko procenata, što je za ovaj bilans sasvim prihvatljivo.

### Korak 5: EMS ukočenog rotora

**Zašto ovaj korak:** Struju rotora računamo u rotorskom kolu, pa statorsku EMS moramo "prevesti" na rotorsku stranu — kao kod transformatora, preko odnosa efektivnih brojeva navojaka.

Iz mini-lekcije 5, EMS po fazi ukočenog rotora je:

$$E_{rfk} = \frac{E_{sf}}{\dfrac{N_s \cdot k_{ns}}{N_r \cdot k_{nr}}}$$

Pošto su navojni sačinioci isti ($k_{ns} = k_{nr}$), oni se u razlomku skraćuju i ostaje samo odnos brojeva navojaka $N_s/N_r = 7/4$:

$$E_{rfk} = \frac{220}{\dfrac{7}{4}} = 220 \cdot \frac{4}{7} = \frac{880}{7} = 125{,}7142\ \mathrm{V}$$

(Deljenje razlomkom $7/4$ je isto što i množenje njegovom recipročnom vrednošću $4/7$ — zato $220 \cdot 4/7$.)

**Šta smo dobili:** Pri ukočenom rotoru u svakoj fazi rotora indukovalo bi se oko $125{,}7\ \mathrm{V}$. Manje je od statorskih 220 V jer rotor ima manje navojaka (4 naspram 7) — logično, kao sekundar transformatora za spuštanje napona.

### Korak 6: Struja rotora

**Zašto ovaj korak:** Struja rotora je tražena veličina i direktno određuje gubitke u bakru rotora i snagu obrtnog polja.

Na osnovu ekvivalencije obrtnog rotora fiktivnim ukočenim rotorom (izvedene u mini-lekciji 6), struja rotora se računa iz kola sa punom EMS $E_{rfk}$, punom reaktansom $X_{\gamma r}$ i fiktivnim otporom $R_r/s$:

$$I_{rf} = \frac{E_{rfk}}{\sqrt{\left(\dfrac{R_r}{s}\right)^2 + X_{\gamma r}^2}}$$

Prvo izračunajmo fiktivni otpor:

$$\frac{R_r}{s} = \frac{0{,}016}{0{,}05} = 0{,}32\ \mathrm{\Omega}$$

Zatim impedansu (moduo) rotorskog kola:

$$\sqrt{\left(\frac{R_r}{s}\right)^2 + X_{\gamma r}^2} = \sqrt{0{,}32^2 + 0{,}256^2} = \sqrt{0{,}1024 + 0{,}065536} = \sqrt{0{,}167936} = 0{,}4098\ \mathrm{\Omega}$$

I na kraju struju:

$$I_{rf} = \frac{125{,}7142}{0{,}4098} = 306{,}7696\ \mathrm{A} \approx 306{,}77\ \mathrm{A}$$

**Šta smo dobili:** Struja rotora je oko $307\ \mathrm{A}$ — deluje ogromno, ali je normalno za rotorski namotaj: rotor ima malo navojaka i vrlo mali otpor ($0{,}016\ \mathrm{\Omega}$), pa radi na principu "mali napon, velika struja" (kao sekundar transformatora sa malo navojaka). Primetimo i da fiktivni otpor $0{,}32\ \mathrm{\Omega}$ dominira nad reaktansom $0{,}256\ \mathrm{\Omega}$ — pri malom klizanju rotorsko kolo je pretežno "omsko", što znači povoljan (skoro jedinični) faktor snage rotorske struje.

### Korak 7: Gubici u bakru rotora

**Zašto ovaj korak:** Tražena veličina; ujedno nam preko relacije $P_\delta = P_{Cur}/s$ otvara vrata ka celom bilansu snaga.

Džulovi (omski) gubici u sve tri faze rotora:

$$P_{Cur} = 3 \cdot R_r \cdot I_{rf}^2$$

- faktor $3$ — tri faze rotorskog namotaja, u svakoj isti otpor i ista efektivna struja.

Uvrštavamo:

$$P_{Cur} = 3 \cdot 0{,}016 \cdot 306{,}7696^2 = 3 \cdot 0{,}016 \cdot 94107{,}6 = 4517{,}1665\ \mathrm{W} \approx 4{,}52\ \mathrm{kW}$$

**Šta smo dobili:** U rotorskom bakru se u toplotu pretvara oko $4{,}5\ \mathrm{kW}$. To je više nego svi statorski gubici (2,2 kW) — pri klizanju od 5 % rotorski bakarni gubici su ozbiljna stavka, jer su po definiciji tačno 5 % snage obrtnog polja.

### Korak 8: Snaga obrtnog polja

**Zašto ovaj korak:** Snaga obrtnog polja je "kičma" bilansa — iz nje ćemo izvući i snagu konverzije i primljenu snagu.

Snaga obrtnog polja, tj. snaga koja prelazi sa statora na rotor, u ekvivalentnom kolu rotora je Džulova snaga na fiktivnom otporu $R_r/s$ (mini-lekcija 7):

$$P_\delta = 3 \cdot \frac{R_r}{s} \cdot I_{rf}^2$$

Uporedimo li ovo sa izrazom za $P_{Cur} = 3 R_r I_{rf}^2$ iz prethodnog koraka, vidimo da su svi činioci isti osim što je $R_r$ zamenjeno sa $R_r/s$ — dakle ceo izraz je $1/s$ puta veći:

$$P_\delta = \frac{P_{Cur}}{s} = \frac{4517{,}1665}{0{,}05} = 90343{,}3312\ \mathrm{W} \approx 90{,}34\ \mathrm{kW}$$

**Šta smo dobili:** Preko vazdušnog zazora na rotor prelazi oko $90{,}3\ \mathrm{kW}$. Deljenje sa $s = 0{,}05$ je isto što i množenje sa 20 — i zaista, gubici u rotorskom bakru su tačno dvadeseti deo (5 %) snage polja, u skladu sa relacijom $P_{Cur} = s \cdot P_\delta$.

### Korak 9: Proizvedena mehanička snaga (snaga konverzije)

**Zašto ovaj korak:** Tražena veličina — koliko se električne snage stvarno pretvorilo u mehaničku.

Proizvedena mehanička snaga (snaga elektromagnetne konverzije) manja je od snage obrtnog polja za iznos gubitaka u bakru rotora:

$$P_c = P_\delta - P_{Cur} = 90343{,}3312 - 4517{,}1665 = 85826{,}1647\ \mathrm{W} \approx 85{,}83\ \mathrm{kW}$$

**Šta smo dobili:** Oko $85{,}8\ \mathrm{kW}$ mehaničke snage nastaje konverzijom. Kontrola preko klizanja: $P_c = (1-s) P_\delta = 0{,}95 \cdot 90343{,}3 \approx 85826\ \mathrm{W}$ — poklapa se, kako i mora.

### Korak 10: Korisna mehanička snaga na vratilu

**Zašto ovaj korak:** Tražena veličina — ono što opterećenje zaista dobija.

Od proizvedene mehaničke snage deo troše trenje u ležajevima i ventilacija; ostatak izlazi na vratilo:

$$P_m = P_c - P_{trv} = 85826{,}1647 - 2000 = 83826{,}1647\ \mathrm{W} \approx 83{,}83\ \mathrm{kW}$$

**Šta smo dobili:** Motor na vratilu daje oko $83{,}8\ \mathrm{kW}$ — ovo je, dakle, motor klase snage ~80–90 kW koji u ovom pogonskom stanju vuče pun teret.

### Korak 11: Primljena električna snaga

**Zašto ovaj korak:** Za stepen korisnog dejstva treba nam ulazna snaga, a nju do sada nismo imali — rekonstruišemo je iz snage polja i statorskih gubitaka.

Dati ukupni gubici na statoru $P_{st}$ obuhvataju gubitke u bakru statora i gubitke u gvožđu statora. Primljena električna (aktivna) snaga koju motor uzima iz mreže veća je od snage predate rotoru upravo za te statorske gubitke:

$$P_s = P_\delta + P_{st} = 90343{,}3312 + 2200 = 92543{,}3312\ \mathrm{W} \approx 92{,}54\ \mathrm{kW}$$

**Šta smo dobili:** Motor iz mreže uzima oko $92{,}5\ \mathrm{kW}$ aktivne snage. Redosled u bilansu je ispoštovan: $P_s > P_\delta > P_c > P_m$, svaka strelica "naniže" odgovara jednoj vrsti gubitaka.

### Korak 12: Stepen korisnog dejstva

**Zašto ovaj korak:** Završna tražena veličina — ukupna "ocena" energetske efikasnosti motora u ovom pogonskom stanju.

$$\eta = \frac{P_m}{P_s} = \frac{83826{,}1647}{92543{,}3312} = 0{,}9058\ \left[\,\right]$$

**Šta smo dobili:** Stepen korisnog dejstva je $\eta \approx 0{,}906$, tj. oko $90{,}6\ \%$. Za asinhroni motor snage ~84 kW to je sasvim realna, dobra vrednost — motori ove klase tipično imaju $\eta$ između 0,90 i 0,95.

## Česte greške i zamke

1. **Linijski umesto fazni napon.** Motor je u spoju Yy — u proračun EMS ulazi fazni napon $380/\sqrt{3} \approx 220\ \mathrm{V}$, ne $380\ \mathrm{V}$. Ko uvrsti 380 V, dobije $\sqrt{3}$ puta veću struju rotora i tri puta veće sve snage.

2. **Pogrešan smer koeficijenta transformacije.** $E_{rfk}$ se dobija **deljenjem** statorske EMS sa $N_s/N_r = 7/4$ (rotor ima manje navojaka, pa mu je EMS manja). Množenje umesto deljenja daje $E_{rfk} = 385\ \mathrm{V}$ — odmah sumnjivo, jer rotorska EMS ispada veća od statorske iako rotor ima manje navojaka.

3. **Mešanje dve ekvivalentne forme rotorskog kola.** Ispravno je ili $\dfrac{s E_{rfk}}{\sqrt{R_r^2 + (sX_{\gamma r})^2}}$ (stvarno rotorsko kolo na frekvenciji $f_r$) ili $\dfrac{E_{rfk}}{\sqrt{(R_r/s)^2 + X_{\gamma r}^2}}$ (fiktivni ukočeni rotor). Česta greška je hibrid: puna EMS sa reaktansom $sX_{\gamma r}$, ili $R_r/s$ zajedno sa $sX_{\gamma r}$ — obe kombinacije su pogrešne.

4. **Zaboravljeno deljenje otpora klizanjem.** Ko izračuna $I_{rf} = E_{rfk}/\sqrt{R_r^2 + X_{\gamma r}^2}$ (bez $s$), zapravo je izračunao struju ukočenog rotora (polaznu struju pri punoj EMS), a ne struju u datom pogonskom stanju.

5. **Pogrešno mesto oduzimanja gubitaka trenja.** Gubici trenja i ventilacije oduzimaju se od **snage konverzije** $P_c$ (oni su mehanički gubici, nastaju posle konverzije), a ne od snage obrtnog polja niti od ulazne snage direktno. Slično, statorski gubici se **dodaju** na $P_\delta$ da bi se dobilo $P_s$ — ne oduzimaju.

6. **Klizanje u procentima umesto relativnih jedinica.** U formulama $R_r/s$, $f_r = s f_s$, $P_\delta = P_{Cur}/s$ mora se koristiti $s = 0{,}05$, a ne $s = 5$. Sa $s=5$ fiktivni otpor bi ispao 156 puta manji, a snage besmislene.

## Rezime rezultata

| Tražena veličina | Oznaka | Rezultat |
|---|---|---|
| Klizanje | $s$ | $0{,}05$ (5 %) |
| Rotorska frekvencija | $f_r$ | $2{,}5\ \mathrm{Hz}$ |
| Struja rotora (po fazi) | $I_{rf}$ | $306{,}77\ \mathrm{A}$ |
| Gubici u bakru rotora | $P_{Cur}$ | $4517{,}17\ \mathrm{W} \approx 4{,}52\ \mathrm{kW}$ |
| Snaga obrtnog polja | $P_\delta$ | $90343{,}33\ \mathrm{W} \approx 90{,}34\ \mathrm{kW}$ |
| Proizvedena mehanička snaga (snaga konverzije) | $P_c$ | $85826{,}16\ \mathrm{W} \approx 85{,}83\ \mathrm{kW}$ |
| Korisna mehanička snaga na vratilu | $P_m$ | $83826{,}16\ \mathrm{W} \approx 83{,}83\ \mathrm{kW}$ |
| Primljena električna snaga | $P_s$ | $92543{,}33\ \mathrm{W} \approx 92{,}54\ \mathrm{kW}$ |
| Stepen korisnog dejstva | $\eta$ | $0{,}9058 \approx 90{,}6\ \%$ |

## Provera smisla

**1. Zlatna relacija klizanja.** Teorija kaže $P_{Cur} = s \cdot P_\delta$ i $P_c = (1-s)\cdot P_\delta$. Provera:

$$s \cdot P_\delta = 0{,}05 \cdot 90343{,}33 = 4517{,}17\ \mathrm{W} = P_{Cur} \checkmark$$
$$(1-s)\cdot P_\delta = 0{,}95 \cdot 90343{,}33 = 85826{,}16\ \mathrm{W} = P_c \checkmark$$

**2. Ukupan bilans gubitaka.** Razlika ulazne i izlazne snage mora biti tačno zbir svih gubitaka:

$$P_s - P_m = 92543{,}33 - 83826{,}16 = 8717{,}17\ \mathrm{W}$$
$$P_{st} + P_{Cur} + P_{trv} = 2200 + 4517{,}17 + 2000 = 8717{,}17\ \mathrm{W} \checkmark$$

Ništa se "nije izgubilo u prevodu" — bilans je zatvoren.

**3. Poređenje sa graničnom vrednošću.** Sam rotor, po zlatnoj relaciji, ne može biti efikasniji od $(1-s) = 0{,}95$; stvarni $\eta = 0{,}906$ je ispod te granice (dodatno ga obaraju statorski i mehanički gubici) ali blizu nje — tačno onako kako treba da bude kod zdravog motora sa malim klizanjem.

**4. Dimenziona provera struje.** $\left[\mathrm{V}\right]/\left[\mathrm{\Omega}\right] = \left[\mathrm{A}\right]$: EMS u voltima podeljena impedansom u omima zaista daje ampere; a $\left[\mathrm{\Omega}\right]\cdot\left[\mathrm{A^2}\right] = \left[\mathrm{W}\right]$ potvrđuje da $3R_rI_{rf}^2$ daje vate.
