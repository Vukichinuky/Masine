# Teorijske osnove — sve što ti treba da pratiš zadatke 50–59

Ovo poglavlje je pisano za čitaoca koji o asinhronim mašinama ne zna ništa. Cilj mu je da posle
čitanja možeš da otvoriš bilo koji od zadataka 50–59 i da ti nijedna formula ne "padne s neba":
svaka formula koja se u zadacima koristi ovde je uvedena, izvedena bar u glavnim crtama i
objašnjena intuitivno. Čitaj redom — sekcije se nadovezuju jedna na drugu, kao stepenice.
Pri kraju poglavlja nalaze se **čeklista najčešćih grešaka** za celu oblast (pregledaj je pre
svakog rešavanja) i **Rečnik oznaka**: tabela svih simbola koji se javljaju u zadacima, da uvek
imaš gde da proveriš "šta je ovo slovo".

Kratka mapa: zadaci 50–52 se bave upravljanjem brzinom promenom frekvencije uz uslov
$U/f = \mathrm{const}$ i Klosovom formulom; zadaci 53 i 54 Klosovom formulom i rotorskim strujama;
zadatak 55 strujno napajanim motorom i maksimalnim polaznim momentom; zadatak 56 protivstrujnim
kočenjem; zadatak 57 radom trofaznog motora kad otpadne jedna faza (što se svodi na teoriju
monofaznog motora); zadatak 58 monofaznim kondenzatorskim motorom; zadatak 59 dinamičkim
(jednosmernim) kočenjem. Sve te teme su pokrivene u nastavku.

---

## 1. Šta je asinhroni motor i kako je građen

**Definicija.** Asinhroni (indukcioni) motor je mašina naizmenične struje kod koje se energija na
rotor (obrtni deo) ne dovodi žicama, nego se u rotoru **indukuje** — kao u transformatoru. Zato mu
je drugo ime *indukcioni motor*. Najkraća moguća slika: **asinhroni motor je transformator čijem je
sekundaru dozvoljeno da se vrti**. Primar je statorski namotaj, sekundar je rotorski namotaj, a
"prenos energije kroz vazduh" ide preko zajedničkog magnetnog polja.

Motor ima tri glavna dela:

1. **Stator** — nepokretni deo. To je šuplji valjak složen od tankih međusobno izolovanih
   gvozdenih limova (limovi smanjuju gubitke usled vrtložnih struja). Po unutrašnjem obodu statora
   su žlebovi, a u žlebovima leže **tri fazna namotaja**, prostorno pomerena za $120^{\circ}$ jedan
   od drugog. Ta tri namotaja se vezuju u zvezdu (Y) ili trougao (Δ) i priključuju na trofaznu
   mrežu. U zadacima ćeš sretati oznaku $q_s$ — **broj faza statora** — koja je za trofazni motor
   uvek $q_s = 3$.
