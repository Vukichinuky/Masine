# Zadatak 50 — Brzina motora dizalice pri U/f upravljanju (Klosova jednačina i slabljenje polja)

## Postavka

Trofazni asinhroni motor sa kaveznim rotorom ima natpisne podatke: $4\ \mathrm{kW}$, $380\ \mathrm{V}$, $9\ \mathrm{A}$, $1440\ \mathrm{min^{-1}}$, $50\ \mathrm{Hz}$, preopteretivost $\nu = M_{\mathrm{max}}/M_{\mathrm{n}} = 2{,}5$. Motor pokreće dizalicu čiji je moment stalan i iznosi $50\ \%$ nazivnog momenta motora. U cilju podešavanja brzine moguća je kontinualna promena učestanosti napajanja uz uslov $U/f = \mathrm{const.}$ Koristeći Klosovu jednačinu odrediti brzinu obrtanja motora ako je učestanost napona $70\ \mathrm{Hz}$.

> **Prevod na običan jezik:** Imamo običan kavezni asinhroni motor koji na natpisnoj pločici kaže: daje 4 kW na vratilu, vrti se 1440 obrtaja u minutu kada je priključen na mrežu 380 V, 50 Hz, i može kratkotrajno da razvije najviše 2,5 puta veći moment od nazivnog. Taj motor vuče dizalicu — a dizalica je „tvrdoglav" teret: traži uvek isti moment, koliko god se brzo vrtela, i to tačno polovinu nazivnog momenta motora. Motor ne napajamo direktno iz mreže, nego preko frekventnog pretvarača (uređaja koji može da menja i učestanost i napon), koji radi po pravilu „napon podeljen učestanošću = konstanta". Pitanje glasi: ako pretvarač podesimo na 70 Hz (dakle *iznad* mrežnih 50 Hz), kojom će se brzinom motor stvarno vrteti? Da bismo to izračunali, usput moramo naći nominalni i prevalni moment, nominalno i prevalno klizanje motora, i razumeti šta se dešava sa karakteristikom motora kada mu menjamo učestanost.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna snaga | $P_{\mathrm{n}}$ | $4\ \mathrm{kW}$ | Mehanička snaga koju motor trajno daje na vratilu u nazivnom režimu. |
| Nazivni napon | $U_{\mathrm{n}}$ | $380\ \mathrm{V}$ | Linijski (međufazni) napon za koji je motor projektovan. |
| Nazivna struja | $I_{\mathrm{n}}$ | $9\ \mathrm{A}$ | Struja koju motor vuče iz mreže u nazivnom režimu. |
| Nazivna brzina | $n_{\mathrm{n}}$ | $1440\ \mathrm{min^{-1}}$ | Brzina obrtanja rotora pri nazivnom opterećenju (obrtaja u minutu; isto što i „o/min"). |
| Nazivna učestanost | $f_{\mathrm{sn}}$ | $50\ \mathrm{Hz}$ | Učestanost napona napajanja statora za koju važe natpisni podaci. |
| Preopteretivost | $\nu = M_{\mathrm{max}}/M_{\mathrm{n}}$ | $2{,}5$ | Koliko puta je najveći (prevalni) moment motora veći od nazivnog momenta. |
| Moment tereta (dizalice) | $M_{\mathrm{opt}}$ | $0{,}5 \cdot M_{\mathrm{n}} = \mathrm{const.}$ | Dizalica traži stalno isti moment, nezavisno od brzine. Indeks „opt" je od „**opt**erećenje" (moment opterećenja) — ne od „optimalno"! |
| Nova učestanost napajanja | $f_{\mathrm{s1}}$ | $70\ \mathrm{Hz}$ | Učestanost na koju podešavamo pretvarač; tražimo brzinu pri njoj. |
| Zakon upravljanja | $U/f = \mathrm{const.}$ | do $f_{\mathrm{sn}}$ | Pretvarač menja napon srazmerno učestanosti — ali samo do nazivne učestanosti (videćemo zašto). |

Primetimo odmah: nazivni napon $380\ \mathrm{V}$ i nazivna struja $9\ \mathrm{A}$ u ovom zadatku se **ne koriste u računu** — dati su kao deo natpisne pločice radi potpunosti. Sve što nam treba izvešćemo iz snage, brzine, učestanosti i preopteretivosti, jer u Klosovoj jednačini napon nikad ne figuriše sam, nego samo kroz *odnose* momenata.

## Šta se traži i zašto

**1. Nominalni moment $M_{\mathrm{n}}$.** To je moment koji motor razvija na vratilu u nazivnom režimu. Inženjera zanima jer je to „radna valuta" motora — teret se uvek izražava u odnosu na njega (ovde: dizalica traži $0{,}5\,M_{\mathrm{n}}$). Dobijamo ga direktno iz nazivne snage i nazivne brzine.

**2. Prevalni (maksimalni) moment $M_{\mathrm{pr}}$.** Najveći moment koji motor uopšte može da razvije. Ako teret zatraži više od toga, motor „prevali" — naglo uspori i zaglavi se (otud ime). Inženjer ga mora znati da bi bio siguran da pogon neće stati. Dobijamo ga množenjem $M_{\mathrm{n}}$ preopteretivošću $\nu$.

**3. Nominalno klizanje $s_{\mathrm{n}}$.** Mera koliko rotor „kasni" za obrtnim poljem u nazivnom režimu. Računamo ga iz razlike sinhrone i nazivne brzine.

**4. Prevalno klizanje $s_{\mathrm{pr}}$.** Klizanje pri kome motor razvija prevalni moment — „vrh brda" na karakteristici momenta. Dobijamo ga iz Klosove jednačine primenjene na nazivnu radnu tačku.

**5. Brzina obrtanja $n_1$ pri $70\ \mathrm{Hz}$.** Ovo je glavno pitanje zadatka. Plan u pet poteza, običnim jezikom:

1. Iz natpisnih podataka nađemo $M_{\mathrm{n}}$, $M_{\mathrm{pr}}$, $s_{\mathrm{n}}$ i $s_{\mathrm{pr}}$ na $50\ \mathrm{Hz}$ — time potpuno „upoznamo" motor.
2. Shvatimo šta promena učestanosti radi karakteristici motora: prevalno klizanje opada kao $1/f_{\mathrm{s}}$, a prevalni moment — pažnja! — na $70\ \mathrm{Hz}$ *nije* isti kao na $50\ \mathrm{Hz}$, jer iznad nazivne učestanosti napon više ne može da prati učestanost (oblast *slabljenja polja*).
3. Izračunamo novo prevalno klizanje $s_{\mathrm{pr1}}$ i novi prevalni moment $M_{\mathrm{pr1}}$ na $70\ \mathrm{Hz}$.
4. Klosovom jednačinom nađemo klizanje $s_1$ pri kome novi „brežuljak" momenta seče horizontalnu liniju tereta $M_{\mathrm{opt}} = 0{,}5\,M_{\mathrm{n}}$.
5. Iz klizanja i nove sinhrone brzine izračunamo brzinu rotora $n_1$.

## Potrebna teorija — mini-lekcije

### 1. Obrtno polje, sinhrona brzina i klizanje

Kada trofazni namotaj statora priključimo na trofazni napon učestanosti $f_{\mathrm{s}}$, u mašini nastaje **obrtno magnetno polje** koje se vrti **sinhronom brzinom**:

$$n_{\mathrm{s}} = \frac{60 \cdot f_{\mathrm{s}}}{p}\ \left[\mathrm{min^{-1}}\right]$$

gde je $p$ **broj pari polova** namotaja (konstruktivna osobina motora — ceo broj: 1, 2, 3…), a faktor $60$ pretvara obrtaje u sekundi u obrtaje u minuti. Poreklo formule: polje napravi jedan pun obrtaj za $p$ perioda napona, pa se u sekundi obrne $f_{\mathrm{s}}/p$ puta.

Rotor asinhronog motora se u motorskom režimu **uvek vrti malo sporije** od polja — upravo ta razlika brzina indukuje struje u kaveznom rotoru, a te struje sa poljem stvaraju moment. Relativno zaostajanje merimo **klizanjem**:

$$s = \frac{n_{\mathrm{s}} - n}{n_{\mathrm{s}}}$$

Klizanje je bezdimenzioni broj: $s = 0$ znači da se rotor vrti sinhrono (tada nema indukovanih struja pa ni momenta), $s = 1$ znači da rotor stoji (polazak). Tipične nazivne vrednosti su svega nekoliko procenata. Iz definicije klizanja odmah sledi i obrnuta veza, koja nam treba na kraju zadatka:

$$n = (1 - s) \cdot n_{\mathrm{s}}$$

### 2. Moment iz snage: $M = P/\Omega$

Osnovna veza mehanike rotacije: snaga je proizvod momenta i ugaone brzine, $P = M \cdot \Omega$. Odatle je moment $M = P/\Omega$. Ugaona brzina $\Omega$ (u radijanima u sekundi) dobija se iz brzine obrtanja $n$ (u obrtajima u minuti) ovako: jedan obrtaj je $2\pi$ radijana, a minut je $60$ sekundi, pa je

$$\Omega = \frac{2\pi \cdot n}{60}\ \left[\mathrm{rad/s}\right]$$

Intuicija: snaga kaže *koliko posla* motor obavi u sekundi, moment kaže *koliko snažno uvrće* vratilo — pri istoj snazi, sporija mašina uvrće jače.

### 3. Karakteristika momenta, prevalni moment i preopteretivost

Ako nacrtamo moment motora $M$ u zavisnosti od klizanja $s$ (ili, ekvivalentno, od brzine $n$), dobijamo krivu oblika brežuljka: od $s = 0$ moment najpre raste približno linearno, dostiže maksimum — **prevalni moment** $M_{\mathrm{pr}}$ — pri **prevalnom klizanju** $s_{\mathrm{pr}}$, a zatim opada prema polaznoj tački $s = 1$.

Ta dva dela krive se suštinski razlikuju:

- **Stabilna grana** ($s < s_{\mathrm{pr}}$, blizu sinhrone brzine): ako teret na trenutak poraste, rotor malo uspori, klizanje poraste, a s njim i moment motora — motor se sam „uhvati" i uspostavi novu ravnotežu. Tu motor normalno radi.
- **Nestabilna grana** ($s > s_{\mathrm{pr}}$): tu veće klizanje znači *manji* moment — ako teret poraste, motor uspori, moment mu opadne, pa uspori još više… i zaglavi se. Na ovoj grani motor ne može trajno da radi.

**Preopteretivost** je odnos prevalnog i nazivnog momenta, $\nu_{\mathrm{n}} = M_{\mathrm{pr}}/M_{\mathrm{n}}$ — daje je proizvođač (ovde $2{,}5$). Opštije, preopteretivost prema *bilo kom* teretu $M$ je $\nu = M_{\mathrm{pr}}/M$; ona kaže koliko „rezerve" momenta pogon ima pre nego što prevali. Uslov da motor uopšte može da vuče teret je $\nu > 1$.

### 4. Klosova jednačina i njeno rešavanje (kvadratna jednačina)

Cela kriva momenta može se, uz uobičajena zanemarenja, opisati jednom jedinom formulom — **Klosovom jednačinom**:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}} \tag{50.2}$$