2. **Rotor** — pokretni deo, takođe od limova, sa žlebovima po spoljnom obodu. Postoje dve izvedbe:
   - **Kavezni (kratkospojeni) rotor:** u žlebove su uliveni goli aluminijumski ili bakarni
     štapovi, koji su na oba čela rotora kratko spojeni prstenovima. Kad bi se izvadio iz gvožđa,
     taj sklop bi ličio na kavez za veverice — otuda ime. Kavez nema izvode: rotorskom kolu se
     spolja ne može ništa dodati. Ovakvi su motori u zadacima 50–55 ("motor sa kaveznim/kratkospojenim
     rotorom") — jeftini su, robusni i najrasprostranjeniji.
   - **Namotani rotor (motor sa kliznim prstenovima):** u žlebovima rotora je pravi trofazni
     namotaj, čiji su krajevi izvedeni na tri klizna prstena na vratilu. Preko četkica koje klize po
     prstenovima rotorskom kolu se spolja može **dodati otpornost** — to je ključna mogućnost koju
     koristi zadatak 56 (dodatni otpor za ograničenje struje pri kočenju). Kod namotanog rotora ima
     smisla govoriti i o **prenosnom odnosu** stator/rotor $m$ (odnos broja navojaka), kao kod
     transformatora.
3. **Vazdušni zazor** — uzak vazdušni procep između statora i rotora (deo milimetra do par
   milimetara). Kroz njega magnetno polje "preskače" sa statora na rotor; kroz njega, računski
   gledano, prelazi i sva snaga koja se predaje rotoru (to će u sekciji 5 biti *snaga obrtnog polja*
   $P_{\mathrm{ob}}$).

**Mini-lekcija: fazni i linijski napon, zvezda i trougao.** Pošto smo upravo pomenuli sprege Y i Δ,
odmah da raščistimo pojmove koji će nam trebati u svakom zadatku sa naponima:

- **Linijski (međufazni) napon** $U_s$ je napon *između dva fazna provodnika* trofazne mreže — to je
  onaj broj koji obično piše na pločici i u postavci zadatka ($380\ \mathrm{V}$, $220\ \mathrm{V}$...).
- **Fazni napon** $U_{sf}$ je napon *na jednom faznom namotaju* motora. Koliki je, zavisi od sprege:
  - **Zvezda (Y):** po jedan kraj sva tri namotaja spojen je u zajedničku tačku (zvezdište), a drugi
    krajevi idu na fazne provodnike. Svaki namotaj je tako između jednog faznog provodnika i
    zvezdišta, pa na njemu nije ceo linijski napon, nego $U_{sf} = U_s/\sqrt{3}$. Odakle $\sqrt{3}$:
    linijski napon je (fazorska) *razlika* dva fazna napona koji su vremenski pomereni za
    $120^{\circ}$; dva jednaka fazora pod uglom od $120^{\circ}$ daju razliku dužine
    $\sqrt{3}$ puta veće od svakog ponaosob (nacrtaj dva jedinična vektora pod $120^{\circ}$ —
    rastojanje njihovih vrhova je $\sqrt{3}$).
  - **Trougao (Δ):** namotaji su vezani "u krug", svaki direktno između dva fazna provodnika, pa je
    $U_{sf} = U_s$.
- **Upozorenje koje sprečava klasičnu grešku:** u sve formule za snagu i moment (sekcije 5 i 6)
  ulazi **fazni** napon. U zadatku 51 motor je u sprezi Δ, pa je $U_{sf} = U_s = 220\ \mathrm{V}$;
  u zadatku 52 motor je u sprezi Y na $380\ \mathrm{V}$, pa je
  $U_{sf} = 380/\sqrt{3} \approx 220\ \mathrm{V}$. Isti broj, dva različita razloga!

**Intuicija za ceo motor u jednoj rečenici:** statorske struje naprave magnetno polje koje kruži po
obodu mašine; to polje, prolazeći pored rotorskih provodnika, u njima indukuje struje; na provodnik
sa strujom u magnetnom polju deluje sila — i rotor krene da se vrti *za poljem*, kao komad metala
koji juri magnet koji mu stalno izmiče.

---

## 2. Obrtno magnetno polje i sinhrona brzina

### 2.1. Kako nastaje obrtno polje

Svaki od tri statorska namotaja, kad kroz njega protiče struja, pravi magnetno polje duž svoje ose.
Namotaji su **prostorno** pomereni za $120^{\circ}$, a trofazne struje kroz njih su **vremenski**
pomerene za $120^{\circ}$ (trećinu periode). Rezultat sabiranja ta tri pulsirajuća polja je jedno
polje **konstantne jačine koje rotira** po obodu mašine — Teslino obrtno polje. Analogija: tri
osobe stoje u krug oko klackalice i guraju je naizmenično, svaka malo kasnije od prethodne — iako
svaka gura samo "svoj pravac", klackalica se ravnomerno okreće u krug.

### 2.2. Sinhrona brzina

**Definicija.** Brzina kojom obrtno polje kruži zove se **sinhrona brzina** $n_s$.

**Formula i poreklo.** Za jednu periodu napona polje pređe put od **jednog para polova**. Zašto
baš toliko: posle tačno jedne periode sve tri struje se vrate na iste vrednosti sa kojima su počele,
pa slika polja mora izgledati identično kao na početku periode — a najmanji pomeraj po obodu koji
šaru polova N–S–N–S... preslikava u samu sebe je upravo jedan korak para polova (sa jednog severnog
pola na sledeći severni). Ako
namotaj pravi $p$ pari polova po obodu (veličina $p$ se zove **broj pari polova** i određena je
načinom motanja namotaja), onda polje za jednu periodu pređe $1/p$ punog kruga, pa za jedan pun
krug treba $p$ perioda. U sekundi ima $f_s$ perioda ($f_s$ je frekvencija napajanja statora), pa
polje napravi $f_s/p$ obrtaja u sekundi, odnosno $60 f_s/p$ obrtaja u minuti:

$$n_s = \frac{60 \cdot f_s}{p}\ \left[\mathrm{o/min}\right]$$

gde je:
- $n_s$ — sinhrona brzina obrtnog polja u obrtajima u minuti (u zbirci se piše i
  $\mathrm{o/min}$ i $\mathrm{min^{-1}}$ — to je ista jedinica),
- $f_s$ — frekvencija statorskog napona u $\mathrm{Hz}$,
- $p$ — broj pari polova (ceo broj: $1, 2, 3, \dots$).

Za mrežu od $f_s = 50\ \mathrm{Hz}$ sinhrona brzina može da bude samo jedna od "lestvice" vrednosti:

| $p$ | $n_s = 60 f_s / p$ |
|---|---|
| 1 | $3000\ \mathrm{o/min}$ |
| 2 | $1500\ \mathrm{o/min}$ |
| 3 | $1000\ \mathrm{o/min}$ |
| 4 | $750\ \mathrm{o/min}$ |

Ovo je koristan "detektor": ako u zadatku piše da motor ima nazivnu brzinu $1440\ \mathrm{o/min}$,
odmah znaš da mu je sinhrona brzina $1500\ \mathrm{o/min}$ (prva vrednost sa lestvice iznad nazivne)
i da ima $p = 2$ para polova. Zašto baš *prva iznad*, i to za malo — videćeš u sekciji 3: motor u
normalnom radu uvek zaostaje za poljem, ali svega nekoliko procenata, pa nazivna brzina pada tik
ispod sinhrone. Šestopolni motor ($p = 3$, jer 6 polova čini 3 para) na
$50\ \mathrm{Hz}$ ima $n_s = 1000\ \mathrm{o/min}$ — to koristi zadatak 57.

### 2.3. Ugaone brzine — dve različite "omege"

U zadacima se javljaju i ugaone brzine, i tu treba pažnja jer postoje **dve** srodne veličine:

- **Električna ugaona učestanost** statorskih veličina: $\omega_s = 2\pi f_s$ u
  $\mathrm{rad/s}$ (električnih radijana u sekundi). Ona se koristi kad se iz induktivnosti računa
  reaktansa: $X = \omega_s L = 2\pi f_s L$.
- **Mehanička sinhrona ugaona brzina** obrtnog polja:

$$\Omega_s = \frac{2\pi \cdot n_s}{60} = \frac{\pi \cdot n_s}{30} = \frac{2\pi \cdot f_s}{p}\ \left[\mathrm{rad/s}\right]$$

  Ona se koristi kad se iz snage računa moment ($M = P/\Omega$). Prva dva oblika su samo
  pretvaranje obrtaja u minuti u radijane u sekundi (jedan obrtaj je $2\pi$ radijana, minut je 60
  sekundi); treći oblik sledi uvrštavanjem $n_s = 60 f_s/p$.

> **Napomena o zapisu u zbirci:** originalna zbirka na nekoliko mesta i mehaničku sinhronu brzinu
> označava sa $\omega_s$ (npr. u izrazu za moment), a negde sa $\Omega_s$. U ovom priručniku
> dosledno koristimo $\Omega_s$ za mehaničku, a $\omega_s = 2\pi f_s$ za električnu. Kad je
> $p = 1$, one su brojno jednake — zato mešanje često prođe nekažnjeno, ali za $p \ne 1$ razlika
> je faktor $p$ i greška je ozbiljna.

Analogno, mehanička ugaona brzina **rotora** je $\Omega = 2\pi n / 60$, gde je $n$ brzina rotora u
$\mathrm{o/min}$; za nazivnu brzinu pišemo $\Omega_n = 2\pi n_n/60$.

---

## 3. Klizanje i rotorska frekvencija

### 3.1. Zašto rotor nikad ne stigne polje

Zamisli da se rotor vrti **tačno** sinhronom brzinom. Tada bi rotorski provodnici mirovali u odnosu
na polje, fluks kroz rotorske konture se ne bi menjao, pa ne bi bilo ni indukovanih napona, ni
rotorskih struja, ni sile — **moment bi bio nula**. Motor koji treba da savlada bilo kakvo trenje
ili teret mora zato da se vrti **malo sporije** od polja: baš to zaostajanje omogućava indukciju.
Otuda ime *asinhroni*: rotor nikada nije u sinhronizmu sa poljem dok radi kao motor.

### 3.2. Klizanje

**Definicija.** **Klizanje** $s$ je relativno zaostajanje rotora za poljem, svedeno na sinhronu
brzinu:

$$s = \frac{n_s - n}{n_s}$$

gde je $n$ brzina obrtanja rotora. Klizanje je čist broj (često se izražava u procentima).
Iz definicije odmah sledi izraz za brzinu rotora, koji se u zadacima stalno koristi:

$$n = (1-s)\cdot n_s$$

Razlika u brojiocu, $n_s - n$, ima i svoje ime — **apsolutno klizanje** (u zadacima označavano sa
$\Delta n$ ili $n_k$):

$$\Delta n = n_s - n = s\cdot n_s\ \left[\mathrm{o/min}\right]$$

Ova veličina je "zvezda" zadataka 51 i 52, jer se pokazuje (sekcija 11.3) da pri upravljanju
$U/f = \mathrm{const}$ ona ostaje ista na svim frekvencijama za isti teret.

**Brojčani primer.** Motor sa $n_s = 1500\ \mathrm{o/min}$ i nazivnom brzinom
$n_n = 1440\ \mathrm{o/min}$ ima nazivno klizanje

$$s_n = \frac{1500 - 1440}{1500} = 0{,}04 = 4\ \%$$

i apsolutno klizanje $\Delta n = 0{,}04 \cdot 1500 = 60\ \mathrm{o/min}$. Tipične nazivne vrednosti
klizanja su male: od $1\ \%$ do $6\ \%$. Zato je brzina motora u normalnom radu uvek "malo ispod" sinhrone.

Karakteristične vrednosti klizanja (zapamti ih, one kodiraju režim rada — detaljno u sekciji 10):

- $s = 0$: rotor se vrti sinhrono ($n = n_s$) — idealni prazan hod, moment nula;
- $s = 1$: rotor stoji ($n = 0$) — trenutak polaska (pokretanja) motora;
- $0 < s < 1$: motorski rad;
- $s < 0$: rotor brži od polja — generatorski rad;
- $s > 1$: rotor se vrti **suprotno** od polja — kočenje.

### 3.3. Rotorska frekvencija

**Definicija i poreklo.** Naponi i struje u rotoru indukuju se zbog **relativnog** kretanja polja u
odnosu na rotor. Polje "beži" rotoru brzinom $n_s - n = s\,n_s$. Ista logika kojom smo dobili
$n_s = 60 f_s/p$ sada, u obrnutom smeru, daje frekvenciju rotorskih veličina: polju koje rotor
"vidi" da promiče brzinom $s\,n_s$ odgovara frekvencija $p\cdot s\,n_s/60 = s\cdot f_s$. Dakle:

$$f_r = s\cdot f_s$$

**Brojčani primeri.** Za $s_n = 0{,}04$ i $f_s = 50\ \mathrm{Hz}$ rotorska frekvencija je svega
$f_r = 0{,}04\cdot 50 = 2\ \mathrm{Hz}$ — rotorske struje u normalnom radu su vrlo spore. Ali pri
polasku ($s=1$) rotorska frekvencija je punih $f_r = 50\ \mathrm{Hz}$.

**Zašto je ovo važno za formule.** Rotorska reaktansa rasipanja zavisi od rotorske frekvencije,
jer je svaka reaktansa proizvod $2\pi f$ i induktivnosti ($X = 2\pi f L$, kao u sekciji 2.3).
Za rotor je ta frekvencija $f_r = s f_s$, pa je jednoredno izvođenje:

$$X_r(s) = 2\pi f_r L_{\gamma r} = 2\pi\,(s\,f_s)\,L_{\gamma r} = s\cdot X_{\gamma r}$$

gde je $X_{\gamma r} = 2\pi f_s L_{\gamma r}$ vrednost pri zaustavljenom rotoru ($s=1$, kada je
$f_r = f_s$). Isto tako, indukovani napon je srazmeran brzini promene fluksa, dakle frekvenciji
(kao kod transformatora: $E \propto f\,\Phi$), pa je

$$E_r \propto f_r\,\Phi = s\,f_s\,\Phi \quad\Longrightarrow\quad E_r = s\cdot E_{r0}$$

gde je $E_{r0}$ napon pri zaustavljenom rotoru. Ove dve činjenice su ključ za
ekvivalentnu šemu u sledećoj sekciji.

---

## 4. Ekvivalentna šema po fazi

### 4.1. Ideja: motor kao transformator sa pokretnim sekundarom

Za proračune se motor predstavlja električnom šemom **jedne faze** (trofazni motor je simetričan,
pa je dovoljno posmatrati jednu fazu; snage se onda množe sa $q_s = 3$). Šema je ista kao kod
transformatora, uz jednu presudnu izmenu koja modeluje vrtenje rotora.

Krenimo od rotorskog kola pri klizanju $s$. Ono je, električno gledano, najobičnije **redno R-L
kolo**: otpornost rotorske faze $R_r$ na red sa rasipnom reaktansom $s\cdot X_{\gamma r}$, napajano
indukovanim naponom $s\cdot E_{r0}$ (obe zavisnosti od $s$ upravo smo izveli u sekciji 3.3). Po
Omovom zakonu za naizmeničnu struju, intenzitet struje je napon podeljen **modulom impedanse**, a
za redno R-L kolo taj modul je $|Z| = \sqrt{R^2 + X^2}$ — podsetnik iz osnova elektrotehnike:
omski i induktivni deo se ne sabiraju prosto, nego "pod pravim uglom", kao katete pravouglog
trougla, jer su napon na otporniku i napon na kalemu fazno pomereni za $90^{\circ}$. Rotorska
struja (po intenzitetu) je dakle:

$$I_r = \frac{s\cdot E_{r0}}{\sqrt{R_r^2 + (s\cdot X_{\gamma r})^2}}$$

gde je:
- $E_{r0}$ — napon indukovan u rotorskoj fazi pri zaustavljenom rotoru,
- $R_r$ — omska (aktivna) otpornost rotorske faze,
- $X_{\gamma r}$ — reaktansa rasipanja rotorske faze pri zaustavljenom rotoru (indeks $\gamma$
  označava *rasipanje* — deo fluksa koji obuhvata samo rotorski namotaj, a ne i statorski).

Podelimo i brojilac i imenilac sa $s$ (dozvoljena algebarska operacija koja ne menja vrednost
razlomka):

$$I_r = \frac{E_{r0}}{\sqrt{\left(\dfrac{R_r}{s}\right)^2 + X_{\gamma r}^2}}$$

Ovo je **glavni trik cele teorije asinhronih mašina**: ista struja bi tekla u *nepokretnom* kolu
napajanom naponom $E_{r0}$ učestanosti $f_s$, u kojem umesto otpornika $R_r$ stoji otpornik
$R_r/s$. Sva mehanika vrtenja se tako "sakrila" u jedan jedini promenljivi otpornik $R_r/s$.

### 4.2. Svođenje rotorskih veličina na stator

Kao kod transformatora, zgodno je rotorske veličine preračunati ("svesti") na statorsku stranu, da
bi se obe strane mogle spojiti u jednu šemu. Ako je $m$ **prenosni odnos** (koeficijent
transformacije) stator/rotor — za namotani rotor sprege Yy to je prosto odnos efektivnih brojeva
navojaka, i baš tako se koristi u zadatku 56 — svedene veličine (obeležene primom) su:

$$R'_r = m^2\cdot R_r, \qquad X'_{\gamma r} = m^2\cdot X_{\gamma r}, \qquad I'_r = \frac{I_r}{m}, \qquad E'_{r0} = m\cdot E_{r0}$$

**Zašto baš $m^2$ za impedanse?** Svođenje mora da očuva snage. Napon se preslikava sa faktorom
$m$, struja sa faktorom $1/m$, pa se impedansa (količnik napona i struje) preslikava sa faktorom
$m / (1/m) = m^2$. Provera preko snage: $q\, I'^2_r R'_r = q\,(I_r/m)^2\, m^2 R_r = q\, I_r^2 R_r$ —
gubici su isti pre i posle svođenja, kako i mora biti. U zadatku 56 se tako od stvarne rotorske
**reaktanse rasipanja** dolazi do svedene:
$X'_{\gamma r} = m^2 X_{\gamma r} = 1{,}63^2 \cdot 0{,}24 = 0{,}638\ \Omega$; potpuno isto pravilo
važi i za otpornosti ($R'_r = m^2 R_r$). Obrnuto, svedeni rezultat se na rotorsku stranu vraća
deljenjem sa $m^2$ — u istom zadatku se od svedene ukupne rotorske otpornosti
$R'_{r\Sigma} = 11{,}717\ \Omega$ dobija stvarna
$R_{r\Sigma} = R'_{r\Sigma}/m^2 = 11{,}717/1{,}63^2 = 4{,}41\ \Omega$.

### 4.3. Elementi šeme i šta koji fizički predstavlja

Kompletna ekvivalentna šema po fazi je redno-paralelna veza sledećih elemenata: od priključka
(fazni napon $U_{sf}$) redno idu $R_s$ i $X_{\gamma s}$, zatim se kolo grana — jedna grana je
**poprečna** (paralelna) sa $X_m$ (i eventualno $R_m$), a druga nastavlja redno kroz
$X'_{\gamma r}$ i $R'_r/s$. Da topologija ne ostane samo na rečima, evo i skice šeme. Čitaj je
sleva nadesno, u smeru u kom struja "putuje": oznaka `[...]` je otpornik, `(...)` reaktansa
(kalem); gornja linija je fazni provodnik, donja je povratni provodnik, a uspravna grana u sredini
je poprečna (magnetizaciona) grana:

```text
      I_s -->    R_s        X_gs                    X'_gr       R'_r/s
  o------------[ R_s ]----( X_gs )------+---------( X'_gr )---[ R'_r/s ]---+
  +                                     |                                  |
                                        | I_mu                             |
 U_sf                               ( X_m )   (paralelno sa X_m            |
                                        |      stoji i R_m, ako se         |
  -                                     |      ne zanemari)                |
  o-------------------------------------+----------------------------------+
```

Kako se dijagram čita: struja $I_s$ ulazi sleva iz mreže, "plati putarinu" na $R_s$ (toplota) i
$X_{\gamma s}$ (rasipni fluks), pa stiže u čvor grananja. Tu se deli: deo $I_{\mu}$ silazi kroz
$X_m$ (to je struja koja održava glavno polje), a ostatak $I'_r$ nastavlja udesno kroz
$X'_{\gamma r}$ i $R'_r/s$ — to je (svedena) rotorska struja, jedina koja pravi moment. Obe grane
se sastaju na donjem, povratnom provodniku. Uloge svih elemenata su u tabeli:

| Element | Ime | Šta fizički predstavlja |
|---|---|---|
| $R_s$ | otpornost statorskog namotaja | omski (toplotni) gubici u bakru statora, $P_{\mathrm{Cu},s}$ |
| $X_{\gamma s}$ | rasipna reaktansa statora | deo statorskog fluksa koji ne stigne do rotora (rasipni fluks statora); "izgubljeni" naponski pad, ne troši snagu |
| $X_m$ | reaktansa magnećenja | glavni (korisni) fluks u vazdušnom zazoru; kroz nju teče struja magnećenja $I_{\mu}$, koja "izdržava" magnetno polje |
| $R_m$ | otpornost gubitaka u gvožđu | gubici u limovima (histerezis + vrtložne struje), $P_{\mathrm{Fe}}$; često se zanemaruje ili prebacuje u mehaničke gubitke |
| $X'_{\gamma r}$ | svedena rasipna reaktansa rotora | rasipni fluks rotora, sveden na stator |
| $R'_r/s$ | svedeni rotorski otpor podeljen klizanjem | **celokupna snaga koja pređe na rotor** (i toplota u rotoru i mehanička snaga) — vidi sekciju 5 |

Struja koja ulazi u motor, $I_s$ (fazna vrednost $I_{sf}$), grana se na struju magnećenja
$I_{\mu}$ (kroz $X_m$) i svedenu rotorsku struju $I'_r$. U praznom hodu (bez tereta,
$s \approx 0$) otpornik $R'_r/s \to \infty$ praktično prekida rotorsku granu, pa motor iz mreže
vuče samo struju magnećenja — to je **struja praznog hoda** $I_0 \approx I_{\mu}$, koju koriste
zadaci 55 i 59. Ona kod asinhronih motora nije mala (tipično $25\ \%$ do $50\ \%$ nazivne struje), jer
magnetni fluks mora da savlada vazdušni zazor.

### 4.4. Razdvajanje otpornika $R'_r/s$ — gde je mehanička snaga

Otpornik $R'_r/s$ se identički može rastaviti na dva redna otpornika (čista algebra — dodali smo i
oduzeli $R'_r$):

$$\frac{R'_r}{s} = R'_r + R'_r\cdot\frac{1-s}{s}$$

Da je ovo zaista identitet, uveri se svođenjem desne strane na zajednički imenilac $s$:

$$R'_r + R'_r\cdot\frac{1-s}{s} = \frac{R'_r\cdot s + R'_r\cdot(1-s)}{s} = \frac{R'_r\cdot\left[s + (1-s)\right]}{s} = \frac{R'_r}{s}$$

Prvi sabirak, $R'_r$, je stvarni otpor rotorskog bakra — snaga na njemu su **gubici u bakru
rotora**. Drugi sabirak, $R'_r(1-s)/s$, je *fiktivni* otpornik: snaga koja se "troši" na njemu je
zapravo **mehanička snaga** koju motor predaje vratilu. Šema, dakle, mehaničku snagu prikazuje kao
snagu na jednom izmišljenom otporniku — to je cena (i lepota) toga što smo vrteću mašinu sveli na
nepokretno kolo.

### 4.5. Pojednostavljenja koja koriste zadaci

- **Zanemarivanje $R_s$** (zadaci 50–54): kod motora srednjih i većih snaga $R_s$ je mali prema
  reaktansama, a formule za moment postaju drastično jednostavnije i simetrične. Zadaci to uvek
  naglase ("zanemariti otpornost statorskog namotaja").
- **Zanemarivanje poprečne grane** ($X_m \to \infty$, $R_m \to \infty$; zadatak 57): tada je
  statorska struja jednaka svedenoj rotorskoj, $I_s = I'_r$, a šema je prosta redna veza. Opravdano
  kad računamo struje pod opterećenjem, jer je struja magnećenja relativno mala prema struji tereta.
- **Kratkospojna (ukupna rasipna) reaktansa:**

$$X_k = X_{\gamma s} + X'_{\gamma r} = \omega_s\left(L_{\gamma s} + L'_{\gamma r}\right) = 2\pi f_s\left(L_{\gamma s} + L'_{\gamma r}\right)$$

  gde su $L_{\gamma s}$ i $L'_{\gamma r}$ odgovarajuće induktivnosti rasipanja. Ime dolazi od
  *ogleda kratkog spoja* (zakočen rotor): tada je $s = 1$ i, uz zanemarene otpore, ukupnu struju
  ograničava upravo $X_k$. U zadacima 51 i 52 podaci su dati kao induktivnosti u $\mathrm{mH}$, pa
  se $X_k$ računa množenjem sa $2\pi f_s$; npr. u zadatku 51:
  $X_k = 2\pi\cdot 50\cdot(12{,}2 + 9)\cdot 10^{-3} = 6{,}66\ \Omega$.
- **Strujno napajanje** (zadatak 55): kad motor napaja strujno regulisani pretvarač, na ulaz šeme
  se stavlja strujni izvor; tada redna statorska impedansa ne utiče na raspodelu struja, pa se
  zadržavaju samo $X_m$ i $R'_r/s$, a struja se između njih deli po pravilu strujnog razdelnika.
  Kompletna mini-lekcija — formula razdelnika, izraz za moment i uslov maksimalnog polaznog
  momenta — čeka te u sekciji 6.4.

---

## 5. Bilans snaga: $P_{\mathrm{ul}} \to P_{\mathrm{ob}} \to P_{\mathrm{meh}}$

### 5.1. Lanac snage kroz motor

Snaga kroz motor teče ovim redom (svaka strelica "naplaćuje" neki gubitak):

$$P_{\mathrm{ul}} \xrightarrow{\ -P_{\mathrm{Cu},s},\ -P_{\mathrm{Fe}}\ } P_{\mathrm{ob}} \xrightarrow{\ -P_{\mathrm{Cu},r}\ } P_{\mathrm{meh}} \xrightarrow{\ -P_{\mathrm{tr,v}}\ } P_{\mathrm{kor}}$$

- $P_{\mathrm{ul}} = q_s U_{sf} I_{sf}\cos\varphi$ — **ulazna (električna) snaga** iz mreže;
  $\cos\varphi$ je faktor snage (kosinus ugla između napona i struje).
- $P_{\mathrm{Cu},s} = q_s I_{sf}^2 R_s$ — gubici u bakru statora; $P_{\mathrm{Fe}}$ — gubici u
  gvožđu statora (u rotorskom gvožđu su zanemarljivi jer je $f_r$ mala).
- $P_{\mathrm{ob}}$ — **snaga obrtnog polja**: ono što preostane i kroz vazdušni zazor pređe na
  rotor. U ekvivalentnoj šemi to je ukupna snaga na otporniku $R'_r/s$:

$$P_{\mathrm{ob}} = q_s\, I'^2_r\, \frac{R'_r}{s}$$

- $P_{\mathrm{Cu},r} = q_s I'^2_r R'_r$ — gubici u bakru (kavezu) rotora.
- $P_{\mathrm{meh}}$ — **mehanička snaga** razvijena na rotoru (snaga fiktivnog otpornika
  $R'_r(1-s)/s$ iz sekcije 4.4).
- $P_{\mathrm{tr,v}}$ — gubici trenja (ležajevi) i ventilacije; $P_{\mathrm{kor}}$ — korisna snaga
  na vratilu. **Nazivna snaga motora $P_n$ sa natpisne pločice je uvek $P_{\mathrm{kor}}$ u
  nazivnom režimu** — mehanička, ne električna!

### 5.2. Zlatna podela: $P_{\mathrm{Cu},r} = s\cdot P_{\mathrm{ob}}$

Podelimo li gubitke u rotoru snagom obrtnog polja:

$$\frac{P_{\mathrm{Cu},r}}{P_{\mathrm{ob}}} = \frac{q_s I'^2_r R'_r}{q_s I'^2_r \dfrac{R'_r}{s}} = s$$

dobijamo dve najvažnije relacije bilansa snaga:

$$P_{\mathrm{Cu},r} = s\cdot P_{\mathrm{ob}}, \qquad P_{\mathrm{meh}} = P_{\mathrm{ob}} - P_{\mathrm{Cu},r} = (1-s)\cdot P_{\mathrm{ob}}$$

**Intuicija:** klizanje je "porez" na snagu koja pređe na rotor. Od svakog vata koji prođe kroz
zazor, deo $s$ ode u toplotu rotora, a deo $(1-s)$ postane mehanička snaga. Zato je malo klizanje
dobro (efikasan motor), a veliko klizanje znači vreo rotor. Ovo je i dubinski razlog zašto je
regulacija brzine povećavanjem klizanja rasipna (sekcija 11.2) i zašto se u zadatku 54 gubici
opterećenja poistovećuju sa $P_{\mathrm{Cu},r}$ (uz zanemaren $R_s$).

**Brojčani primer (proveren račun).** Neka motor uzima $P_{\mathrm{ul}} = 5{,}5\ \mathrm{kW}$, neka
su $P_{\mathrm{Cu},s} + P_{\mathrm{Fe}} = 0{,}5\ \mathrm{kW}$ i neka je $s = 0{,}04$. Tada:

$$P_{\mathrm{ob}} = 5500 - 500 = 5000\ \mathrm{W}$$
$$P_{\mathrm{Cu},r} = 0{,}04\cdot 5000 = 200\ \mathrm{W}, \qquad P_{\mathrm{meh}} = 0{,}96\cdot 5000 = 4800\ \mathrm{W}$$

Ako su još gubici trenja i ventilacije $100\ \mathrm{W}$, korisna snaga je
$P_{\mathrm{kor}} = 4700\ \mathrm{W}$, a stepen iskorišćenja
$\eta = P_{\mathrm{kor}}/P_{\mathrm{ul}} = 4700/5500 \approx 0{,}855$ (tj. $85{,}5\ \%$).

### 5.3. Moment iz snage

Moment je snaga podeljena ugaonom brzinom. Suština je da **ista vrednost momenta** izlazi iz dva
različita para (snaga, brzina):

$$M = \frac{P_{\mathrm{meh}}}{\Omega} = \frac{(1-s)P_{\mathrm{ob}}}{(1-s)\Omega_s} = \frac{P_{\mathrm{ob}}}{\Omega_s}$$

U srednjem koraku smo iskoristili $P_{\mathrm{meh}} = (1-s)P_{\mathrm{ob}}$ i
$\Omega = (1-s)\Omega_s$ (jer je $n = (1-s)n_s$), pa se faktor $(1-s)$ skratio. Praktična
posledica: **moment se najlakše računa kao snaga obrtnog polja podeljena sinhronom ugaonom
brzinom** — tako rade zadaci 55, 56 i 57. Provera na primeru iz 5.2 (za $n_s = 1500\ \mathrm{o/min}$,
tj. $\Omega_s = 157{,}08\ \mathrm{rad/s}$): $M = 5000/157{,}08 = 31{,}8\ \mathrm{Nm}$, a isto daje i
$P_{\mathrm{meh}}/\Omega = 4800/(0{,}96\cdot 157{,}08) = 31{,}8\ \mathrm{Nm}$.

Iz istog obrasca dolazi i veza koju zadaci koriste na svakom koraku — **nazivni moment iz podataka
sa pločice**:

$$M_n = \frac{P_n}{\Omega_n} = \frac{P_n}{\dfrac{2\pi}{60}\cdot n_n}$$

Primer (ulaz u zadatak 50): $P_n = 4\ \mathrm{kW}$, $n_n = 1440\ \mathrm{o/min}$:

$$M_n = \frac{4000}{\dfrac{2\pi}{60}\cdot 1440} = 26{,}5\ \mathrm{Nm}$$

(Strogo uzevši, $P_n/\Omega_n$ je moment na vratilu, a elektromagnetni moment je za doprinos
trenja malo veći; u zadacima se ta razlika zanemaruje jer su gubici trenja mali.)

---

## 6. Moment: opšti izraz, prevalni moment i prevalno klizanje

### 6.1. Opšti izraz momenta (uz zanemaren $R_s$)

Uz zanemarenu statorsku otpornost i poprečnu granu, ekvivalentna šema po fazi je prosta redna veza:
napon $U_{sf}$ tera struju kroz $X_k$ i $R'_r/s$. Intenzitet svedene rotorske struje je:

$$I'_r = \frac{U_{sf}}{\sqrt{\left(\dfrac{R'_r}{s}\right)^2 + X_k^2}}$$

Snaga obrtnog polja je $P_{\mathrm{ob}} = q_s I'^2_r (R'_r/s)$, a moment $M = P_{\mathrm{ob}}/\Omega_s$.
Uvrstimo struju:

$$M = \frac{q_s}{\Omega_s}\cdot U_{sf}^2\cdot \frac{R'_r/s}{\left(\dfrac{R'_r}{s}\right)^2 + X_k^2}$$

Ovo je formula (50.6) iz zbirke (tamo zapisana sa $\omega_s$ u smislu naše $\Omega_s$ — vidi
napomenu u sekciji 2.3). Simboli: $q_s = 3$ broj faza, $U_{sf}$ fazni napon statora,
$X_k = X_{\gamma s} + X'_{\gamma r}$ kratkospojna reaktansa. Primeti odmah: **moment zavisi od
kvadrata napona** — smanjiš li napon za $10\ \%$, moment na istom klizanju padne za $19\ \%$.

### 6.2. Gde je maksimum? Prevalno klizanje

Moment kao funkcija klizanja ima maksimum. Nađimo ga. Uvedimo smenu $x = R'_r/s$ (što je $s$ veće,
$x$ je manje) i posmatrajmo deo formule koji zavisi od $s$:

$$f(x) = \frac{x}{x^2 + X_k^2} = \frac{1}{x + \dfrac{X_k^2}{x}}$$

(drugi oblik smo dobili deljenjem brojioca i imenioca sa $x$). Funkcija $f$ je najveća kad je
imenilac $x + X_k^2/x$ najmanji. Zbir broja i njemu obrnuto proporcionalnog broja najmanji je kad
su sabirci jednaki (nejednakost aritmetičke i geometrijske sredine; formalno: izvod
$1 - X_k^2/x^2 = 0$ daje $x = X_k$). Dakle, maksimum momenta nastupa kada je:

$$\frac{R'_r}{s} = X_k$$

tj. kada je fiktivni otpornik po vrednosti jednak kratkospojnoj reaktansi. Klizanje pri kojem se to
dešava zove se **prevalno klizanje**:

$$s_{\mathrm{pr}} = \pm\frac{R'_r}{X_k} = \pm\frac{R'_r}{X_{\gamma s} + X'_{\gamma r}} = \pm\frac{R'_r}{2\pi f_s\left(L_{\gamma s} + L'_{\gamma r}\right)}$$

(formula (50.7) u zbirci). Znak $+$ važi u motorskom, znak $-$ u generatorskom režimu; u zadacima
radimo sa apsolutnom vrednošću. Dva zapažanja koja zadaci direktno koriste:

- $s_{\mathrm{pr}}$ je **srazmerno rotorskoj otpornosti** $R'_r$ — dodavanjem otpora u rotor (kod
  namotanog rotora) prevalna tačka se pomera ka većim klizanjima, a maksimum momenta ostaje isti;
- $s_{\mathrm{pr}}$ je **obrnuto srazmerno frekvenciji** $f_s$ — na nižoj frekvenciji preval je na
  većem klizanju (koristi se u zadacima 50 i 51).

### 6.3. Prevalni moment

Uvrstimo $R'_r/s_{\mathrm{pr}} = X_k$ nazad u opšti izraz momenta:

$$M_{\mathrm{pr}} = \frac{q_s}{\Omega_s}\cdot U_{sf}^2\cdot \frac{X_k}{X_k^2 + X_k^2} = \frac{q_s\cdot U_{sf}^2}{2\,\Omega_s\, X_k}$$

**Prevalni (maksimalni) moment** je najveći moment koji motor uopšte može da razvije pri datom
naponu i frekvenciji; pređe li teret tu granicu, motor se "prevali" — naglo izgubi brzinu i stane
(otuda ime). Uz $\Omega_s = \pi n_s/30$ ovo je tačno oblik iz zadataka 51 i 52:

$$M_{\mathrm{pr}} = \frac{q_s\, U_{sf}^2}{\dfrac{\pi}{30} n_s \cdot 2\left(X_{\gamma s} + X'_{\gamma r}\right)} = \frac{30}{\pi}\cdot\frac{q_s}{n_s}\cdot\frac{U_{sf}^2}{2\left(X_{\gamma s} + X'_{\gamma r}\right)}$$

**Brojčani primer (ulaz u zadatak 51):** motor $220\ \mathrm{V}$, $50\ \mathrm{Hz}$, sprega Δ (pa je
fazni napon jednak linijskom, $U_{sf} = 220\ \mathrm{V}$ — mini-lekcija u sekciji 1),
$n_s = 1500\ \mathrm{o/min}$,
$X_k = 6{,}66\ \Omega$:

$$M_{\mathrm{pr}} = 3\cdot\frac{220^2}{\dfrac{\pi}{30}\cdot 1500\cdot 2\cdot 6{,}66} = 69{,}4\ \mathrm{Nm}, \qquad s_{\mathrm{pr}} = \frac{2{,}56}{6{,}66} = 0{,}384$$

Ključna zapažanja o $M_{\mathrm{pr}}$ (svako od njih nosi po jedan zadatak):

1. **$M_{\mathrm{pr}}$ ne zavisi od $R'_r$.** Dodavanje otpora u rotor ne menja visinu maksimuma,
   samo ga pomera ka većem klizanju (nižoj brzini). Zato se namotanom rotoru dodaje otpor za
   pokretanje i kočenje bez žrtvovanja momenta.
2. **$M_{\mathrm{pr}} \propto U_{sf}^2$** — vrlo osetljiv na napon.
3. Raspišemo li $\Omega_s = 2\pi f_s/p$ i $X_k = 2\pi f_s(L_{\gamma s} + L'_{\gamma r})$:

$$M_{\mathrm{pr}} = \frac{q_s\, U_{sf}^2\, p}{2\cdot 2\pi f_s\cdot 2\pi f_s\left(L_{\gamma s} + L'_{\gamma r}\right)} = \frac{p\cdot q_s}{8\pi^2}\cdot\left(\frac{U_{sf}}{f_s}\right)^2\cdot\frac{1}{L_{\gamma s} + L'_{\gamma r}}$$

   (formula (50.8) u zbirci). **Prevalni moment zavisi samo od količnika $U_{sf}/f_s$.** Držimo li
   $U/f = \mathrm{const}$, prevalni moment je isti na svim frekvencijama — to je temelj skalarnog
   upravljanja u sekciji 11.3 i zadacima 50–52. Ako pak napon ostane na nazivnom, a frekvencija
   raste (slabljenje polja), onda $M_{\mathrm{pr}} \propto 1/f_s^2$: npr. na $70\ \mathrm{Hz}$
   umesto $50\ \mathrm{Hz}$ prevalni moment padne na $(50/70)^2 = 0{,}51$ nazivnog prevalnog
   (zadatak 50).

Odnos prevalnog i nazivnog momenta zove se **preopteretivost**:

$$\nu = \frac{M_{\mathrm{pr}}}{M_n}$$

i tipično iznosi od $1{,}8$ do $3$. Proizvođač je često daje na pločici (u zadatku 50:
$\nu = M_{\mathrm{max}}/M_n = 2{,}5$). U zadacima se isti simbol koristi i opštije, kao odnos
prevalnog momenta i *bilo kog* momenta ($\nu = M_{\mathrm{pr}}/M$); kad je taj drugi moment teret
$M_t$, zbirka piše i $\gamma$ (zadatak 51) ili $\nu_T$ (zadatak 52) — sve je to ista ideja: *koliko
puta je maksimum iznad posmatranog momenta*.

### 6.4. Moment pri strujnom napajanju i maksimalni polazni moment (zadatak 55)

Sve dosadašnje formule za moment pretpostavljaju da mreža motoru nameće **napon**. Savremeni
frekventni pretvarači, međutim, često rade kao **strujni izvori**: elektronika drži zadatu efektivnu
vrednost statorske struje $I_s$ (npr. na strujnom limitu pretvarača pri polasku), a napon se
"namesti sam". Zadatak 55 pita: koliki najveći polazni moment motor može da razvije kad je struja
ograničena? Za to nam treba izraz za moment iz *struje* umesto iz napona.

**Šema za strujno napajanje.** Kako je rečeno u sekciji 4.5: strujni izvor kroz redne elemente
$R_s$ i $X_{\gamma s}$ progura tačno zadatu struju ma koliki oni bili, pa oni ne utiču na
raspodelu struja (samo menjaju napon izvora) i izbacujemo ih iz priče. Rotorska rasipna reaktansa
$X'_{\gamma r}$ se u zadatku 55 zanemaruje (podatak za nju i ne postoji). Ostaje najprostija moguća
slika: strujni izvor $I_s$ napaja **paralelnu vezu** reaktanse magnećenja $X_m$ i fiktivnog
otpornika $R'_r/s$.

**Strujni razdelnik.** Obe paralelne grane imaju isti napon; struja se zato deli obrnuto srazmerno
impedansama — kroz granu ide onoliko struje koliko joj impedansa "dozvoli". Rotorska struja je:

$$I'_r = I_s\cdot\frac{X_m}{\sqrt{X_m^2 + \left(\dfrac{R'_r}{s}\right)^2}}$$