Poreklo: formula se dobija kada se tačan izraz za moment (mini-lekcija 5, jednačina (50.6)) podeli sopstvenim maksimumom — pri tom deljenju se svi parametri mašine (otpori, reaktanse, napon) skrate, i ostane samo odnos $s/s_{\mathrm{pr}}$. Zato je Klosova jednačina tako moćna: **cela statička karakteristika zavisi samo od dva broja** — $M_{\mathrm{pr}}$ i $s_{\mathrm{pr}}$ — koje umemo da nađemo iz natpisnih podataka. Ne trebaju nam ni otpori ni reaktanse motora!

Provera intuicije: za $s = s_{\mathrm{pr}}$ imenilac je $1 + 1 = 2$, pa je $M = M_{\mathrm{pr}}$ — vrh brežuljka, tačno kako treba. Za vrlo malo $s$ dominira član $s_{\mathrm{pr}}/s$ (veliki), pa je $M$ mali — takođe tačno.

**Kako se iz Klosove jednačine „izvlači" klizanje.** U stacionarnom (ustaljenom) pogonu motor razvija tačno onoliki moment koliki teret traži: $M = M_{\mathrm{opt}}$. Klosova jednačina za tu radnu tačku glasi:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}}$$

Unakrsnim množenjem (imenilac leve strane množi brojilac desne i obrnuto):

$$\frac{s}{s_{\mathrm{pr}}} + \frac{s_{\mathrm{pr}}}{s} = 2\,\frac{M_{\mathrm{pr}}}{M}$$

Pomnožimo obe strane sa $s \cdot s_{\mathrm{pr}}$ da se otarasimo razlomaka (prvi član daje $s^2$, drugi $s_{\mathrm{pr}}^2$, desna strana $2\,\dfrac{M_{\mathrm{pr}}}{M}\, s\, s_{\mathrm{pr}}$), pa sve prebacimo na levu stranu:

$$s^2 - 2\,\frac{M_{\mathrm{pr}}}{M} \cdot s \cdot s_{\mathrm{pr}} + s_{\mathrm{pr}}^2 = 0 \tag{50.3}$$

(Original u (50.3) umesto $M$ piše $M_{\mathrm{ob}}$ — moment opterećenja; to je isti moment, jer u stacionarnom stanju motor razvija baš onoliko koliko teret traži.) Odnos $M_{\mathrm{pr}}/M$ je preopteretivost prema stvarnom teretu — tek kad uvedemo oznaku $\nu = M_{\mathrm{pr}}/M$, jednačina (50.3) postaje kompaktna:

$$s^2 - 2\nu \cdot s \cdot s_{\mathrm{pr}} + s_{\mathrm{pr}}^2 = 0 \tag{50.4}$$

Ovo je obična kvadratna jednačina po $s$ (koeficijenti: $a = 1$, $b = -2\nu s_{\mathrm{pr}}$, $c = s_{\mathrm{pr}}^2$). Rešimo je standardnom formulom $s = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a}$:

$$s_{1,2} = \frac{2\nu s_{\mathrm{pr}} \pm \sqrt{4\nu^2 s_{\mathrm{pr}}^2 - 4 s_{\mathrm{pr}}^2}}{2} = \nu s_{\mathrm{pr}} \pm s_{\mathrm{pr}}\sqrt{\nu^2 - 1}$$

odnosno, kad izvučemo $s_{\mathrm{pr}}$ ispred zagrade:

$$s_{1,2} = s_{\mathrm{pr}} \cdot \left(\nu \pm \sqrt{\nu^2 - 1}\right) \tag{50.5}$$

Dobili smo **dva** rešenja, a fizički je „pravo" samo jedno. Zašto dva? Zato što horizontalna linija tereta seče brežuljak karakteristike na dva mesta: jednom na stabilnoj grani (malo klizanje, znak „$-$") i jednom na nestabilnoj (veliko klizanje, znak „$+$"). Motor trajno radi samo u stabilnoj tački, pa **uvek biramo manji koren** (onaj sa minusom), za koji je $s < s_{\mathrm{pr}}$.

Jednačina (50.4) je potpuno simetrična po $s$ i $s_{\mathrm{pr}}$ (zameniš li im mesta, jednačina se ne menja). Zato ista formula radi i „unazad": ako znamo radno klizanje $s$ a tražimo prevalno, važi

$$s_{\mathrm{pr}\,1,2} = s \cdot \left(\nu \pm \sqrt{\nu^2 - 1}\right)$$

i tada biramo **veći** koren (sa plusom), jer prevalno klizanje mora biti *veće* od radnog klizanja stabilne tačke.

### 5. Izraz za moment kad se zanemari $R_s$; odakle $s_{\mathrm{pr}}$ i $M_{\mathrm{pr}}$

Da bismo razumeli šta učestanost radi karakteristici, treba nam izraz za moment izveden iz ekvivalentne šeme asinhronog motora. Kad se zanemari omski otpor statorskog namotaja $R_s$ (opravdano kod motora ove i veće snage, gde je pad napona na $R_s$ mali), moment je:

$$M = \frac{q_s}{\omega_s} \cdot U_{sf}^2 \cdot \frac{R'_r / s}{\left(\dfrac{R'_r}{s}\right)^2 + X_{\mathrm{k}}^2} \tag{50.6}$$

Značenje svakog simbola:

- $q_s$ — broj faza statora (kod trofaznog motora $q_s = 3$);
- $\omega_s = \dfrac{2\pi f_{\mathrm{s}}}{p}$ — sinhrona **mehanička** ugaona brzina obrtnog polja u $\mathrm{rad/s}$ (isto što i $2\pi n_{\mathrm{s}}/60$);
- $U_{sf}$ — **fazni** napon statora;
- $R'_r$ — otpor rotorskog namotaja *sveden* na stator (prim označava svođenje: rotorske veličine preračunate kao da rotor ima isti namotaj kao stator, da bi se mogle crtati u istoj šemi);
- $X_{\mathrm{k}} = X_{\gamma s} + X'_{\gamma r}$ — **reaktansa kratkog spoja**: zbir rasipne reaktanse statora $X_{\gamma s}$ i svedene rasipne reaktanse rotora $X'_{\gamma r}$. Reaktansa je „otpor" koji kalem pruža naizmeničnoj struji, $X = 2\pi f_{\mathrm{s}} L$, gde je $L$ induktivnost.

Poreklo formule (50.6) u dve rečenice: iz ekvivalentne šeme se izračuna rotorska struja $I'_r = U_{sf}\big/\sqrt{(R'_r/s)^2 + X_{\mathrm{k}}^2}$, pa se moment dobije iz snage obrtnog polja $P_{ob} = q_s \, I'^2_r \, R'_r/s$ podeljene sinhronom brzinom: $M = P_{ob}/\omega_s$. Zašto baš tako? Fiktivna otpornost $R'_r/s$ u ekvivalentnoj šemi troši ukupnu aktivnu snagu koju obrtno polje kroz vazdušni zazor predaje rotoru — to je „snaga obrtnog polja" $P_{ob}$. A pošto tu snagu prenosi polje koje se vrti sinhronom brzinom $\omega_s$ (ne brzinom rotora!), moment koji polje razvija na zazoru je $M = P_{ob}/\omega_s$ — i taj isti moment deluje na rotor. Fizički: sav moment potiče od snage koju polje predaje rotoru preko vazdušnog zazora.

> **Napomena o originalu:** Zbirka uz jednačinu (50.6) piše da je $X_{\mathrm{k}}$ „induktivitet kratkog spoja". Ispravan naziv je **reaktansa** kratkog spoja (induktivnost bi bila $L_{\mathrm{k}} = L_{\gamma s} + L'_{\gamma r}$, a $X_{\mathrm{k}} = 2\pi f_{\mathrm{s}} L_{\mathrm{k}}$); na str. 170 iste zbirke, uz identičnu jednačinu (49.8), stoji ispravno „reaktansa".

**Gde je vrh brežuljka?** Uvedimo smenu $x = R'_r/s$ (za motorski režim $x > 0$). Tada iz (50.6):

$$M = \frac{q_s}{\omega_s} U_{sf}^2 \cdot \frac{x}{x^2 + X_{\mathrm{k}}^2} = \frac{q_s}{\omega_s} U_{sf}^2 \cdot \frac{1}{x + \dfrac{X_{\mathrm{k}}^2}{x}}$$

(u drugom koraku smo brojilac i imenilac podelili sa $x$). Moment je najveći kad je imenilac $x + X_{\mathrm{k}}^2/x$ najmanji. Po nejednakosti između aritmetičke i geometrijske sredine, zbir dva pozitivna broja čiji je proizvod stalan ($x \cdot X_{\mathrm{k}}^2/x = X_{\mathrm{k}}^2$) najmanji je kad su ta dva broja jednaka: $x = X_{\mathrm{k}}^2/x$, tj. $x = X_{\mathrm{k}}$. (Mini-dokaz, bez izvoda: $x + \dfrac{X_{\mathrm{k}}^2}{x} - 2X_{\mathrm{k}} = \left(\sqrt{x} - \dfrac{X_{\mathrm{k}}}{\sqrt{x}}\right)^2 \ge 0$, jer je kvadrat uvek nenegativan — dakle zbir nikad nije manji od $2X_{\mathrm{k}}$, a jednakost, tj. minimum, nastupa tačno kada je zagrada nula: $\sqrt{x} = X_{\mathrm{k}}/\sqrt{x}$, tj. $x = X_{\mathrm{k}}$.) Dakle maksimum momenta nastupa kada je $R'_r/s = X_{\mathrm{k}}$, odnosno pri klizanju:

$$s_{\mathrm{pr}} = \pm\frac{R'_r}{X_{\mathrm{k}}} = \pm\frac{R'_r}{X_{\gamma s} + X'_{\gamma r}} = \pm\frac{R'_r}{2\pi f_{\mathrm{s}} \cdot \left(L_{\gamma s} + L'_{\gamma r}\right)} \tag{50.7}$$

(znak $+$ važi za motorski, $-$ za generatorski režim; nas zanima motorski). U poslednjem koraku smo reaktansu raspisali preko induktivnosti, $X_{\mathrm{k}} = 2\pi f_{\mathrm{s}}(L_{\gamma s} + L'_{\gamma r})$, i tu se vidi **ključna činjenica**: otpor $R'_r$ i induktivnosti $L_{\gamma s}, L'_{\gamma r}$ su konstante mašine, pa se

$$s_{\mathrm{pr}} \sim \frac{1}{f_{\mathrm{s}}}$$

**prevalno klizanje menja obrnuto srazmerno učestanosti** — podignemo li učestanost sa 50 na 70 Hz, prevalno klizanje se smanji u odnosu $50/70$. (Napon uopšte ne ulazi u $s_{\mathrm{pr}}$!)

**Koliki je vrh?** Uvrstimo $s = s_{\mathrm{pr}}$ (tj. $R'_r/s_{\mathrm{pr}} = X_{\mathrm{k}}$) u (50.6): brojilac postaje $X_{\mathrm{k}}$, imenilac $X_{\mathrm{k}}^2 + X_{\mathrm{k}}^2 = 2X_{\mathrm{k}}^2$, pa je razlomak $X_{\mathrm{k}}/(2X_{\mathrm{k}}^2) = 1/(2X_{\mathrm{k}})$. Uz $\omega_s = 2\pi f_{\mathrm{s}}/p$:

$$M_{\mathrm{pr}} = \frac{q_s}{\dfrac{2\pi f_{\mathrm{s}}}{p}} \cdot U_{sf}^2 \cdot \frac{1}{2X_{\mathrm{k}}} = \frac{q_s}{\dfrac{4\pi f_{\mathrm{s}}}{p}} \cdot U_{sf}^2 \cdot \frac{1}{X_{\mathrm{k}}} \tag{50.8}$$

Zamenimo još $X_{\mathrm{k}} = 2\pi f_{\mathrm{s}}(L_{\gamma s} + L'_{\gamma r})$:

$$M_{\mathrm{pr}} = \frac{p \cdot q_s}{4\pi f_{\mathrm{s}}} \cdot U_{sf}^2 \cdot \frac{1}{2\pi f_{\mathrm{s}}\left(L_{\gamma s} + L'_{\gamma r}\right)} = \frac{p \cdot q_s}{8\pi^2}\left(\frac{U_{sf}}{f_{\mathrm{s}}}\right)^2 \cdot \frac{1}{L_{\gamma s} + L'_{\gamma r}}$$

Ovo je najvažnija formula za razumevanje U/f upravljanja: **prevalni moment zavisi samo od količnika $U_{sf}/f_{\mathrm{s}}$** (sve ostalo su konstante mašine). Odavde direktno slede dva režima iz sledeće mini-lekcije.

**Zatvaranje kruga — odakle tačno Klosova jednačina.** U mini-lekciji 4 smo obećali da se Klosova jednačina dobija kada se izraz za moment podeli sopstvenim maksimumom i da se pri tom deljenju svi parametri mašine skrate. Sada imamo sve da to deljenje i prikažemo. Sa smenom $x = R'_r/s$ izraz za moment glasi $M = \dfrac{q_s}{\omega_s} U_{sf}^2 \cdot \dfrac{x}{x^2 + X_{\mathrm{k}}^2}$, a njegov maksimum je $M_{\mathrm{pr}} = \dfrac{q_s}{\omega_s} U_{sf}^2 \cdot \dfrac{1}{2X_{\mathrm{k}}}$. Podelimo prvo drugim:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{\dfrac{x}{x^2 + X_{\mathrm{k}}^2}}{\dfrac{1}{2X_{\mathrm{k}}}} = \frac{2X_{\mathrm{k}}\, x}{x^2 + X_{\mathrm{k}}^2} = \frac{2}{\dfrac{x}{X_{\mathrm{k}}} + \dfrac{X_{\mathrm{k}}}{x}}$$

(u poslednjem koraku smo brojilac i imenilac podelili proizvodom $x\,X_{\mathrm{k}}$). Zaista su se $q_s$, $\omega_s$ i $U_{sf}^2$ skratili odmah, a ostatak zavisi samo od odnosa $x/X_{\mathrm{k}}$. Pošto je $x = R'_r/s$, a upravo smo izveli da je $X_{\mathrm{k}} = R'_r/s_{\mathrm{pr}}$, taj odnos je:

$$\frac{x}{X_{\mathrm{k}}} = \frac{R'_r/s}{R'_r/s_{\mathrm{pr}}} = \frac{s_{\mathrm{pr}}}{s}$$

— skratio se, dakle, i $R'_r$. Uvrštavanjem dobijamo tačno jednačinu (50.2): $\dfrac{M}{M_{\mathrm{pr}}} = \dfrac{2}{\dfrac{s_{\mathrm{pr}}}{s} + \dfrac{s}{s_{\mathrm{pr}}}}$. Krug je zatvoren: od pune formule sa parametrima mašine stigli smo do formule u kojoj figurišu samo $M_{\mathrm{pr}}$ i $s_{\mathrm{pr}}$.

### 6. Skalarno U/f upravljanje: bazna oblast i oblast slabljenja polja

**Zašto baš $U/f = \mathrm{const.}$?** Krenimo od Faradejevog zakona: u namotaju se indukuje elektromotorna sila srazmerna brzini promene fluksa kroz njega, $e = -N_s\, \dfrac{\mathrm{d}\Phi}{\mathrm{d}t}$, gde je $N_s$ broj navojaka statorskog namotaja. Glavni (zajednički) fluks $\Phi$ mašine menja se prostoperiodično učestanošću $f_{\mathrm{s}}$; izvod takve funkcije unosi faktor $2\pi f_{\mathrm{s}}$, pa je amplituda indukovane EMS $2\pi f_{\mathrm{s}} N_s \Phi$ (gde je $\Phi$ amplituda fluksa), a njena efektivna vrednost je amplituda podeljena sa $\sqrt{2}$:

$$E_s = \frac{2\pi}{\sqrt{2}}\, f_{\mathrm{s}}\, N_s\, \Phi \approx 4{,}44\, f_{\mathrm{s}}\, N_s\, \Phi$$

To je isti obrazac koji važi i kod transformatora — konstanta $4{,}44$ je prosto $2\pi/\sqrt{2} = 4{,}443\ldots$ Sama konstanta nam ovde nije ni važna; važno je jedino da iz nje sledi $\Phi \sim E_s/f_{\mathrm{s}}$. Pošto je pri zanemarenom $R_s$ **i** malom padu napona na rasipnoj reaktansi $X_{\gamma s}$ (a u normalnom pogonu taj pad jeste mali) napon približno jednak elektromotornoj sili, $U_{sf} \approx E_s$, sledi:

$$\Phi \sim \frac{U_{sf}}{f_{\mathrm{s}}}$$

Dakle: **količnik napona i učestanosti određuje fluks u mašini.** Šta biva ako taj količnik nije nominalan?

- Povećamo li učestanost, a napon ostavimo — isto kao da smo *snizili* napon: fluks opada, a sa njim (kvadratno!) polazni i prevalni moment; motor se lako preoptereti.
- Smanjimo li učestanost, a napon ostavimo — isto kao da smo *povisili* napon: fluks raste, magnetno kolo ulazi u zasićenje, struja praznog hoda (struja magnetisanja) naraste i preko nominalne struje.

U oba slučaja motor se pregreva. Zato se pri **regulaciji brzine promenom učestanosti** — tzv. **U/f upravljanju** ili **skalarnom upravljanju** — napon i učestanost menjaju *zajedno*, i to po sledećem pravilu sa dve oblasti:

**Bazna oblast** ($f_{\mathrm{s}} \le f_{\mathrm{sn}}$, brzine do nazivne):

$$\frac{U_s}{f_{\mathrm{s}}} = \mathrm{const.} = \frac{U_{\mathrm{sn}}}{f_{\mathrm{sn}}}$$

Fluks je tada stalno jednak nominalnom, $\Phi = \Phi_{\mathrm{n}}$, pa je po formuli iz mini-lekcije 5 **prevalni moment konstantan**: $M_{\mathrm{pr}} = M_{\mathrm{prn}}$. Karakteristika momenta zadržava istu visinu i praktično isti oblik, samo se **translatorno pomera duž ose brzine** — kao da familiju identičnih brežuljaka ređamo oko različitih sinhronih brzina $n_{\mathrm{s}} = 60 f_{\mathrm{s}}/p$. (U stvarnosti, kad se $R_s$ ne zanemari, $M_{\mathrm{pr}}$ se pri vrlo niskim učestanostima ipak nešto smanjuje.)

**Oblast slabljenja polja** ($f_{\mathrm{s}} > f_{\mathrm{sn}}$, brzine iznad nazivne): napon **ne sme** preko nazivnog — ograničava ga izolacija namotaja (i naponska granica samog pretvarača). Zato važi:

$$U_s = U_{\mathrm{sn}} = \mathrm{const.}, \qquad f_{\mathrm{s}} > f_{\mathrm{sn}}$$

Sada količnik $U_s/f_{\mathrm{s}}$ opada sa učestanošću, pa **fluks slabi** (otud ime oblasti), a prevalni moment opada **kvadratno**:

$$\frac{M_{\mathrm{pr1}}}{M_{\mathrm{prn}}} = \frac{\left(U_{\mathrm{sn}}/f_{\mathrm{s1}}\right)^2}{\left(U_{\mathrm{sn}}/f_{\mathrm{sn}}\right)^2} = \frac{f_{\mathrm{sn}}^2}{f_{\mathrm{s1}}^2}$$

Ovo je srce našeg zadatka: na $70\ \mathrm{Hz}$ motor je u oblasti slabljenja polja, pa mu je „brežuljak" niži nego na $50\ \mathrm{Hz}$ — i to tačno $(50/70)^2 \approx 0{,}51$ puta.

Ova metoda regulacije brzine je ekonomična (velika promena brzine uz malu promenu klizanja, dakle uz male gubitke) i danas je dominantna u praksi — realizuje se frekventnim pretvaračima.

### 7. Karakteristika tereta i stacionarna radna tačka

Radna mašina (teret) ima svoju karakteristiku momenta. **Dizalica** je školski primer tereta **konstantnog momenta**: moment koji ona traži određen je težinom podignutog tereta i poluprečnikom doboša, pa ne zavisi od brzine — u $M$–$n$ dijagramu to je horizontalna prava. U **stacionarnom pogonu** (ustaljena brzina, bez ubrzavanja) moment motora tačno pokriva moment tereta:

$$M = M_{\mathrm{opt}}$$

Radna tačka je presek karakteristike motora i karakteristike tereta — i to onaj presek na stabilnoj grani (mini-lekcija 3).

## Rešenje, korak po korak

### Korak 1: Broj pari polova i sinhrona brzina na 50 Hz

**Zašto ovaj korak:** Sve dalje (klizanje, sinhrone brzine na raznim učestanostima) zahteva da znamo broj pari polova $p$, a on nije eksplicitno dat — „pročitaćemo" ga iz nazivne brzine.

Sinhrona brzina je $n_{\mathrm{s}} = 60 f_{\mathrm{sn}}/p$, a rotor se u motorskom režimu vrti *malo sporije* od nje. Isprobajmo cele vrednosti $p$ pri $f_{\mathrm{sn}} = 50\ \mathrm{Hz}$:

$$p = 1: \ n_{\mathrm{s}} = 3000\ \mathrm{min^{-1}}, \qquad p = 2: \ n_{\mathrm{s}} = 1500\ \mathrm{min^{-1}}, \qquad p = 3: \ n_{\mathrm{s}} = 1000\ \mathrm{min^{-1}}$$

Nazivna brzina $n_{\mathrm{n}} = 1440\ \mathrm{min^{-1}}$ mora ležati *neposredno ispod* sinhrone. Jedina sinhrona brzina malo iznad $1440$ je $1500\ \mathrm{min^{-1}}$, dakle:

$$p = 2, \qquad n_{\mathrm{s}} = \frac{60 \cdot 50}{2} = 1500\ \mathrm{min^{-1}}$$

**Šta smo dobili:** Motor je četvoropolni ($p = 2$ para polova), sa sinhronom brzinom $1500\ \mathrm{min^{-1}}$ — najčešća izvedba u praksi. Rotor kasni za poljem $60\ \mathrm{min^{-1}}$, što je razumno malo.

### Korak 2: Nominalni moment $M_{\mathrm{n}}$

**Zašto ovaj korak:** Nominalni moment je referenca za sve — i teret ($0{,}5\,M_{\mathrm{n}}$) i prevalni moment ($2{,}5\,M_{\mathrm{n}}$) izraženi su preko njega.

Opšti oblik (mini-lekcija 2): moment je snaga podeljena ugaonom brzinom,

$$M_{\mathrm{n}} = \frac{P_{\mathrm{n}}}{\Omega_{\mathrm{n}}} = \frac{P_{\mathrm{n}}}{\dfrac{2\pi}{60} \cdot n_{\mathrm{n}}}$$

gde je $P_{\mathrm{n}}$ nazivna snaga na vratilu, a $\Omega_{\mathrm{n}}$ nazivna mehanička ugaona brzina. Prvo izračunajmo ugaonu brzinu:

$$\Omega_{\mathrm{n}} = \frac{2\pi}{60} \cdot 1440 = 2\pi \cdot 24 = 150{,}8\ \mathrm{rad/s}$$

pa je moment:

$$M_{\mathrm{n}} = \frac{4000\ \mathrm{W}}{150{,}8\ \mathrm{rad/s}} = 26{,}5\ \mathrm{Nm}$$

**Šta smo dobili:** Motor od 4 kW pri ~1500 min⁻¹ daje oko $26{,}5\ \mathrm{Nm}$ — tipičan red veličine (gruba praktičarska mnemonika: $M[\mathrm{Nm}] \approx 9550 \cdot P[\mathrm{kW}] / n[\mathrm{min^{-1}}]$ — to je samo prepakovano $M = P/\Omega$ — što pri našoj brzini od 1440 min⁻¹ daje oko $6{,}6\ \mathrm{Nm}$ po kilovatu). Dizalica, dakle, traži $M_{\mathrm{opt}} = 0{,}5 \cdot 26{,}5 = 13{,}25\ \mathrm{Nm}$, stalno:

$$M_{\mathrm{opt}} = 0{,}5 \cdot M_{\mathrm{n}} = \mathrm{konst.} \tag{50.1}$$

### Korak 3: Prevalni moment $M_{\mathrm{prn}}$ na nazivnoj učestanosti

**Zašto ovaj korak:** Prevalni moment je jedan od dva parametra Klosove jednačine; bez njega ne znamo koliko je „visok brežuljak".

Po definiciji preopteretivosti $\nu = M_{\mathrm{pr}}/M_{\mathrm{n}}$, prevalni moment u nominalnom režimu je:

$$M_{\mathrm{prn}} = \nu \cdot M_{\mathrm{n}} = 2{,}5 \cdot 26{,}5\ \mathrm{Nm} = 66{,}25\ \mathrm{Nm}$$

**Šta smo dobili:** Na 50 Hz motor može kratkotrajno da razvije do $66{,}25\ \mathrm{Nm}$ — pet puta više nego što dizalica traži ($13{,}25\ \mathrm{Nm}$). Na nazivnoj učestanosti rezerva je ogromna; pitanje je šta od nje ostane na 70 Hz.

### Korak 4: Nominalno klizanje $s_{\mathrm{n}}$

**Zašto ovaj korak:** Klizanje u poznatoj (nazivnoj) radnoj tački je ulaz za Klosovu jednačinu — iz njega ćemo u sledećem koraku dobiti prevalno klizanje.

Po definiciji klizanja (mini-lekcija 1):

$$s_{\mathrm{n}} = \frac{n_{\mathrm{s}} - n_{\mathrm{n}}}{n_{\mathrm{s}}} = \frac{1500 - 1440}{1500} = \frac{60}{1500} = 0{,}04 = 4\ \%$$

> **Napomena o originalu:** U zbirci (str. 174) simbolički oblik ove formule ima štamparsku grešku — u imeniocu piše $n_{\mathrm{n}}$ umesto $n_{\mathrm{s}}$. Brojčano je, međutim, uvršteno ispravno $1500$ (dakle $n_{\mathrm{s}}$), pa je rezultat $0{,}04$ tačan. Ispravna definicija klizanja uvek deli sa sinhronom brzinom.

**Šta smo dobili:** Nazivno klizanje od 4 % je sasvim uobičajeno za kavezni motor ove snage — rotor kasni za poljem svega 4 % sinhrone brzine.

### Korak 5: Prevalno klizanje $s_{\mathrm{prn}}$ na nazivnoj učestanosti

**Zašto ovaj korak:** Ovo je drugi parametar Klosove jednačine. Znamo jednu tačku na krivoj ($s_{\mathrm{n}}$, $M_{\mathrm{n}}$) i znamo koliko je vrh viši od te tačke ($\nu = 2{,}5$) — Klosova jednačina nam onda kaže gde je vrh.

Koristimo rezultat mini-lekcije 4 sa poznatim klizanjem $s = s_{\mathrm{n}}$ i preopteretivošću $\nu = M_{\mathrm{prn}}/M_{\mathrm{n}} = 2{,}5$, birajući koren sa **plusom** (prevalno klizanje mora biti veće od radnog):

$$s_{\mathrm{prn}} = s_{\mathrm{n}} \cdot \left(\nu + \sqrt{\nu^2 - 1}\right)$$

Uvrstimo brojeve, deo po deo. Prvo potkorena veličina:

$$\nu^2 - 1 = 2{,}5^2 - 1 = 6{,}25 - 1 = 5{,}25, \qquad \sqrt{5{,}25} = 2{,}291$$

zatim zagrada i proizvod:

$$s_{\mathrm{prn}} = 0{,}04 \cdot \left(2{,}5 + 2{,}291\right) = 0{,}04 \cdot 4{,}791 = 0{,}192 = 19{,}2\ \%$$

**Šta smo dobili:** Vrh karakteristike je na klizanju od oko 19 % — tj. pri brzini $n = (1 - 0{,}192) \cdot 1500 \approx 1212\ \mathrm{min^{-1}}$. Time je motor na 50 Hz potpuno opisan parom $(M_{\mathrm{prn}},\, s_{\mathrm{prn}}) = (66{,}25\ \mathrm{Nm},\ 0{,}192)$. Da smo izabrali koren sa minusom, dobili bismo $s_{\mathrm{pr}} < s_{\mathrm{n}}$ — vrh „ispod" radne tačke, što je nemoguće za stabilan nazivni rad.

### Korak 6: Prevalno klizanje $s_{\mathrm{pr1}}$ na 70 Hz

**Zašto ovaj korak:** Prelazimo na novu učestanost — a sa njom se menja i položaj vrha karakteristike. Iz mini-lekcije 5 znamo tačno kako.

Prema jednačini (50.7), $s_{\mathrm{pr}} = R'_r \big/ \left[2\pi f_{\mathrm{s}} (L_{\gamma s} + L'_{\gamma r})\right] \sim 1/f_{\mathrm{s}}$, jer su $R'_r$ i induktivnosti konstante mašine. Zato je odnos prevalnih klizanja jednak obrnutom odnosu učestanosti:

$$s_{\mathrm{pr1}} = \frac{f_{\mathrm{sn}}}{f_{\mathrm{s1}}} \cdot s_{\mathrm{prn}} = \frac{50}{70} \cdot 0{,}192 = 0{,}7143 \cdot 0{,}192 = 0{,}137 = 13{,}7\ \%$$

**Šta smo dobili:** Na višoj učestanosti brežuljak momenta postaje relativno „uži" — vrh mu je na svega 13,7 % klizanja. Podsetimo: napon u $s_{\mathrm{pr}}$ ne ulazi, pa ovaj rezultat važi svejedno u kojoj smo oblasti upravljanja.

### Korak 7: Prevalni moment $M_{\mathrm{pr1}}$ na 70 Hz — slabljenje polja

**Zašto ovaj korak:** Ovo je ključni i najlakše promašivi korak. Učestanost $70\ \mathrm{Hz} > f_{\mathrm{sn}} = 50\ \mathrm{Hz}$ znači da smo u **oblasti slabljenja polja**: napon je već na nazivnoj vrednosti i ne sme više da raste (izolacija namotaja!), pa uslov $U/f = \mathrm{const.}$ prestaje da važi — količnik $U/f$ opada, fluks slabi, i prevalni moment više **nije** $M_{\mathrm{prn}}$.

Prema izvedenoj formuli $M_{\mathrm{pr}} = \dfrac{p\, q_s}{8\pi^2}\left(\dfrac{U_{sf}}{f_{\mathrm{s}}}\right)^2 \dfrac{1}{L_{\gamma s} + L'_{\gamma r}}$ (mini-lekcija 5, iz (50.8)), pri **istom** (nazivnom) naponu u obe tačke, sve konstante se skrate i ostane:

$$\frac{M_{\mathrm{pr1}}}{M_{\mathrm{prn}}} = \frac{f_{\mathrm{sn}}^2}{f_{\mathrm{s1}}^2} \quad\Longrightarrow\quad M_{\mathrm{pr1}} = M_{\mathrm{prn}} \cdot \left(\frac{50}{70}\right)^2 = M_{\mathrm{prn}} \cdot 0{,}51$$

Brojčano: $\left(50/70\right)^2 = 0{,}7143^2 = 0{,}5102 \approx 0{,}51$, pa je

$$M_{\mathrm{pr1}} = 0{,}51 \cdot 66{,}25\ \mathrm{Nm} \approx 33{,}8\ \mathrm{Nm}$$

**Šta smo dobili:** Prevalni moment je na 70 Hz prepolovljen — od $66{,}25\ \mathrm{Nm}$ ostalo je $33{,}8\ \mathrm{Nm}$. Motor i dalje može da vuče dizalicu ($33{,}8 > 13{,}25\ \mathrm{Nm}$), ali mu je rezerva vidno istopljena. Ovo je cena vožnje iznad nazivne brzine.

### Korak 8: Preopteretivost prema teretu na 70 Hz

**Zašto ovaj korak:** Klosova formula za klizanje (50.5) traži preopteretivost $\nu$ — ali **prema stvarnom teretu**, ne prema nazivnom momentu! U stacionarnom pogonu motor razvija $M = M_{\mathrm{opt}} = 0{,}5\,M_{\mathrm{n}}$, pa je:

$$\nu_1 = \frac{M_{\mathrm{pr1}}}{M_{\mathrm{opt}}} = \frac{0{,}51 \cdot M_{\mathrm{prn}}}{0{,}5 \cdot M_{\mathrm{n}}}$$

Iskoristimo $M_{\mathrm{prn}} = 2{,}5 \cdot M_{\mathrm{n}}$, pa se $M_{\mathrm{n}}$ skrati:

$$\nu_1 = \frac{0{,}51 \cdot 2{,}5 \cdot M_{\mathrm{n}}}{0{,}5 \cdot M_{\mathrm{n}}} = \frac{0{,}51 \cdot 2{,}5}{0{,}5} = 2{,}55$$

**Šta smo dobili:** Iako je prevalni moment prepolovljen, preopteretivost prema *ovom lakom teretu* iznosi udobnih 2,55 — jer dizalica traži samo pola nazivnog momenta. Radna tačka postoji i daleko je od prevale.

### Korak 9: Klizanje $s_1$ na 70 Hz iz Klosove jednačine

**Zašto ovaj korak:** Sada znamo oba parametra karakteristike na 70 Hz ($s_{\mathrm{pr1}} = 0{,}137$, $\nu_1 = 2{,}55$) — formula (50.5) daje klizanje radne tačke. A sme li se Klosova jednačina uopšte koristiti na 70 Hz? Sme: izvod „podeli moment njegovim maksimumom" iz mini-lekcija 4 i 5 važi na svakoj fiksnoj učestanosti ponaosob, pa Klos na 70 Hz ima potpuno isti oblik — samo se u njega uvrštava prevalni par *te* učestanosti, a to su upravo $M_{\mathrm{pr1}}$ i $s_{\mathrm{pr1}}$.

$$s_{1,2} = s_{\mathrm{pr1}} \cdot \left(\nu_1 \pm \sqrt{\nu_1^2 - 1}\right) = 0{,}137 \cdot \left(2{,}55 \pm \sqrt{2{,}55^2 - 1}\right)$$

Računajmo deo po deo:

$$2{,}55^2 - 1 = 6{,}5025 - 1 = 5{,}5025, \qquad \sqrt{5{,}5025} = 2{,}346$$

pa su dva korena:

$$s_{11} = 0{,}137 \cdot \left(2{,}55 + 2{,}346\right) = 0{,}137 \cdot 4{,}896 = 0{,}67$$

$$s_{12} = 0{,}137 \cdot \left(2{,}55 - 2{,}346\right) = 0{,}137 \cdot 0{,}204 = 0{,}028$$

Koren $s_{11} = 0{,}67$ leži na nestabilnoj grani ($0{,}67 > s_{\mathrm{pr1}} = 0{,}137$) — tu motor ne može trajno da radi, pa ga odbacujemo. Fizički ispravno rešenje je manji koren:

$$s_1 = 0{,}028 = 2{,}8\ \%$$

> **Napomena o originalu:** Zbirka na ovom mestu (str. 175) upućuje na jednačinu „(4.5)" — očigledna štamparska greška; misli se na jednačinu (50.5) iz istog rešenja.

**Šta smo dobili:** Klizanje radne tačke od svega 2,8 % — motor radi blizu nove sinhrone brzine, duboko na stabilnoj grani ($0{,}028 \ll 0{,}137$), što i očekujemo za teret znatno manji od prevalnog momenta.

### Korak 10: Sinhrona brzina i brzina rotora na 70 Hz

**Zašto ovaj korak:** Klizanje je relativna mera — da bismo dobili traženu brzinu u obrtajima u minuti, treba nam još sinhrona brzina na novoj učestanosti.

Brzina obrtnog polja pri $f_{\mathrm{s1}} = 70\ \mathrm{Hz}$ (isti $p = 2$, jer broj polova ne zavisi od napajanja):

$$n_{\mathrm{s1}} = \frac{60 \cdot f_{\mathrm{s1}}}{p} = \frac{60 \cdot 70}{2} = 2100\ \mathrm{min^{-1}}$$

Brzina rotora sledi iz definicije klizanja, $n = (1 - s)\,n_{\mathrm{s}}$:

$$n_1 = \left(1 - s_1\right) \cdot n_{\mathrm{s1}} = \left(1 - 0{,}028\right) \cdot 2100 = 0{,}972 \cdot 2100 = 2041{,}2\ \mathrm{min^{-1}}$$

**Šta smo dobili:** Konačan odgovor — dizalica se pri 70 Hz vrti sa oko $\boxed{2041\ \mathrm{min^{-1}}}$, dakle znatno iznad nazivne brzine od $1440\ \mathrm{min^{-1}}$. Promenom učestanosti postigli smo veliku promenu brzine (sa 1440 na 2041 min⁻¹) uz malo klizanje, tj. uz male gubitke — upravo zato je regulacija brzine promenom učestanosti danas dominantna metoda u praksi.

## Česte greške i zamke

1. **Uzeti $M_{\mathrm{pr1}} = M_{\mathrm{prn}}$ i na 70 Hz.** Pravilo „$U/f = \mathrm{const.} \Rightarrow M_{\mathrm{pr}} = \mathrm{const.}$" važi **samo do nazivne učestanosti**. Iznad nje napon je zakovan na $U_{\mathrm{n}}$ (izolacija!), fluks slabi i prevalni moment pada kvadratno: $M_{\mathrm{pr1}} = M_{\mathrm{prn}}(f_{\mathrm{sn}}/f_{\mathrm{s1}})^2$. Ko ovo preskoči, dobije pogrešnu preopteretivost (5 umesto 2,55) i pogrešno klizanje.

2. **Preopteretivost računati prema nazivnom momentu umesto prema stvarnom teretu.** U formuli (50.5) figuriše $\nu = M_{\mathrm{pr}}/M$, gde je $M$ moment koji motor *stvarno razvija* u stacionarnom stanju — a to je moment tereta $0{,}5\,M_{\mathrm{n}}$, ne $M_{\mathrm{n}}$. Pogrešan izbor daje $\nu_1 = 0{,}51 \cdot 2{,}5 = 1{,}275$ i potpuno pogrešno klizanje.

3. **Izabrati pogrešan koren kvadratne jednačine.** Jednačina uvek daje dva rešenja; $s_{11} = 0{,}67$ je presek sa nestabilnom granom i fizički je neupotrebljiv. Kriterijum: stacionarno radno klizanje mora biti **manje** od prevalnog ($s_1 < s_{\mathrm{pr1}}$). Obrnuto, kad iz poznate radne tačke tražimo *prevalno* klizanje (Korak 5), bira se **veći** koren.

4. **Klizanje deliti nazivnom umesto sinhronom brzinom.** Definicija je $s = (n_{\mathrm{s}} - n)/n_{\mathrm{s}}$ — imenilac je sinhrona brzina. (Baš tu je i štamparska greška u originalu — ne dajte da vas zbuni.)

5. **Zaboraviti da i $s_{\mathrm{pr}}$ zavisi od učestanosti.** Prevalno klizanje nije konstanta motora: $s_{\mathrm{pr}} \sim 1/f_{\mathrm{s}}$. Ko na 70 Hz upotrebi $s_{\mathrm{prn}} = 0{,}192$ umesto $s_{\mathrm{pr1}} = 0{,}137$, dobije klizanje (i pad brzine) uvećane za 40 %.

6. **Računati $M_{\mathrm{n}}$ bez pretvaranja brzine u $\mathrm{rad/s}$.** U $M = P/\Omega$ ugaona brzina mora biti u radijanima u sekundi: $\Omega = 2\pi n/60$. Deljenje snage brojem obrtaja u minuti daje besmislen rezultat ($4000/1440 = 2{,}78$ — nije moment ni u jednoj razumnoj jedinici).

## Rezime rezultata

| Veličina | Oznaka | Vrednost |
|---|---|---|
| Broj pari polova | $p$ | $2$ |
| Sinhrona brzina na 50 Hz | $n_{\mathrm{s}}$ | $1500\ \mathrm{min^{-1}}$ |
| Nominalni moment | $M_{\mathrm{n}}$ | $26{,}5\ \mathrm{Nm}$ |
| Moment tereta (dizalice) | $M_{\mathrm{opt}}$ | $13{,}25\ \mathrm{Nm}$ |
| Prevalni moment na 50 Hz | $M_{\mathrm{prn}}$ | $66{,}25\ \mathrm{Nm}$ |
| Nominalno klizanje | $s_{\mathrm{n}}$ | $0{,}04 = 4\ \%$ |
| Prevalno klizanje na 50 Hz | $s_{\mathrm{prn}}$ | $0{,}192 = 19{,}2\ \%$ |
| Prevalno klizanje na 70 Hz | $s_{\mathrm{pr1}}$ | $0{,}137 = 13{,}7\ \%$ |
| Prevalni moment na 70 Hz | $M_{\mathrm{pr1}}$ | $0{,}51 \cdot M_{\mathrm{prn}} \approx 33{,}8\ \mathrm{Nm}$ |
| Preopteretivost prema teretu na 70 Hz | $\nu_1$ | $2{,}55$ |
| Klizanje na 70 Hz (stabilni koren) | $s_1$ | $0{,}028 = 2{,}8\ \%$ |
| Odbačeni (nestabilni) koren | $s_{11}$ | $0{,}67$ |
| Sinhrona brzina na 70 Hz | $n_{\mathrm{s1}}$ | $2100\ \mathrm{min^{-1}}$ |
| **Brzina obrtanja motora na 70 Hz** | $n_1$ | $\mathbf{2041{,}2\ \mathrm{min^{-1}}}$ |

## Provera smisla

**1. Vraćanje rezultata u Klosovu jednačinu.** Ako je $s_1 = 0{,}028$ zaista radna tačka, Klosova jednačina sa parametrima za 70 Hz mora vratiti moment tereta:

$$M = \frac{2 \, M_{\mathrm{pr1}}}{\dfrac{s_1}{s_{\mathrm{pr1}}} + \dfrac{s_{\mathrm{pr1}}}{s_1}} = \frac{2 \cdot 33{,}8}{\dfrac{0{,}028}{0{,}137} + \dfrac{0{,}137}{0{,}028}} = \frac{67{,}6}{0{,}204 + 4{,}893} = \frac{67{,}6}{5{,}097} \approx 13{,}3\ \mathrm{Nm}$$

a to je (do zaokruživanja) tačno $M_{\mathrm{opt}} = 0{,}5 \cdot 26{,}5 = 13{,}25\ \mathrm{Nm}$. Račun se zatvara.

**2. Dimenziona provera nominalnog momenta.** $\dfrac{\mathrm{W}}{\mathrm{rad/s}} = \dfrac{\mathrm{J/s}}{1/\mathrm{s}} = \mathrm{J} = \mathrm{Nm}$ — vat podeljen radijanom u sekundi zaista daje njutn-metar (radijan je bezdimenzion).

**3. Granični slučaj: do koje učestanosti pogon uopšte radi?** U slabljenju polja prevalni moment pada kao $1/f_{\mathrm{s}}^2$; pogon staje kad prevalni moment padne na moment tereta. Granična učestanost:

$$M_{\mathrm{prn}}\left(\frac{f_{\mathrm{sn}}}{f_{\mathrm{s,max}}}\right)^2 = M_{\mathrm{opt}} \ \Longrightarrow\ f_{\mathrm{s,max}} = f_{\mathrm{sn}}\sqrt{\frac{M_{\mathrm{prn}}}{M_{\mathrm{opt}}}} = 50 \cdot \sqrt{\frac{66{,}25}{13{,}25}} = 50\sqrt{5} \approx 112\ \mathrm{Hz}$$

Naših $70\ \mathrm{Hz}$ je udobno ispod te granice — zato je rešenje sa malim klizanjem i postojalo. (U praksi bi se stalo znatno ranije, da ostane rezerve za ubrzavanja i udare tereta.)

**4. Poređenje sa nazivnim vrednostima.** Dobijena brzina $2041{,}2\ \mathrm{min^{-1}}$ je za oko 42 % veća od nazivne — logično, jer smo učestanost digli za 40 % (sa 50 na 70 Hz), a klizanje je malo. I obratno: da je ispalo npr. $n_1 > n_{\mathrm{s1}} = 2100\ \mathrm{min^{-1}}$ ili $n_1 < 1440\ \mathrm{min^{-1}}$, znali bismo da smo negde pogrešili.