U brojiocu je impedansa *one druge* (paralelne) grane, u imeniocu modul zbira impedansi obe grane —
$\sqrt{X_m^2 + (R'_r/s)^2}$, jer se reaktansa $X_m$ i otpornost $R'_r/s$ sabiraju "pod pravim
uglom" (kao u sekciji 4.1). Provera smisla: za $s \to 0$ (prazan hod) $R'_r/s \to \infty$, pa
$I'_r \to 0$ — sva struja ide u magnećenje, baš kako sekcija 4.3 kaže.

**Moment.** Po već poznatom pravilu $M = P_{\mathrm{ob}}/\Omega_s$ i
$P_{\mathrm{ob}} = q_s I'^2_r (R'_r/s)$:

$$M = \frac{3}{\Omega_s}\cdot\frac{R'_r}{s}\cdot I'^2_r = \frac{3}{\Omega_s}\cdot I_s^2\cdot\frac{X_m^2\cdot\dfrac{R'_r}{s}}{X_m^2 + \left(\dfrac{R'_r}{s}\right)^2}$$

**Gde je maksimum?** Uvedimo opet smenu $x = R'_r/s$ i pogledajmo deo koji zavisi od $s$:
$x/(x^2 + X_m^2)$ — **potpuno ista funkcija kao u sekciji 6.2**, samo sa $X_m$ umesto $X_k$! Istom
logikom (zbir $x + X_m^2/x$ najmanji kad su sabirci jednaki) maksimum nastupa kada je:

$$\frac{R'_r}{s} = X_m$$

Uporedi sa naponskim napajanjem ($R'_r/s = X_k$): sada ulogu "merodavne" reaktanse igra
**reaktansa magnećenja** $X_m$, jer o raspodeli zadate struje odlučuje magnetizaciona grana, a ne
rasipne reaktanse. (Da $X'_{\gamma r}$ nije zanemarena, uslov bi glasio
$R'_r/s = X_m + X'_{\gamma r}$ — ista logika, samo bi se u imeniocu razdelnika pojavio zbir
$X_m + X'_{\gamma r}$.) Uvrštavanjem $R'_r/s = X_m$ u izraz za moment dobija se maksimum:

$$M_{\mathrm{max}} = \frac{3}{\Omega_s}\cdot I_s^2\cdot\frac{X_m^2\cdot X_m}{2X_m^2} = \frac{3\,X_m\,I_s^2}{2\,\Omega_s}$$

**Kako se uslov ispunjava pri polasku (s = 1)?** Pri polasku uslov glasi $R'_r = X_m$. Ali $R'_r$
je konstanta — jedino što pretvarač može da menja je *frekvencija*, a sa njom i
$X_m = 2\pi f_s L_m$! Zato pretvarač polazak izvodi na vrlo niskoj frekvenciji $f_{s\mathrm{max}}$,
izabranoj tako da $X_m$ padne baš na vrednost $R'_r$. Reaktansa magnećenja na $50\ \mathrm{Hz}$
zna se iz ogleda praznog hoda ($X_m^{50} \approx U_{sf}/I_0$, jer u praznom hodu motor vuče
praktično samo struju magnećenja — sekcija 4.3), a pošto je $X_m$ srazmerna frekvenciji:

$$\frac{X_m}{X_m^{50}} = \frac{f_{s\mathrm{max}}}{50} \quad\Longrightarrow\quad f_{s\mathrm{max}} = 50\cdot\frac{R'_r}{X_m^{50}} = 50\cdot\frac{R'_r\, I_0}{U_{sf}}$$

**Brojčani primer (zadatak 55):** $R'_r = 0{,}6\ \Omega$, $I_0 = 9\ \mathrm{A}$, sprega Y na
$380\ \mathrm{V}$ (pa je $U_{sf} = 380/\sqrt{3} = 220\ \mathrm{V}$), struja ograničena na
$I_s = 25\ \mathrm{A}$:

$$f_{s\mathrm{max}} = 50\cdot\frac{0{,}6\cdot 9}{220} = 1{,}23\ \mathrm{Hz}, \qquad
M_{\mathrm{max}} = \frac{3\,R'_r\,p}{2\pi f_{s\mathrm{max}}}\cdot\frac{I_s^2}{2} = \frac{3\cdot 0{,}6\cdot 2}{2\pi\cdot 1{,}23}\cdot\frac{25^2}{2} = 145{,}6\ \mathrm{Nm}$$

(u drugom koraku je uvršteno $\Omega_s = 2\pi f_{s\mathrm{max}}/p$ i $X_m = R'_r$). Polazna
frekvencija ispada neverovatno mala — nešto preko $1\ \mathrm{Hz}$ — a moment ogroman za struju od
svega $25\ \mathrm{A}$: strujno upravljani pogon startuje "meko po struji, a snažno po momentu",
jer je frekvencijom sva raspoloživa struja preusmerena tamo gde pravi moment.

---

## 7. Klosova formula

### 7.1. Izvođenje

Podelimo opšti izraz momenta (6.1) prevalnim momentom (6.3):

$$\frac{M}{M_{\mathrm{pr}}} = \frac{\dfrac{q_s}{\Omega_s} U_{sf}^2 \dfrac{x}{x^2 + X_k^2}}{\dfrac{q_s U_{sf}^2}{2\,\Omega_s X_k}} = \frac{2 X_k\, x}{x^2 + X_k^2} = \frac{2}{\dfrac{x}{X_k} + \dfrac{X_k}{x}}$$

(u poslednjem koraku smo brojilac i imenilac podelili sa $x X_k$). Sada iskoristimo
$x = R'_r/s$ i $X_k = R'_r/s_{\mathrm{pr}}$, odakle je $x/X_k = s_{\mathrm{pr}}/s$ i
$X_k/x = s/s_{\mathrm{pr}}$. Dobijamo **Klosovu formulu**:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}}$$

Sve mašinske konstante ($U_{sf}$, $X_k$, $q_s$, $\Omega_s$, $R'_r$) su se skratile! Cela momentna
karakteristika opisana je sa **samo dva broja**: $M_{\mathrm{pr}}$ i $s_{\mathrm{pr}}$. To je
razlog zašto je Klosova formula radni konj zadataka 50–54: iz kataloških podataka (nazivni moment,
preopteretivost, nazivno klizanje) rekonstruiše celu krivu, bez poznavanja parametara šeme.
(Formula je približna utoliko što je izvedena uz zanemaren $R_s$ — za motore srednjih snaga to je
sasvim dobra aproksimacija.)

**Intuicija za oblik:** imenilac je zbir "broj + obrnuti broj", minimalan (i jednak 2) baš kad je
$s = s_{\mathrm{pr}}$ — tada je $M = M_{\mathrm{pr}}$, kako i treba. Daleko od prevala jedan od dva
sabirka dominira, pa moment opada i levo i desno od maksimuma.

### 7.2. Klosova formula kao kvadratna jednačina

U zadacima je tipično poznat moment (npr. teret), a traži se klizanje — ili obrnuto. Klosovu
formulu tada prepišemo kao kvadratnu jednačinu. Krenimo od:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2\, s\, s_{\mathrm{pr}}}{s^2 + s_{\mathrm{pr}}^2}$$

(dobijeno množenjem brojioca i imenioca sa $s\,s_{\mathrm{pr}}$). Unakrsnim množenjem:

$$M\left(s^2 + s_{\mathrm{pr}}^2\right) = 2 M_{\mathrm{pr}}\, s\, s_{\mathrm{pr}}$$

pa deljenjem sa $M$ i prebacivanjem svega na jednu stranu, uz oznaku $\nu = M_{\mathrm{pr}}/M$:

$$s^2 - 2\,\nu\, s\, s_{\mathrm{pr}} + s_{\mathrm{pr}}^2 = 0$$

Ovo je jednačina (50.4) iz zbirke. Rešimo je klasičnom formulom za kvadratnu jednačinu
$s_{1,2} = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a}$; ovde je $a = 1$, $b = -2\nu s_{\mathrm{pr}}$ i
$c = s_{\mathrm{pr}}^2$, pa je:

$$s_{1,2} = \frac{2\nu s_{\mathrm{pr}} \pm \sqrt{4\nu^2 s_{\mathrm{pr}}^2 - 4 s_{\mathrm{pr}}^2}}{2} = \frac{2\nu s_{\mathrm{pr}} \pm \sqrt{4 s_{\mathrm{pr}}^2\left(\nu^2 - 1\right)}}{2} = \frac{2\nu s_{\mathrm{pr}} \pm 2 s_{\mathrm{pr}}\sqrt{\nu^2 - 1}}{2}$$

U srednjem koraku smo ispod korena izvukli zajednički faktor $4 s_{\mathrm{pr}}^2$, a zatim ga
iskorenili kao $2 s_{\mathrm{pr}}$. Skraćivanjem dvojke i izvlačenjem $s_{\mathrm{pr}}$ ispred
zagrade:

$$s_{1,2} = s_{\mathrm{pr}}\left(\nu \pm \sqrt{\nu^2 - 1}\right)$$

a potpuno simetrično, ako je poznato $s$ a traži se $s_{\mathrm{pr}}$:

$$s_{\mathrm{pr}\,1,2} = s\left(\nu \pm \sqrt{\nu^2 - 1}\right)$$

**Koje od dva rešenja je pravo?** Po Vietovim pravilima proizvod rešenja je
$s_1\cdot s_2 = s_{\mathrm{pr}}^2$ — jedno rešenje je uvek ispod, a drugo iznad prevalnog
klizanja (isti moment kriva seče jednom levo i jednom desno od maksimuma). Pravila izbora:

- tražiš **radno klizanje** na stabilnom delu karakteristike → uzmi **manje** rešenje, tj. znak
  minus: $s = s_{\mathrm{pr}}(\nu - \sqrt{\nu^2 - 1})$ (tako rade zadaci 50, 51, 52);
- tražiš **prevalno klizanje iz nazivne tačke** ($s_n < s_{\mathrm{pr}}$ mora da važi) → uzmi
  **veće**: $s_{\mathrm{pr}} = s_n(\nu + \sqrt{\nu^2 - 1})$ (zadatak 50);
- ako iz polazne tačke ($s = 1$) računaš $s_{\mathrm{pr}}$, fizički ispravno je ono rešenje koje je
  manje od 1 (preval je između polaska i radne tačke) — zadatak 53.

**Brojčani primer (proveren račun; ulaz u zadatak 50).** Nazivno klizanje $s_n = 0{,}04$,
preopteretivost $\nu = 2{,}5$:

$$s_{\mathrm{pr}} = 0{,}04\cdot\left(2{,}5 + \sqrt{2{,}5^2 - 1}\right) = 0{,}04\cdot\left(2{,}5 + 2{,}29\right) = 0{,}192 = 19{,}2\ \%$$

Unakrsna provera Klosovom formulom: pri $s = s_n = 0{,}04$ mora da se vrati nazivni moment.
Zaista, $\dfrac{2}{\frac{0{,}04}{0{,}192} + \frac{0{,}192}{0{,}04}} = 0{,}40 = \dfrac{1}{2{,}5} = \dfrac{1}{\nu}$,
tj. $M = 0{,}40\cdot M_{\mathrm{pr}} = M_n$. Formula je konzistentna sama sa sobom.

### 7.3. Rotorske struje i koeficijent rasipanja $\sigma$ (zadaci 53 i 54)

Klosova formula odgovara na pitanja o *momentima*. Ali zadaci 53 i 54 pitaju i za **struje**:
koliko je puta polazna rotorska struja veća od nazivne (zadatak 53), odnosno šta odnos struja
govori o prevalnom klizanju kad su poznati gubici (zadatak 54). Za to zbirka koristi izraz za
rotorsku struju **tačniji** od onog iz sekcije 6.1 — takav koji ne zanemaruje granu magnećenja
$X_m$. U njemu se pojavljuje novo slovo, **koeficijent rasipanja** $\sigma$, i red je da vidimo
odakle dolazi.

**Izvođenje tačnijeg izraza.** Šema: zanemarimo $R_s$ (kao u celoj ovoj glavi), ali *zadržimo*
$X_m$. Od izvora $U_{sf}$ redno ide $X_{\gamma s}$, pa čvor iz kojeg se grana $X_m$ (poprečno) i
rotorska grana $X'_{\gamma r}$ + $R'_r/s$. Rotorsku struju dobijamo u dva koraka. Ukupna struja je
$\underline{I}_s = U_{sf}/\underline{Z}_{\mathrm{uk}}$, gde je
$\underline{Z}_{\mathrm{uk}} = jX_{\gamma s} + \dfrac{jX_m\left(\frac{R'_r}{s} + jX'_{\gamma r}\right)}{jX_m + \frac{R'_r}{s} + jX'_{\gamma r}}$
(redna reaktansa plus paralelna veza), a strujni razdelnik daje
$\underline{I}'_r = \underline{I}_s\cdot\dfrac{jX_m}{jX_m + \frac{R'_r}{s} + jX'_{\gamma r}}$.
Kad se ovo dvoje spoji i sredi (imenilac se pomnoži, pa se i brojilac i imenilac podele sa
$jX_m$ — uradi taj korak na papiru, sve se lepo skraćuje), dobija se kompaktan rezultat:

$$\underline{I}'_r = \frac{U_{sf}}{\sigma\cdot\dfrac{R'_r}{s} + j\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}, \qquad \sigma = 1 + \frac{X_{\gamma s}}{X_m}$$

**Šta je $\sigma$ fizički?** Broj *malo veći od jedinice* (jer je rasipna reaktansa $X_{\gamma s}$
mnogo manja od reaktanse magnećenja $X_m$; tipično $\sigma = 1{,}02$ do $1{,}1$). On "naduva"
rotorske parametre u imeniocu i time uračunava da deo statorske struje ode u granu magnećenja
umesto u rotor. Granični slučaj je odlična provera: pusti $X_m \to \infty$ (zanemarena poprečna
grana) — tada $\sigma \to 1$ i formula se svede tačno na prostu formulu iz sekcije 6.1,
$I'_r = U_{sf}\big/\sqrt{(R'_r/s)^2 + X_k^2}$. I prevalno klizanje ima svoj tačniji oblik: istom
logikom kao u sekciji 6.2 (maksimizacija po $s$) dobija se

$$s_{\mathrm{pr}} = \frac{\sigma\, R'_r}{X_{\gamma s} + \sigma\, X'_{\gamma r}}$$

što se za $\sigma = 1$ svodi na poznato $R'_r/X_k$. Zapamti ovu jednakost — ona je ključ sledećeg
koraka.

**Glavni trik: odnos dve struje istog motora.** U zadacima nisu poznati ni $\sigma$, ni reaktanse,
ni $R'_r$ — ali i ne trebaju! Traži se uvek *odnos* dve struje, a u odnosu se sve mašinske
konstante skrate. Podelimo brojilac i imenilac izraza za $\underline{I}'_r$ sa
$(X_{\gamma s} + \sigma X'_{\gamma r})$ i prepoznajmo $s_{\mathrm{pr}}$ iz jednakosti iznad:

$$\underline{I}'_r = \frac{U_{sf}\,/\,(X_{\gamma s} + \sigma X'_{\gamma r})}{\dfrac{s_{\mathrm{pr}}}{s} + j}$$

Ceo brojilac je konstanta mašine — od radne tačke zavisi samo imenilac $s_{\mathrm{pr}}/s + j$!
Odatle za **polaznu** struju ($s = 1$, indeks $\mathrm{k}$ kao "kratak spoj/polazak", isti kao kod
$M_k$) i **nazivnu** struju ($s = s_n$):

$$\frac{\underline{I}'_{r\mathrm{k}}}{\underline{I}'_{r\mathrm{n}}} = \frac{\dfrac{s_{\mathrm{pr}}}{s_n} + j}{s_{\mathrm{pr}} + j}
\quad\Longrightarrow\quad
\frac{I'_{r\mathrm{k}}}{I'_{r\mathrm{n}}} = \frac{\sqrt{\left(\dfrac{s_{\mathrm{pr}}}{s_n}\right)^2 + 1}}{\sqrt{s_{\mathrm{pr}}^2 + 1}}$$

(intenzitet kompleksnog broja $a + j$ je $\sqrt{a^2+1}$). **Brojčani primer (zadatak 53):** iz
Klosove kvadratne jednačine tamo ispadne $s_{\mathrm{pr}} = 0{,}485$ i $s_n = 0{,}123$, pa je

$$\frac{I'_{r\mathrm{k}}}{I'_{r\mathrm{n}}} = \frac{\sqrt{(0{,}485/0{,}123)^2 + 1}}{\sqrt{0{,}485^2 + 1}} = \frac{\sqrt{16{,}55}}{\sqrt{1{,}235}} = 3{,}7$$

Polazna struja je skoro četiri puta veća od nazivne — zato pokretanje velikih motora direktnim
priključenjem na mrežu izaziva propade napona i zato postoje ograničenja polazne struje.

**Varijanta iz zadatka 54: struja pri prevalnom klizanju.** Stavimo li $s = s_{\mathrm{pr}}$,
imenilac postaje $s_{\mathrm{pr}}/s_{\mathrm{pr}} + j = 1 + j$, čiji je intenzitet $\sqrt{2}$:

$$\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}} = \frac{\sqrt{\left(\dfrac{s_{\mathrm{pr}}}{s_n}\right)^2 + 1}}{\sqrt{2}}$$

Zadatak 54 ovu vezu koristi *unazad*: poznato je da su gubici opterećenja pri prevalnom momentu 9
puta veći od nazivnih, a gubici rastu sa kvadratom struje ($P_{\mathrm{Cu},r} = q\,I'^2_r R'_r$,
sekcija 5), pa je odnos struja $\sqrt{9} = 3$. Rešavanjem gornje jednačine po $s_{\mathrm{pr}}$
(kvadriraj obe strane, pomnoži sa 2, oduzmi 1, koreni):

$$s_{\mathrm{pr}} = s_n\cdot\sqrt{2\left(\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}}\right)^2 - 1} = 0{,}028\cdot\sqrt{2\cdot 3^2 - 1} = 0{,}028\cdot\sqrt{17} = 0{,}115$$

**Šta smo dobili:** za momente je i dalje dovoljan prost model (Klos); čim se pitanje tiče
*struja*, zbirka poseže za tačnijim izrazom sa $\sigma$ — ali pošto se uvek radi sa odnosima, na
kraju sve zavisi samo od dva klizanja, $s_n$ i $s_{\mathrm{pr}}$, koja već umeš da nađeš Klosovom
formulom. Nijedna nova brojka o mašini nije potrebna.

---

## 8. Momentna karakteristika $M(n)$ i kako se čita

**Definicija.** Momentna (mehanička) karakteristika je grafik razvijenog momenta u zavisnosti od
brzine, $M(n)$, ili ravnopravno od klizanja, $M(s)$ — jer su $n$ i $s$ vezani sa $n = (1-s)n_s$.
Na grafiku $M(n)$ brzina raste udesno; imaj u vidu da tada klizanje **opada** udesno ($n = 0$
odgovara $s = 1$, a $n = n_s$ odgovara $s = 0$).

Kako izgleda kriva u motorskoj oblasti, čitano sleva (od $n = 0$) udesno (ka $n = n_s$):

1. **Polazna tačka** ($n = 0$, $s = 1$): motor razvija **polazni moment** $M_k$. Iz Klosove
   formule sa $s = 1$:

$$\frac{M_k}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{1}{s_{\mathrm{pr}}} + s_{\mathrm{pr}}}$$

   Za naš primer ($s_{\mathrm{pr}} = 0{,}192$): $M_k/M_{\mathrm{pr}} = 2/(5{,}21 + 0{,}192) = 0{,}37$,
   tj. $M_k = 0{,}37\cdot 2{,}5\, M_n = 0{,}93\, M_n$ — polazni moment je reda nazivnog.
2. **Uspon do prevala:** kako se rotor zaleće i $s$ opada ka $s_{\mathrm{pr}}$, moment raste, do
   maksimuma $M_{\mathrm{pr}}$ u tački $s = s_{\mathrm{pr}}$ (tj. $n = (1 - s_{\mathrm{pr}})n_s$).
3. **Radni (stabilni) deo:** desno od prevala moment naglo opada ka nuli u $n = n_s$. Ovaj deo je
   strm i **približno prav**. To se vidi iz Klosove formule: za $s \ll s_{\mathrm{pr}}$ član
   $s/s_{\mathrm{pr}}$ je zanemarljiv prema $s_{\mathrm{pr}}/s$, pa

$$\frac{M}{M_{\mathrm{pr}}} \approx \frac{2}{\dfrac{s_{\mathrm{pr}}}{s}} = \frac{2\,s}{s_{\mathrm{pr}}} \quad\Longrightarrow\quad M \approx \frac{2 M_{\mathrm{pr}}}{s_{\mathrm{pr}}}\cdot s$$

   — moment je na radnom delu **linearan po klizanju**. Sve normalne radne tačke motora
   (uključujući nazivnu) leže na ovom strmom delu, blizu $n_s$.

Kad čitaš momentne karakteristike u zadacima (slike 51.1, 51.2, 52.1, 52.2, 56.1, 57.4), obrati
pažnju na tri stvari: gde kriva seče osu brzine (to je $n_s$ — pomera se sa frekvencijom), koliki
joj je vrh (to je $M_{\mathrm{pr}}$ — pomera se sa $(U/f)^2$) i gde horizontalna prava tereta seče
radni deo (to je stacionarna radna tačka — sledeća sekcija).

---

## 9. Stabilna i nestabilna radna tačka sa radnom mašinom

Motor nikad ne radi sam: na vratilu visi **radna mašina** (pumpa, dizalica, ventilator...) sa
svojom karakteristikom **otpornog momenta** $M_t(n)$ — momenta kojim se teret opire vrtenju. U
zadacima 50–52 teret je **konstantan** ($M_t = \mathrm{const}$, nezavisno od brzine) i
"potencijalne prirode" — tipično dizalica, gde moment potiče od težine tereta pa je isti ma kojom
se brzinom dizalo.

**Gde motor radi?** Zakon obrtanja (Njutnov zakon za rotaciju) glasi:

$$J\cdot\frac{d\Omega}{dt} = M - M_t$$

gde je $J$ moment inercije obrtnih masa. U stacionarnom stanju brzina se ne menja
($d\Omega/dt = 0$), pa mora biti $M = M_t$: **radna tačka je presek karakteristike motora $M(n)$ i
karakteristike tereta $M_t(n)$.** Horizontalna prava $M_t = \mathrm{const}$ seče krivu motora u
(najviše) dve tačke — jednoj na strmom delu desno od prevala i jednoj na usponu levo od prevala.

- **Presek na radnom delu (desno od prevala) je stabilan.** Perturbuj brzinu malo nadole: klizanje
  poraste, motorov moment (na strmom delu) poraste iznad $M_t$, višak momenta ubrza rotor nazad.
  Perturbuj nagore: moment padne ispod tereta i rotor uspori nazad. Sistem se sam vraća — kao
  kliker na dnu udubljenja.
- **Presek levo od prevala je nestabilan.** Tu moment motora *raste* sa brzinom: uspori li rotor
  malo, motorov moment padne još niže od tereta, pa rotor dalje usporava — do zastoja; ubrza li se,
  višak momenta ga tera još brže, dok ne "pređe preval" i skrasi se u stabilnoj tački. Kao kliker
  na vrhu brega.

Praktično pravilo za zadatke: **stacionarno rešenje je uvek ono sa klizanjem manjim od prevalnog**
— zato se u Klosovoj kvadratnoj jednačini "uzima rešenje manje od jedinice" odnosno manje od
$s_{\mathrm{pr}}$ (zadaci 50, 51, 52). I još jedno: motor uopšte može da vuče teret samo ako je
$M_t < M_{\mathrm{pr}}$ (prava tereta mora da seče krivu!) — na tome se zasniva određivanje
maksimalne frekvencije u zadatku 51b (frekvencija se diže dok $M_{\mathrm{pr}}$, koji u slabljenju
polja opada, ne padne na vrednost tereta) i maksimalnog ubrzanja u zadatku 52b (najveći višak
$M - M_t$ na polasku dobija se ako motor kreće baš iz prevalne tačke). A kako se motor "natera" da
krene iz prevalne tačke? Izborom startne frekvencije: treba da prevalna tačka padne baš u $n = 0$.
Pošto apsolutno prevalno klizanje $\Delta n_{\mathrm{pr}} = s_{\mathrm{pr}}\cdot n_s$ pri
$U/f = \mathrm{const}$ ne zavisi od frekvencije ($s_{\mathrm{pr}} \propto 1/f_s$, a
$n_s \propto f_s$, pa se $f_s$ skrati), uslov glasi $n_{sb} = \Delta n_{\mathrm{pr}}$, tj.
$f_{sb} = s_{\mathrm{pr}}\cdot f_{sn}$. U zadatku 52 je $s_{\mathrm{pr}} = 0{,}4$, pa je
$f_{sb} = 0{,}4\cdot 50 = 20\ \mathrm{Hz}$, uz napon skaliran po $U/f$:
$U_{sb} = 380\cdot 20/50 = 152\ \mathrm{V}$ (detaljnije o $U/f$ receptu u sekciji 11.3).

---

## 10. Režimi rada asinhrone mašine

Ista mašina, zavisno od odnosa brzine rotora i polja, radi kao motor, generator ili kočnica.
Režim čitaš direktno iz klizanja:

| Režim | Klizanje | Brzina | Šta se dešava sa snagom |
|---|---|---|---|
| Motor | $0 < s < 1$ | $0 < n < n_s$, isti smer kao polje | električna → mehanička |
| Generator | $s < 0$ | $n > n_s$, isti smer | mehanička → električna (u mrežu) |
| Kočnica (protivstrujno) | $s > 1$ | rotor se vrti **suprotno** od polja | i električna i mehanička → toplota u rotoru |

### 10.1. Generatorski režim

Ako spoljna mašina (ili inercija pri naglom snižavanju frekvencije napajanja) zavrti rotor **brže**
od polja ($n > n_s$, $s < 0$), uloge se obrću: rotor "gura" polje umesto da ga juri, moment menja
znak i mašina predaje aktivnu snagu mreži. Ovo se dešava, na primer, kod dizalice koja spušta
teret. Momentna karakteristika se glatko nastavlja u oblast $n > n_s$ sa negativnim momentom
(ima i svoj negativni preval, $s_{\mathrm{pr}} < 0$ — otuda znak $\pm$ u formuli za
$s_{\mathrm{pr}}$).

### 10.2. Protivstrujno kočenje (kočenje suprotnim poljem)

Motoru koji se vrti zamene se **dve faze napajanja**. Obrtno polje gotovo trenutno promeni smer
(struje se uspostave brzo), a rotor zbog mehaničke inercije nastavi da se vrti po starom — sada
**suprotno** od polja. Novo klizanje, računato prema novom smeru polja, je:

$$s_{\mathrm{koc}} = \frac{n_s - (-n)}{n_s} = \frac{n_s + n}{n_s} \approx 2$$

Približno 2 zato što se motor neposredno pre prespajanja vrteo skoro sinhronom brzinom
($n \approx n_s$, jer je klizanje u normalnom radu svega nekoliko procenata — sekcija 3.2), pa je
$(n_s + n)/n_s \approx 2n_s/n_s = 2$. Primer (ulaz u zadatak 56): $n_s = 750\ \mathrm{o/min}$,
$n_n = 718\ \mathrm{o/min}$:
$s_{\mathrm{koc}} = (750 + 718)/750 = 1{,}957$. Polje sada vuče rotor unazad — moment deluje
suprotno od obrtanja i mašina naglo koči (može i da se zaustavi i krene unazad, pa napajanje treba
isključiti u nuli brzine). Cena: pri $s \approx 2$ struje su ogromne (veće nego pri polasku!), a
prema $P_{\mathrm{Cu},r} = s\,P_{\mathrm{ob}}$ rotor guta i električnu i mehaničku snagu kao
toplotu. Zato se kod **namotanog rotora** u rotorsko kolo tada uključuje **dodatna otpornost**
$R_{r\mathrm{d}}$: ona ograniči struju i podesi kočioni moment na željenu vrednost (u zadatku 56:
na $130\ \%$ nazivnog), a mehanička karakteristika sa velikim rotorskim otporom postaje gotovo
prava linija ("meka" karakteristika). Ukupan rotorski otpor tada pišemo
$R_{r\Sigma} = R_r + R_{r\mathrm{d}}$ (svedeno: $R'_{r\Sigma} = m^2 R_{r\Sigma}$).

### 10.3. Dinamičko kočenje (kočenje jednosmernom strujom)

Stator se odvoji od naizmenične mreže i kroz njegove namotaje se propusti **jednosmerna struja**
$I_{\mathrm{DC}}$ (u nekoj od šema veze dve ili tri faze — zadatak 59 razmatra dve takve šeme).
Jednosmerna struja pravi **nepomično** magnetno polje. Rotor koji se još vrti seče to polje, u
njemu se indukuju struje, i one koče rotor — mašina radi kao generator čija se sva proizvodnja
(kinetička energija rotirajućih masa) troši na toplotu u rotorskom kolu. Kad se rotor zaustavi,
indukcije više nema i kočenje samo prestane — zato je ovo najelegantniji način zaustavljanja.

Koliku jednosmernu struju pustiti? Prirodan kriterijum (zadatak 59): da **magnetopobudna sila**
(mms, oznaka $\Theta$ — proizvod struje i broja navojaka, $\Theta = N\cdot I$ u amper-navojcima,
"koliko amper-navojaka tera fluks") jednosmernih struja bude jednaka mms-u koju u normalnom radu
pravi naizmenična struja praznog hoda $I_0$ — tada je i indukcija u mašini približno kao u praznom
hodu (ni premagnećeno, ni "prazno"). Izvedimo taj uslov za obe šeme vezivanja koje zadatak 59
razmatra.

**Referentni slučaj: mms trofaznog sistema u jednom "zamrznutom" trenutku.** Uhvatimo trenutak u
kojem je naizmenična struja faze U na svom vrhuncu: $i_U = I_m = \sqrt{2}\,I_0$ (amplituda!). Zbir
tri struje je nula, a druge dve faze su vremenski pomerene za $\pm 120^{\circ}$, pa je tada
$i_V = i_W = -I_m/2$ (jer je $\cos 120^{\circ} = -1/2$). Svaka faza pravi mms duž svoje ose
($\Theta_U$ — mms faze U, itd.), a ose su prostorno razmaknute po $120^{\circ}$. Projektujmo sve
na osu faze U: faza U daje $N I_m$; faze V i W nose po $N I_m/2$, a njihovi vektori (zbog
negativnog znaka struje okrenuti "ka" osi U) zaklapaju sa njom po $60^{\circ}$, pa svaka dodaje
$\frac{N I_m}{2}\cos 60^{\circ} = \frac{N I_m}{4}$. **Rezultantna mms** je:

$$\Theta_r = N I_m\left(1 + \tfrac{1}{4} + \tfrac{1}{4}\right) = \frac{3}{2}\,N I_m = \frac{3}{2}\,N\sqrt{2}\,I_0$$

To je poznati rezultat "rezultantna mms trofaznog namotaja je $3/2$ amplitude mms-a jedne faze"
(u zbirci jednačina (59.1): $\Theta_r = \frac{3}{2}\Theta_U$). Ovaj broj je naša "meta" — toliku
mms jednosmerne struje treba da naprave.

**Šema (a): jedna faza redno sa paralelnom vezom druge dve.** Kroz fazu U teče cela struja
$I_{\mathrm{DC}}$, a kroz V i W po $I_{\mathrm{DC}}/2$ — *identičan raspored struja po fazama kao
u zamrznutom trenutku iznad!* Zato je, istim računom, $\Theta_{\mathrm{DC}} = \frac{3}{2}N I_{\mathrm{DC}}$,
i uslov jednakosti mms-ova glasi:

$$\frac{3}{2}\,N\,I_{\mathrm{DC}} = \frac{3}{2}\,N\,\sqrt{2}\,I_0 \quad\Longrightarrow\quad I_{\mathrm{DC}} = \sqrt{2}\cdot I_0$$

Faktor $\sqrt{2}$ dolazi otuda što se jednosmerna (konstantna) struja poredi sa **amplitudom**
naizmenične, a $I_0$ je efektivna vrednost. Potreban napon izvora je mali — nepomično polje ne
indukuje protivelektromotornu silu u statoru, pa izvor savlađuje samo omski otpor namotaja. Otpor
koji izvor "vidi" u šemi (a): faza U redno sa paralelnom vezom V i W, dakle
$R_s + (R_s \parallel R_s) = R_s + \frac{R_s}{2} = \frac{3}{2}R_s$, pa je:

$$U_{\mathrm{DC}} = I_{\mathrm{DC}}\cdot\frac{3}{2}R_s$$

**Šema (b): dve faze redno, treća slobodna.** Kroz faze U i V teče ista struja $I_{\mathrm{DC}}$.
Njihovi mms vektori sada zaklapaju $60^{\circ}$ (ne $120^{\circ}$ — struja kroz drugu fazu teče
"unatrag" u odnosu na referentni smer, što njen vektor obrne za $180^{\circ}$), pa je rezultanta
dijagonala romba: $\Theta_{\mathrm{DC}} = 2\,N I_{\mathrm{DC}}\cos 30^{\circ} = \sqrt{3}\,N I_{\mathrm{DC}}$.
Uslov:

$$\sqrt{3}\,N\,I_{\mathrm{DC}} = \frac{3}{2}\,N\,\sqrt{2}\,I_0 \quad\Longrightarrow\quad I_{\mathrm{DC}} = \frac{3}{2\sqrt{3}}\cdot\sqrt{2}\,I_0 = \sqrt{\frac{3}{2}}\cdot I_0 \approx 1{,}22\,I_0$$

a napon je $U_{\mathrm{DC}} = I_{\mathrm{DC}}\cdot 2R_s$ (dve faze redno).

**Snaga jednosmernog izvora** je $P_{\mathrm{DC}} = U_{\mathrm{DC}}\cdot I_{\mathrm{DC}}$, i tu se
krije elegantna provera — obe šeme daju *istu* snagu:

$$\text{(a): } P_{\mathrm{DC}} = \frac{3}{2}R_s\left(\sqrt{2}\,I_0\right)^2 = 3\,I_0^2 R_s, \qquad
\text{(b): } P_{\mathrm{DC}} = 2R_s\left(\sqrt{\tfrac{3}{2}}\,I_0\right)^2 = 3\,I_0^2 R_s$$

A $3 I_0^2 R_s = q_s I_0^2 R_s$ su tačno **gubici u bakru statora pri praznom hodu** — logično:
izvor plaća samo statorsku toplotu, a za isto polje treba ista "magnetna investicija", ma kako se
struja raspodelila po fazama. Brojke iz zadatka 59 ($I_0 = 22{,}17\ \mathrm{A}$): šema (a) daje
$I_{\mathrm{DC}} = 31{,}35\ \mathrm{A}$ i $U_{\mathrm{DC}} = 10{,}7\ \mathrm{V}$, šema (b)
$I_{\mathrm{DC}} = 27{,}15\ \mathrm{A}$ i $U_{\mathrm{DC}} = 12{,}3\ \mathrm{V}$; snaga je u oba
slučaja $P_{\mathrm{DC}} \approx 335\ \mathrm{W}$ — smešno malo za mašinu koja inače radi na
$380\ \mathrm{V}$. Baš zato je dinamičko kočenje tako jednostavno za izvedbu (invertorima posebno
zgodno). Jedna ograda iz zbirke: tokom samog kočenja indukcija ipak neće ostati baš kao u praznom
hodu, jer polje rotorskih struja dodatno slabi ukupno polje — stvarne struje pri kočenju su zato
nešto veće od ovako izračunatih.

---

## 11. Upravljanje brzinom

Iz $n = (1-s)\cdot n_s = (1-s)\cdot\dfrac{60 f_s}{p}$ vidi se da na brzinu možemo uticati kroz
tri "poluge": broj pari polova $p$, klizanje $s$ i frekvenciju $f_s$.

### 11.1. Promena broja pari polova

Ako se statorski namotaj izvede tako da mu se prespajanjem menja $p$ (npr. Dahlanderova sprega
daje $p$ i $2p$), sinhrona brzina skače između diskretnih vrednosti sa lestvice iz sekcije 2.2
(npr. $3000/1500\ \mathrm{o/min}$). Robusno, ali **stepenasto** — nema kontinualne regulacije.
Koristi se npr. kod ventilatora i liftova sa dve brzine.

### 11.2. Promena klizanja

Pri fiksnom $n_s$ brzina se može smanjiti povećanjem klizanja: **dodatnim otporom u rotoru**
(samo namotani rotor; $s_{\mathrm{pr}} \propto R'_{r\Sigma}$ pa se radni deo karakteristike
"polegne", a radna tačka za isti teret sklizne na niže brzine) ili **snižavanjem napona**
($M \propto U^2$ obara krivu, pa presek sa teretom beži ka većem $s$). Obe varijante su
**energetski rasipne**: po zlatnoj podeli $P_{\mathrm{Cu},r} = s\,P_{\mathrm{ob}}$, koliko klizanje
— toliki procenat snage obrtnog polja završi kao toplota. Za trajni pogon na pola brzine bacala bi
se polovina snage. Zato je ovo danas pomoćna, a ne glavna metoda.

### 11.3. Promena frekvencije uz $U/f = \mathrm{const}$ (skalarno upravljanje)

Frekventni pretvarač može statoru da nametne proizvoljnu frekvenciju $f_s$ — time se $n_s$, a s
njim i cela momentna karakteristika, **kontinualno klizi levo-desno** po osi brzine. Ali frekvencija
se ne sme menjati sama: **napon mora da je prati**, tako da je

$$\frac{U_{sf}}{f_s} = \mathrm{const} = \frac{U_{sfn}}{f_{sn}}$$

**Zašto se fluks drži konstantnim — poreklo pravila.** Indukovani napon u statorskom namotaju
(zanemarimo li mali pad na $R_s$ i $X_{\gamma s}$, on je približno jednak priključenom naponu)
vezan je za fluks poznatom transformatorskom formulom:

$$U_{sf} \approx E_s = 4{,}44\cdot f_s\cdot N_s k_{ns}\cdot \Phi_{\mathrm{max}}$$

gde je $N_s k_{ns}$ efektivni broj navojaka statorske faze (broj navojaka puta navojni sačinilac),
$\Phi_{\mathrm{max}}$ amplituda glavnog fluksa, a $4{,}44 \approx 2\pi/\sqrt{2}$ konstanta koja
dolazi od prelaska sa amplitude izvoda sinusnog fluksa na efektivnu vrednost napona. Odavde:

$$\Phi_{\mathrm{max}} \approx \frac{U_{sf}}{4{,}44\, f_s\, N_s k_{ns}} \propto \frac{U_{sf}}{f_s}$$

**Fluks je srazmeran količniku $U/f$.** Držimo li $U/f$ konstantnim, fluks ostaje na projektovanoj
vrednosti — a to želimo iz dva razloga. Ako bi fluks porastao (napon prevelik za datu frekvenciju),
gvožđe ulazi u **zasićenje**: struja magnećenja eksplodira, gubici u gvožđu takođe — motor
pregoreva. Ako bi fluks opao, motor po amperu struje pravi manje momenta — traći se strujna
"nosivost" mašine. Konstantan fluks = maksimalan moment po amperu, bez pregrevanja.

Posledice koje zadaci 50–52 direktno koriste (uz zanemaren $R_s$):

1. **Prevalni moment je konstantan u celom opsegu** ispod nazivne frekvencije, jer
   $M_{\mathrm{pr}} \propto (U_{sf}/f_s)^2$ (sekcija 6.3). Kriva se translira po osi brzine ne
   menjajući visinu vrha.
2. **Apsolutno klizanje pri istom teretu je isto na svim frekvencijama.** Dokaz: na radnom delu
   je $M \approx 2M_{\mathrm{pr}}\,s/s_{\mathrm{pr}}$ (sekcija 8). Raspišimo
   $\dfrac{s}{s_{\mathrm{pr}}} = \dfrac{\Delta n/n_s}{R'_r/X_k} = \Delta n\cdot\dfrac{X_k}{n_s R'_r}$,
   a $\dfrac{X_k}{n_s} = \dfrac{2\pi f_s (L_{\gamma s}+L'_{\gamma r})}{60 f_s/p} = \dfrac{\pi\, p\,(L_{\gamma s}+L'_{\gamma r})}{30}$
   — frekvencija se skratila! Dakle $M$ zavisi samo od $\Delta n$: isti teret → isto
   $\Delta n = s\cdot n_s$ na svakoj frekvenciji. Radni recept iz zadataka 51 i 52: izračunaj
   $\Delta n$ na nazivnoj frekvenciji (Klosom), pa za traženu brzinu $n$ stavi
   $n_{sa} = n + \Delta n$, odakle je $f_{sa} = f_{sn}\cdot n_{sa}/n_{s}$ i
   $U_{sa} = U_{sn}\cdot f_{sa}/f_{sn}$. Isti recept, primenjen na polazak: za start sa
   maksimalnim ubrzanjem prevalna tačka treba da padne u $n = 0$, tj. $n_{sb} = \Delta n_{\mathrm{pr}}
   = s_{\mathrm{pr}}\, n_s$, što daje $f_{sb} = s_{\mathrm{pr}}\cdot f_{sn}$ (zadatak 52b:
   $20\ \mathrm{Hz}$ i $152\ \mathrm{V}$ — izvedeno u sekciji 9).
3. **Primer skaliranja napona:** motor $220\ \mathrm{V}$, $50\ \mathrm{Hz}$ na $25\ \mathrm{Hz}$
   dobija $U = 220\cdot 25/50 = 110\ \mathrm{V}$.

**Bazni opseg i slabljenje polja.** Pravilo $U/f = \mathrm{const}$ važi do nazivne frekvencije
(**bazni opseg**). Iznad nje napon ne sme preko nazivnog (izolacija, naponski limit pretvarača),
pa se drži $U = U_n = \mathrm{const}$ dok $f_s$ raste — fluks tada **opada** kao $1/f_s$ (oblast
**slabljenja polja**). Prevalni moment tu opada kao
$M_{\mathrm{pr}} \propto 1/f_s^2$:

$$\frac{M_{\mathrm{pr}1}}{M_{\mathrm{pr}n}} = \left(\frac{f_{sn}}{f_{s1}}\right)^2$$

(npr. za $f_{s1} = 70\ \mathrm{Hz}$: $(50/70)^2 = 0{,}51$ — zadatak 50), a prevalno klizanje kao
$s_{\mathrm{pr}} \propto 1/f_s$ (npr. $s_{\mathrm{pr}1} = \frac{50}{70}\cdot 0{,}192 = 0{,}137$).
Brzina se tako može podizati iznad nazivne sve dok opadajući $M_{\mathrm{pr}}$ ne padne na moment
tereta — to je granica koju traži zadatak 51b.

---

## 12. Monofazni asinhroni motor

### 12.1. Pulsirajuće polje i dvopoljna (Leblanova) teorija

Monofazni motor ima na statoru (u osnovnoj varijanti) **jedan** namotaj priključen na monofazni
napon. Jedan namotaj sa naizmeničnom strujom ne pravi obrtno, nego **pulsirajuće** polje: polje
fiksnog pravca čija jačina osciluje sinusno (kao opruga koja se steže i rasteže duž jedne ose).

**Leblanova teorema:** pulsirajuće polje amplitude $B_m$ matematički je identično zbiru **dva
obrtna polja** amplitude $B_m/2$ koja rotiraju sinhronom brzinom u **suprotnim smerovima**.
(Provera intuicijom: u trenutku kad su oba obrtna vektora poklopljena, zbir je pun $B_m$ duž ose;
četvrt periode kasnije pokazuju suprotno jedan od drugog i zbir je nula — baš kako pulsirajuće
polje diše.) Polje koje rotira u smeru vrtenja rotora zovemo **direktno**, a suprotno **inverzno**.

Klizanje se sada definiše prema svakom polju posebno. Prema direktnom polju (brzina $+n_s$):

$$s_d = \frac{n_s - n}{n_s} = s$$

Prema inverznom polju (brzina $-n_s$):

$$s_i = \frac{-n_s - n}{-n_s} = \frac{n_s + n}{n_s} = \frac{n_s + (1-s)\,n_s}{n_s} = 2 - s$$

(u srednjem koraku smo i brojilac i imenilac podelili sa $-1$, pa uvrstili $n = (1-s)n_s$).
Zapamti par: **direktno polje "vidi" klizanje $s$, inverzno polje "vidi" klizanje $2-s$.** Isti par
klizanja pojavljuje se i kod trofaznog motora kome je otpala jedna faza (zadatak 57) i kod
protivstrujnog kočenja ($s_{\mathrm{koc}} \approx 2 - s$, sekcija 10.2) — to je jedna te ista
matematika.

### 12.2. Zašto nema polaznog momenta — i zašto se ipak vrti kad ga zavrtiš

Svako od dva polja pravi svoj moment po običnoj trofaznoj teoriji: direktno $M_d$ (u smeru $+$),
inverzno $M_i$ (u smeru $-$). Rezultantni moment je razlika:

$$M = M_d(s) - M_i(2-s)$$

**Pri mirovanju** je $s = 1$, pa je i $2 - s = 1$: oba polja vide potpuno isto klizanje, prave
jednake momente u suprotnim smerovima, i rezultanta je **nula** — monofazni motor **nema polazni
moment**. Vuku ga dva jednaka konja na suprotne strane.

**Čim se rotor pokrene** (mehanički, ili pomoćnom fazom), simetrija puca. Recimo da se zavrti u
direktnom smeru: klizanje prema direktnom polju opadne ($s < 1$) — rotorske struje direktnog
sistema postanu sporije (manja $f_r$), njihova induktivna otpornost opadne i aktivna komponenta
struje (ona koja pravi moment) poraste. Prema inverznom polju je obrnuto: $2 - s > 1$, frekvencija
i induktivna otpornost porastu, aktivna komponenta opadne. Direktni moment prevagne i motor sam
nastavlja da se ubrzava u smeru u kom je gurnut. Karakteristika $M(s)$ monofaznog motora prolazi
kroz nulu u $s = 1$, a radni deo joj je sličan trofaznom — uz nešto **veće nazivno klizanje** i
lošije performanse, jer inverzno polje stalno pravi protivmoment i dodatne gubitke.

**Ekvivalentna šema — šta se tačno polovi i zašto.** Pošto rotor istovremeno kliže prema oba
polja, motor se modeluje kao **redna veza dve ekvivalentne šeme**: direktne, sa rotorskim otporom
podeljenim klizanjem $s$ (njena puna impedansa je $Z_d$), i inverzne, sa otporom podeljenim sa
$2-s$ (impedansa $Z_i$). Kod *čistog monofaznog motora* sa jednim namotajem svaki element pritom
ulazi sa **polovinom** svoje vrednosti: direktna polovina šeme je redno
$\frac{1}{2}R_s$ i $\frac{1}{2}X_{\gamma s}$, pa poprečno $\frac{1}{2}X_m$ paralelno sa granom
$\frac{1}{2}X'_{\gamma r} + \frac{1}{2}\frac{R'_r}{s}$; ispod nje je ista takva inverzna polovina,
samo sa $2-s$ umesto $s$ (slika 58.4 u zbirci). Zašto baš polovina: po Leblanovoj teoremi svako od
dva obrtna polja nosi po **pola amplitude** pulsirajućeg polja, pa jednom jedinom (istom!) namotaju
po pola njegove impedanse "pripada" svakom od dva sistema; ukupno je
$U = I\cdot\frac{1}{2}(Z_d + Z_i)$.

Na sličnu šemu svodi se i **trofazni motor kome je otpala jedna faza** (zadatak 57) — on tada radi
kao monofazni — ali sa dve bitne razlike na koje treba dobro paziti:

1. **Napon je linijski.** Kod sprege Y preostale dve zdrave faze ostaju *redno* vezane između dva
   fazna provodnika mreže, pa ih tera **linijski (međufazni) napon**: u zadatku 57 se uvršta
   $U_{\mathrm{lin}} = 380\ \mathrm{V}$, ne fazni $220\ \mathrm{V}$. Struja kroz obe faze je:

$$I = \frac{U_{\mathrm{lin}}}{Z_d + Z_i}$$

   Uz zanemarenu granu magnećenja (tako radi zadatak 57: $X_m \to \infty$, sekcija 4.5) impedanse
   se pišu eksplicitno kao
   $Z_d = R_s + j\left(X_{\gamma s} + X'_{\gamma r}\right) + \dfrac{R'_r}{s}$ i
   $Z_i = R_s + j\left(X_{\gamma s} + X'_{\gamma r}\right) + \dfrac{R'_r}{2-s}$ — ovde **nema
   polovljenja**, jer svaka od dve redno vezane faze unosi svoju punu impedansu (jedna "igra" za
   direktni, druga za inverzni sistem). U zbiru se zato javljaju $2R_s$, $2X_{\gamma s}$ i
   $2X'_{\gamma r}$, tačno kao u rešenju zadatka 57:

$$I = \frac{U_{\mathrm{lin}}}{\sqrt{\left(2R_s + \dfrac{R'_r}{s} + \dfrac{R'_r}{2-s}\right)^2 + \left(2X_{\gamma s} + 2X'_{\gamma r}\right)^2}}$$

2. **Nema faktora $q_s = 3$.** Struja je *jedna* i teče kroz redno vezane namotaje, pa se snage
   obrtnog polja računaju **bez** faktora 3 (zbirka na to izričito upozorava: "nema faktora 3 jer
   je u pitanju monofazan rad") — za razliku od trofazne definicije iz sekcije 5:

$$P_{\mathrm{ob},d} = I^2\cdot\frac{R'_r}{s}, \qquad P_{\mathrm{ob},i} = I^2\cdot\frac{R'_r}{2-s}$$

Moment je razlika direktnog i inverznog doprinosa, po već poznatom pravilu "moment = snaga obrtnog
polja podeljena sinhronom ugaonom brzinom":

$$M = \frac{P_{\mathrm{ob},d} - P_{\mathrm{ob},i}}{\Omega_s}$$

Ko po navici iz sekcije 5 ubaci i trojku, dobiće trostruko veći moment: u zadatku 57 bi umesto
$163{,}7\ \mathrm{Nm}$ izašlo nemogućih $\approx 491\ \mathrm{Nm}$ — više nego što motor razvija sa
sve tri faze!

### 12.3. Pomoćna faza i kondenzator

Da bi motor krenuo sam, treba mu pri polasku napraviti **obrtno** polje. Rešenje: na stator se,
prostorno pomereno za $90^{\circ}$ od **glavne faze** (namotaj impedanse $Z_g = R_g + jX_g$),
doda **pomoćna faza** (namotaj impedanse $Z_p = R_p + jX_p$), a u red sa pomoćnom fazom veže se
element koji njenoj struji promeni fazni stav — najčešće **kondenzator** (ređe otpornik ili
prigušnica). Dve struje pomerene u vremenu kroz dva namotaja pomerena u prostoru — to je isti
recept kojim trofazni sistem pravi obrtno polje, samo sa dve "faze".

**Fazni uslov obrtnog polja:** struje glavne i pomoćne faze treba da
budu fazno pomerene za $90^{\circ}$:

$$\varphi_g - \varphi_p = 90^{\circ}$$

gde su $\varphi_g = \arctan(X_g/R_g)$ i $\varphi_p$ fazni stavovi struja prema naponu. Kondenzator
u pomoćnoj grani menja njenu reaktansu u $X_p + X_C$, gde je reaktansa kondenzatora negativna:

$$X_C = -\frac{1}{\omega C} = -\frac{1}{2\pi f\, C}$$

pa se iz traženog $\varphi_p$ preko $\tan\varphi_p = (X_p + X_C)/R_p$ izračuna $X_C$, a iz njega
kapacitivnost $C$ — tačno postupak zadatka 58. Strogo uzevši, fazni pomeraj od $90^{\circ}$ je
*potreban, ali ne i dovoljan* uslov savršeno kružnog polja: zbirka navodi da za punu simetriju
treba još i da struje glavne i pomoćne faze proizvode **jednake magnetopobudne sile** (amplitudski
uslov) i da imaju isti fazni stav prema svojim naponima. U zadatku 58 se podešava samo fazni
uslov, pa se — kako i sama postavka kaže — dobija tek "približno simetrično" polje. Ako fazni
uslov od $90^{\circ}$ uopšte nije pogođen, polje
nije kružno nego **elipsoidno** (obrtno polje promenljivog intenziteta): ono i dalje vrti rotor,
ali sadrži i inverznu komponentu sa njenim gubicima. Kondenzator se može izabrati da simetriju da
tačno u jednom režimu — ili pri polasku (**startni kondenzator**, isključuje se po zaletu
centrifugalnim prekidačem) ili u nazivnom radu (**pogonski kondenzator**, trajno uključen). Dve
praktične napomene, obe iz zbirke (zadatak 58): pogonski kondenzator je orijentaciono $25$ do
$55\ \mu\mathrm{F}$ po $\mathrm{kW}$ snage motora za mrežu od $230\ \mathrm{V}$; i — napon na
kondenzatoru je znatno viši od mrežnog (fazorski se sabira sa naponom namotaja), pa se za mrežu od
$230\ \mathrm{V}$ biraju kondenzatori nazivnog napona $450$ do $550\ \mathrm{V}$.

---

## 13. Najčešće greške u celoj oblasti — čeklista pred zadatke

Pre nego što kreneš na zadatke, evo spiska grešaka koje se na ovom gradivu najčešće prave. Svaka
je već objašnjena u svojoj sekciji — ovde su skupljene na jedno mesto, da ih pregledaš pre (i
posle) svakog rešavanja.

1. **Mešanje dve "omege".** Električna $\omega_s = 2\pi f_s$ služi za reaktanse
   ($X = \omega_s L$); mehanička $\Omega_s = 2\pi f_s/p$ za momente ($M = P_{\mathrm{ob}}/\Omega_s$).
   Za $p = 1$ su brojno iste, pa greška prolazi nekažnjeno; za $p \ne 1$ moment ispadne $p$ puta
   pogrešan. (Sekcija 2.3.)
2. **$n_n$ umesto $n_s$ u imeniocu klizanja.** Uvek je $s = (n_s - n)/n_s$ — u imeniocu stoji
   *sinhrona* brzina. Da je zamka realna, pokazuje i sama zbirka: na str. 174, u formuli za $s_n$,
   štamparski stoji $n_n$ u imeniocu, ali je račun (ispravno) izveden sa $n_s = 1500$.
   > **Napomena o originalu:** to je štamparski lapsus u zbirci, ne druga definicija klizanja —
   > brojčani rezultat $s_n = 0{,}04$ odgovara deljenju sa $n_s$.
3. **Linijski umesto faznog napona.** U formule za snagu i moment ulazi *fazni* napon $U_{sf}$:
   kod sprege Y prvo podeli linijski sa $\sqrt{3}$ (zadatak 52: $380 \to 220\ \mathrm{V}$), kod Δ
   je $U_{sf} = U_s$ (zadatak 51). Jedini slučaj u kojem se koristi baš linijski napon je ispad
   jedne faze (zadatak 57) — tamo su dve faze redno vezane na međufazni napon. (Sekcije 1 i 12.2.)
4. **$P_n$ sa pločice je mehanička (korisna) snaga**, ne električna ulazna:
   $M_n = P_n/\Omega_n$. Ko uzme $P_n$ za $P_{\mathrm{ul}}$, prećutno je "poklonio" motoru stepen
   iskorišćenja 1. (Sekcija 5.1.)
5. **Pogrešan koren Klosove kvadratne jednačine.** Jednačina uvek daje dva rešenja, po jedno sa
   svake strane prevala; proveri koje ima fizičkog smisla: radna tačka → manje od
   $s_{\mathrm{pr}}$; $s_{\mathrm{pr}}$ iz nazivne tačke → veće od $s_n$; $s_{\mathrm{pr}}$ iz
   polazne tačke → manje od 1. (Sekcije 7.2 i 9.)
6. **Faktor 3 u monofaznom radu.** Kod monofaznog motora i kod trofaznog kome je otpala faza
   snage obrtnog polja se računaju **bez** $q_s = 3$ — struja je jedna i teče kroz redno vezane
   namotaje. (Sekcija 12.2.)
7. **Zaboravljanje da se reaktanse menjaju sa frekvencijom.** Pri svakoj promeni $f_s$ menjaju se
   i sve reaktanse, $X = 2\pi f_s L$ — dakle i $X_k$ i $X_m$; zato je
   $s_{\mathrm{pr}} \propto 1/f_s$ i zato u zadatku 55 uslov maksimuma određuje *frekvenciju*.
   Otpornosti ($R_s$, $R'_r$) od frekvencije ne zavise. (Sekcije 6.2 i 6.4.)
8. **Brkanje svedenih i nesvedenih rotorskih veličina.** Prim znači "svedeno na stator" (faktor
   $m^2$ za otpornosti *i* reaktanse). Rezultat koji se tiče stvarnog rotorskog kola (zadatak 56)
   na kraju vrati deljenjem sa $m^2$. (Sekcija 4.2.)

---

## 14. Rečnik oznaka

Sve oznake koje ćeš sresti u zadacima 50–59, na jednom mestu. Prim ($'$) uvek znači "svedeno na
stator"; indeks $\mathrm{n}$ znači "nazivno" (vrednost iz nazivnog režima, sa natpisne pločice).

| Oznaka | Šta označava | Jedinica |
|---|---|---|
| $n_s$ | sinhrona brzina obrtnog polja, $n_s = 60 f_s/p$ | $\mathrm{o/min}$ ($=\mathrm{min^{-1}}$) |
| $n$ | brzina obrtanja rotora, $n = (1-s)\,n_s$ | $\mathrm{o/min}$ |
| $n_n$ | nazivna brzina rotora | $\mathrm{o/min}$ |
| $\Delta n$, $n_k$ | apsolutno klizanje, $\Delta n = n_s - n = s\,n_s$ | $\mathrm{o/min}$ |
| $p$ | broj pari polova | — |
| $q_s$, $q_r$ | broj faza statora odn. rotora (trofazni: $q_s = 3$) | — |
| $f_s$, $f_{sn}$ | frekvencija statorskog napajanja; nazivna | $\mathrm{Hz}$ |
| $f_r$ | frekvencija rotorskih veličina, $f_r = s\,f_s$ | $\mathrm{Hz}$ |
| $\omega_s$ | električna ugaona učestanost, $\omega_s = 2\pi f_s$ | $\mathrm{rad/s}$ |
| $\Omega_s$ | mehanička sinhrona ugaona brzina, $\Omega_s = 2\pi n_s/60 = 2\pi f_s/p$ (u zbirci ponegde pisana $\omega_s$) | $\mathrm{rad/s}$ |
| $\Omega$, $\Omega_n$ ($\omega_n$) | mehanička ugaona brzina rotora, $2\pi n/60$; nazivna | $\mathrm{rad/s}$ |
| $s$ | klizanje, $s = (n_s - n)/n_s$ | — (ili $\%$) |
| $s_n$ | nazivno klizanje | — |
| $s_{\mathrm{pr}}$ | prevalno klizanje, $s_{\mathrm{pr}} = \pm R'_r/X_k$ | — |
| $s_t$, $s_T$ | klizanje u stacionarnoj radnoj tački pri teretu $M_t$ ($M_T$) | — |
| $s_{\mathrm{koc}}$ | klizanje na početku protivstrujnog kočenja, $(n_s+n)/n_s$ | — |
| $s_d$, $s_i$ | klizanje prema direktnom ($=s$) odn. inverznom ($=2-s$) polju | — |
| $U_s$, $U_{sf}$ | linijski odn. fazni napon statora (Y: $U_s = \sqrt{3}\,U_{sf}$; Δ: $U_{sf}=U_s$) | $\mathrm{V}$ |
| $U_{sn}$, $U_{sfn}$ | nazivni linijski odn. fazni napon | $\mathrm{V}$ |
| $U_{\mathrm{DC}}$, $I_{\mathrm{DC}}$, $P_{\mathrm{DC}}$ | napon, struja i snaga jednosmernog izvora pri dinamičkom kočenju ($P_{\mathrm{DC}} = U_{\mathrm{DC}} I_{\mathrm{DC}} = 3 I_0^2 R_s$, sekcija 10.3) | $\mathrm{V}$, $\mathrm{A}$, $\mathrm{W}$ |
| $E_s$ | indukovani napon (ems) statorske faze, $\approx 4{,}44 f_s N_s k_{ns}\Phi_{\mathrm{max}}$ | $\mathrm{V}$ |
| $\Phi_{\mathrm{max}}$ | amplituda glavnog magnetnog fluksa | $\mathrm{Wb}$ |
| $N_s k_{ns}$ | efektivni broj navojaka statorske faze | — |
| $I_s$, $I_{sf}$ | statorska struja (linijska odn. fazna) | $\mathrm{A}$ |
| $I'_r$, $I'_{rf}$ | svedena rotorska struja (po fazi) | $\mathrm{A}$ |
| $I_{\mu}$ | struja magnećenja (kroz $X_m$) | $\mathrm{A}$ |
| $I_0$, $I_{sf0}$ | struja praznog hoda | $\mathrm{A}$ |
| $I'_{rk}$, $I'_{rn}$ | polazna odn. nazivna (svedena) rotorska struja (sekcija 7.3) | $\mathrm{A}$ |
| $R_s$ | otpornost statorskog namotaja po fazi | $\Omega$ |
| $X_{\gamma s}$, $L_{\gamma s}$ | rasipna reaktansa odn. induktivnost statora | $\Omega$, $\mathrm{H}$ |
| $R_r$, $R'_r$ | otpornost rotora po fazi; svedena na stator ($R'_r = m^2 R_r$) | $\Omega$ |
| $X_{\gamma r}$, $X'_{\gamma r}$, $L'_{\gamma r}$ | rasipna reaktansa rotora; svedena; svedena induktivnost | $\Omega$, $\Omega$, $\mathrm{H}$ |
| $R'_r/s$ | fiktivni otpor koji predstavlja ukupnu snagu predatu rotoru | $\Omega$ |
| $X_m$, $L_m$ | reaktansa odn. induktivnost magnećenja | $\Omega$, $\mathrm{H}$ |
| $R_m$ | otpornost koja predstavlja gubitke u gvožđu | $\Omega$ |
| $X_k$ | kratkospojna reaktansa, $X_k = X_{\gamma s} + X'_{\gamma r}$ | $\Omega$ |
| $m$ | prenosni odnos (koeficijent transformacije) stator/rotor | — |
| $\sigma$ | koeficijent rasipanja, $\sigma = 1 + X_{\gamma s}/X_m$ (sekcija 7.3; tačniji izrazi za rotorsku struju u zad. 53, 54) | — |
| $R_{r\mathrm{d}}$ | dodatna otpornost u rotorskom kolu (namotani rotor) | $\Omega$ |
| $R_{r\Sigma}$, $R'_{r\Sigma}$ | ukupna rotorska otpornost ($R_r + R_{r\mathrm{d}}$); svedena | $\Omega$ |
| $Z_d$, $Z_i$ | impedansa motora prema direktnom odn. inverznom polju | $\Omega$ |
| $Z_g$, $Z_p$ | impedansa glavne odn. pomoćne faze monofaznog motora | $\Omega$ |
| $X_C$, $C$ | reaktansa kondenzatora ($X_C = -1/\omega C$); kapacitivnost | $\Omega$, $\mathrm{F}$ |
| $\varphi_g$, $\varphi_p$ | fazni stav struje glavne odn. pomoćne faze prema naponu | $^{\circ}$ |
| $M$ | elektromagnetni (razvijeni) moment | $\mathrm{Nm}$ |
| $M_n$ | nazivni moment, $M_n = P_n/\Omega_n$ | $\mathrm{Nm}$ |
| $M_{\mathrm{pr}}$ | prevalni (maksimalni) moment | $\mathrm{Nm}$ |
| $M_k$ | polazni moment (pri $s=1$) | $\mathrm{Nm}$ |
| $M_t$, $M_T$, $M_{\mathrm{opt}}$ | moment opterećenja (otporni moment radne mašine); tri oznake za isto — $M_t$ iz zad. 51, $M_T$ iz zad. 52, $M_{\mathrm{opt}}$ iz zad. 50 | $\mathrm{Nm}$ |
| $M_{\mathrm{koc}}$ | kočioni moment | $\mathrm{Nm}$ |
| $M_d$, $M_i$ | moment direktnog odn. inverznog polja | $\mathrm{Nm}$ |
| $\nu$ | preopteretivost, $\nu = M_{\mathrm{pr}}/M_n$ (opštije $M_{\mathrm{pr}}/M$) | — |
| $\gamma$, $\nu_T$ | odnos $M_{\mathrm{pr}}/M_t$ (iste uloge kao $\nu$, oznake iz zad. 51 i 52) | — |
| $P_n$ | nazivna (korisna, mehanička) snaga motora | $\mathrm{W}$ |
| $P_{\mathrm{ul}}$ | ulazna električna snaga | $\mathrm{W}$ |
| $P_{\mathrm{Cu},s}$, $P_{\mathrm{Cu},r}$ | gubici u bakru statora odn. rotora ($P_{\mathrm{Cu},r} = s P_{\mathrm{ob}}$) | $\mathrm{W}$ |
| $P_{\mathrm{Fe}}$ | gubici u gvožđu | $\mathrm{W}$ |
| $P_{\mathrm{ob}}$ | snaga obrtnog polja (prelazi kroz zazor na rotor); $P_{\mathrm{ob},d}$, $P_{\mathrm{ob},i}$ — njeni direktni i inverzni deo | $\mathrm{W}$ |
| $P_{\mathrm{meh}}$ | mehanička snaga, $(1-s)P_{\mathrm{ob}}$ | $\mathrm{W}$ |
| $P_{\mathrm{tr,v}}$ | gubici trenja i ventilacije | $\mathrm{W}$ |
| $\eta$ | stepen iskorišćenja, $P_{\mathrm{kor}}/P_{\mathrm{ul}}$ | — |
| $\cos\varphi$ | faktor snage | — |
| $J$ | moment inercije obrtnih masa | $\mathrm{kg\,m^2}$ |
| $\Theta$ | magnetopobudna sila (mms), $\Theta = N\cdot I$; $\Theta_r$ rezultantna, $\Theta_U$ mms jedne faze (sekcija 10.3) | $\mathrm{A}$ (amper-navojci) |

Uz ovaj rečnik i sekcije iznad, spreman si za zadatke. Kreni od zadatka 50 — on je prirodan
nastavak sekcija 7 i 11.
