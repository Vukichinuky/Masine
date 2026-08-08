# Zadatak 31 — Koeficijent transformacije, klizanje i rotorska frekvencija iz podataka rotorskog kola (kočioni režim)

## Postavka

Trofazni asinhroni motor sa statorskim namotajem spregnutim u zvezdu priključen je na mrežu
linijskog napona $380\ \mathrm{V}$ i frekvencije $50\ \mathrm{Hz}$. U jednom pogonskom stanju
izmereno je / poznato je sledeće za **rotorsko** kolo:

- indukovana elektromotorna sila po fazi rotorskog namotaja: $22\ \mathrm{V}$,
- struja rotora (po fazi): $100\ \mathrm{A}$,
- gubici u bakru rotora: $300\ \mathrm{W}$,
- induktivnost rasipanja rotora: $6{,}114\cdot 10^{-4}\ \mathrm{H}$.

Koliko u tom pogonskom stanju iznose: **koeficijent transformacije motora**
$m_e = \dfrac{N_s k_s}{N_r k_r}$, **klizanje** $s$ i **frekvencija rotorskih veličina** $f_r$?

> **Prevod na običan jezik:** Imamo asinhroni motor i o njegovom rotoru znamo skoro sve: koliki mu
> se napon indukuje, kolika struja teče, koliko se snage greje u njegovim provodnicima i koliko mu
> „beži" magnetnog fluksa (induktivnost rasipanja). O statoru znamo samo napon i frekvenciju mreže.
> Iz tih rotorskih podataka treba, kao detektivi, da rekonstruišemo tri stvari: (1) koliko brzo se
> rotor okreće u odnosu na obrtno polje (klizanje), (2) na kojoj frekvenciji „žive" struje i naponi
> u rotoru, i (3) koliki je „prenosni odnos" između statorskog i rotorskog namotaja — veličina
> analogna prenosnom odnosu transformatora. Zanimljivo je da će se ispostaviti da mašina uopšte ne
> radi kao običan motor, nego u **kočionom režimu** — to ćemo otkriti iz samog računa.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Linijski napon mreže | $U_s$ | $380\ \mathrm{V}$ | Napon između dva fazna provodnika mreže na koju je priključen stator. |
| Frekvencija mreže (statorska) | $f_s$ | $50\ \mathrm{Hz}$ | Učestanost napona i struja statora; određuje brzinu obrtnog magnetnog polja. |
| Sprega statora | — | zvezda (Y) | Način vezivanja tri fazna namotaja statora; kod zvezde je fazni napon $\sqrt{3}$ puta manji od linijskog. |
| Indukovana EMS po fazi rotora (u datom pogonskom stanju) | $E_{rf}$ | $22\ \mathrm{V}$ | Napon koji obrtno polje indukuje u jednoj fazi rotorskog namotaja **dok se rotor obrće** — zavisi od klizanja. |
| Struja rotora po fazi | $I_{rf}$ | $100\ \mathrm{A}$ | Struja koja teče kroz jednu fazu rotorskog namotaja. |
| Gubici u bakru rotora | $P_{\mathrm{Cu}r}$ | $300\ \mathrm{W}$ | Snaga koja se pretvara u toplotu u provodnicima rotora (Džulovi gubici), za sve tri faze zajedno. |
| Induktivnost rasipanja rotora | $L_{\gamma r}$ | $6{,}114\cdot 10^{-4}\ \mathrm{H}$ | Mera onog dela rotorskog fluksa koji se „rasipa" — obuhvata samo rotorski namotaj i ne učestvuje u sprezi sa statorom. |

Tražene veličine: koeficijent transformacije $m_e$, klizanje $s$, rotorska frekvencija $f_r$.

## Šta se traži i zašto

**1) Klizanje $s$.** Klizanje je relativna razlika između brzine obrtnog polja i brzine rotora —
ono je „lična karta" pogonskog stanja asinhrone mašine. Iz klizanja se odmah vidi da li mašina
radi kao motor, generator ili kočnica, kolika joj je rotorska frekvencija i kako joj se raspodeljuje
snaga. Inženjera zanima jer bez klizanja ne može da izračuna ništa drugo o radnoj tački.

**2) Rotorska frekvencija $f_r$.** To je učestanost struja i napona u rotoru. Ona određuje
zagrevanje gvožđa rotora, vrednost rotorske reaktanse i ponašanje mašine u prelaznim režimima.
Kad znamo klizanje, dobijamo je jednim množenjem: $f_r = s\, f_s$.

**3) Koeficijent transformacije $m_e = \dfrac{N_s k_s}{N_r k_r}$.** Asinhroni motor je u suštini
„obrtni transformator": stator je primar, rotor sekundar. Koeficijent transformacije govori u kom
odnosu se naponi (i struje) preslikavaju između statora i rotora. Potreban je svaki put kad
rotorske veličine želimo da „svedemo" na statorsku stranu (ili obrnuto) — što je osnova ekvivalentne
šeme asinhrone mašine.

**Plan rešavanja u pet koraka, običnim jezikom:**

1. Iz gubitaka u bakru i struje rotora izračunamo **otpor rotorskog namotaja** $R_r$ (Džulov zakon unazad).
2. Iz induktivnosti rasipanja izračunamo **reaktansu rasipanja rotora na statorskoj frekvenciji** $X_{\gamma r}$ (to je reaktansa ukočenog rotora).
3. Napišemo Omov zakon za rotorsko kolo koje se obrće — u njemu figuriše klizanje — pa iz te jednačine **izrazimo i izračunamo klizanje** $s$.
4. Pomnožimo klizanje sa statorskom frekvencijom i dobijemo **rotorsku frekvenciju** $f_r$; usput protumačimo šta znači to što je $s > 1$.
5. Fazni napon statora izjednačimo (približno) sa statorskom EMS, rotorsku EMS „vratimo" na vrednost ukočenog rotora deljenjem sa $s$, i njihov količnik nam da **koeficijent transformacije** $m_e$.

## Potrebna teorija — mini-lekcije

### Mini-lekcija 1: Klizanje i režimi rada asinhrone mašine

Statorske struje frekvencije $f_s$ stvaraju **obrtno magnetno polje** koje se okreće sinhronom
brzinom $n_s$. Rotor se okreće nekom svojom brzinom $n$. **Klizanje** je relativna razlika te dve
brzine:

$$s = \frac{n_s - n}{n_s}$$

- $n_s$ — sinhrona brzina (brzina obrtnog polja),
- $n$ — mehanička brzina rotora.

Klizanje je bezdimenziona veličina (brzina podeljena brzinom) i po njegovoj vrednosti odmah
prepoznajemo režim rada:

| Klizanje | Režim | Šta se dešava |
|---|---|---|
| $0 < s < 1$ | **motorni** | Rotor se okreće u smeru polja, ali sporije od njega; mašina daje mehaničku snagu. |
| $s < 0$ | **generatorski** | Rotor je pogonjen spolja brže od polja; mašina vraća električnu snagu u mrežu. |
| $s > 1$ | **kočioni (protivstrujno kočenje)** | Rotor se okreće **suprotno** od smera obrtnog polja ($n < 0$, pa je $n_s - n > n_s$). Polje „vuče" rotor unazad — mašina koči. |

Kočioni režim se u praksi javlja npr. kada motoru koji se vrti u jednom smeru naglo zamenimo dve
faze napajanja: polje odmah promeni smer obrtanja, a rotor po inerciji nastavlja da se vrti na
staru stranu — trenutno klizanje postane veće od 1 i mašina naglo koči. Sličan režim je i
spuštanje tereta kod dizalica, gde teret vuče rotor suprotno od polja.

**Intuicija:** klizanje meri „koliko brzo polje promiče pored rotorskih provodnika". Ako rotor
juri zajedno sa poljem ($n \approx n_s$), polje ga jedva „šiša" i $s \approx 0$. Ako rotor stoji,
polje ga šiša punom sinhronom brzinom i $s = 1$. Ako se rotor vrti **u susret** polju, relativna
brzina je veća nego kad miruje — zato je tada $s > 1$.

### Mini-lekcija 2: Rotorska frekvencija

Naponi i struje u rotoru indukuju se zato što obrtno polje promiče pored rotorskih provodnika.
Učestanost tih indukovanih veličina zato zavisi od **relativne** brzine polja u odnosu na rotor,
a nju upravo meri klizanje. Kada rotor stoji ($s = 1$), polje ga preseca punom brzinom i rotorska
frekvencija je jednaka statorskoj; pri svakom drugom klizanju frekvencija se skalira srazmerno:

$$f_r = s \cdot f_s$$

- $f_r$ — frekvencija rotorskih napona i struja,
- $f_s$ — frekvencija statorskih (mrežnih) veličina.

U motornom režimu ($s$ malo, npr. $0{,}02\ldots 0{,}05$) rotorska frekvencija je svega par herca.
U kočionom režimu ($s > 1$) rotorska frekvencija je **veća od statorske** — rotorske veličine
osciluju brže od mrežnih, jer polje preseca provodnike brže nego kada rotor miruje.

### Mini-lekcija 3: Rotorska EMS — ukočen i obrtni rotor

Indukovana elektromotorna sila (EMS) je, po Faradejevom zakonu, srazmerna brzini promene fluksa,
dakle srazmerna frekvenciji. Definišimo:

- $E_{rfk}$ — EMS po fazi rotora **kada rotor miruje** (ukočen rotor, $s = 1$); tada je rotorska
  frekvencija jednaka statorskoj i EMS je najveća;
- $E_{rf}$ — EMS po fazi rotora **u pogonskom stanju sa klizanjem $s$**; fluks je isti, ali ga
  rotor „vidi" na frekvenciji $f_r = s f_s$, pa je EMS srazmerno manja/veća:

$$E_{rf} = s \cdot E_{rfk} \qquad\Longleftrightarrow\qquad E_{rfk} = \frac{E_{rf}}{s}$$

Ova veza je ključna za ovaj zadatak: podatak $22\ \mathrm{V}$ je EMS **obrtnog** rotora (u datom
pogonskom stanju), a za koeficijent transformacije treba nam EMS **ukočenog** rotora — do nje
dolazimo deljenjem sa klizanjem.

### Mini-lekcija 4: Reaktansa rasipanja rotora i njena zavisnost od klizanja

Deo fluksa koji stvara rotorska struja ne stiže do statora, već se zatvara lokalno oko rotorskih
provodnika — to je **rasipni fluks**, a njegova mera je **induktivnost rasipanja** $L_{\gamma r}$.
Induktivnost je svojstvo geometrije i broja navojaka, pa **ne zavisi** od frekvencije. Ali
reaktansa (otpor koji induktivnost pruža naizmeničnoj struji) zavisi od frekvencije po opštoj
formuli $X = \omega L = 2\pi f L$.

Reaktansa rasipanja rotora izračunata **na statorskoj frekvenciji** (dakle za ukočen rotor, gde je
$f_r = f_s$) je referentna vrednost:

$$X_{\gamma r} = 2\pi f_s L_{\gamma r}$$

U pogonskom stanju sa klizanjem $s$ rotorske struje imaju frekvenciju $f_r = s f_s$, pa je stvarna
reaktansa rotora:

$$X_{\gamma r}(s) = 2\pi f_r L_{\gamma r} = 2\pi\, (s f_s)\, L_{\gamma r} = s \cdot X_{\gamma r}$$

**Zapamti:** aktivni otpor $R_r$ ne zavisi od klizanja, a reaktansa rasipanja se množi klizanjem.
To je srce cele analize rotorskog kola.

### Mini-lekcija 5: Omov zakon za rotorsko kolo koje se obrće

Jedna faza rotorskog namotaja je zatvoreno kolo (kavezni rotor je kratko spojen; namotani rotor je
kratko spojen preko prstenova ili spoljašnjeg otpora — ovde spoljašnjeg otpora nema). U tom kolu
deluje EMS $E_{rf}$, a struju ograničava redna veza aktivnog otpora $R_r$ i reaktanse rasipanja
$s X_{\gamma r}$. Moduo impedanse redne $R$–$X$ veze je $\sqrt{R^2 + X^2}$ (Pitagorina teorema u
kompleksnoj ravni: otpor i reaktansa su pod pravim uglom). Omov zakon za rotorsko kolo zato glasi:

$$I_{rf} = \frac{E_{rf}}{\sqrt{R_r^{\,2} + \left(s\, X_{\gamma r}\right)^2}}$$

- $I_{rf}$ — struja po fazi rotora,
- $E_{rf}$ — EMS po fazi rotora u datom pogonskom stanju,
- $R_r$ — aktivni otpor faze rotorskog namotaja,
- $s X_{\gamma r}$ — reaktansa rasipanja rotora na stvarnoj rotorskoj frekvenciji (mini-lekcija 4).

U ovoj jednačini jedina nepoznata (kad izračunamo $R_r$ i $X_{\gamma r}$) jeste klizanje $s$ —
upravo iz nje ćemo ga izvući.

### Mini-lekcija 6: Džulovi gubici u bakru rotora

Svaki provodnik kroz koji teče struja $I$ i koji ima otpor $R$ greje se snagom $R I^2$ (Džulov
zakon). Rotor ima tri faze, pa su ukupni gubici u bakru rotora:

$$P_{\mathrm{Cu}r} = 3\, R_r\, I_{rf}^{\,2}$$

- $P_{\mathrm{Cu}r}$ — ukupni gubici u bakru rotora (sve tri faze),
- $R_r$ — otpor po fazi,
- $I_{rf}$ — efektivna vrednost struje po fazi.

Ova formula radi u oba smera: ako znamo gubitke i struju, iz nje računamo otpor — što ćemo ovde i
uraditi.

### Mini-lekcija 7: Sprega zvezda i aproksimacija $U_{sf} \approx E_{sf}$

Kod sprege **zvezda** svaki fazni namotaj je vezan između jednog faznog provodnika i zvezdišta, pa
je napon na jednom namotaju (fazni napon) manji od linijskog za $\sqrt{3}$:

$$U_{sf} = \frac{U_s}{\sqrt{3}}$$

Statorski namotaj ima i svoj otpor i svoju reaktansu rasipanja, pa se deo dovedenog napona „potroši"
na njima; ostatak je indukovana EMS statora $E_{sf}$. Taj pad napona je u normalnim uslovima mali
(nekoliko procenata). Pošto u ovom zadatku **nemamo podatke** o otporu i reaktansi rasipanja
statora, ne možemo pad ni da izračunamo — zato usvajamo standardnu aproksimaciju:

$$E_{sf} \approx U_{sf}$$

To je legitiman inženjerski potez: kada podaci ne postoje, koristi se najbolja dostupna procena, a
greška koju time pravimo je reda veličine par procenata.

### Mini-lekcija 8: Koeficijent transformacije asinhronog motora i navojni sačinioci

Asinhroni motor radi kao transformator sa obrtnim sekundarom: isti obrtni fluks indukuje EMS i u
statorskom i u rotorskom namotaju. **Koeficijent transformacije** je po definiciji odnos faznih
EMS statora i **ukočenog (mirujućeg)** rotora:

$$m_e = \frac{N_s k_s}{N_r k_r} = \frac{E_{sf}}{E_{rfk}}$$

- $N_s,\ N_r$ — broj navojaka po fazi statora, odnosno rotora,
- $k_s,\ k_r$ — **rezultantni navojni sačinioci** statora i rotora,
- $E_{sf}$ — EMS po fazi statora,
- $E_{rfk}$ — EMS po fazi ukočenog rotora (zato ukočenog: samo tada su obe EMS na istoj
  frekvenciji, pa je njihov odnos čist odnos namotaja, bez uticaja klizanja).

Zašto se, za razliku od transformatora, pojavljuju navojni sačinioci $k_s$ i $k_r$? Kod
transformatora je namotaj **koncentričan** — svi navojci su na istom mestu na jezgru i njihove EMS
se sabiraju algebarski (prosto: $E \sim N$). Kod obrtne mašine namotaj je **raspoređen po obimu**
statora i rotora (u žlebovima na raznim uglovima), a pored toga navojci mogu biti **skraćenog
koraka** (tetivni), a ne dijametralni. Zbog toga EMS pojedinih navojaka nisu u fazi, sabiraju se
**vektorski**, i rezultanta je nešto manja od algebarskog zbira. Faktor koji to umanjenje opisuje
je navojni sačinilac $k \le 1$ (tipično $0{,}9\ldots 0{,}96$). Zato u odnosu EMS ne stoji goli
odnos brojeva navojaka $N_s/N_r$, nego odnos **efektivnih** brojeva navojaka $N_s k_s / N_r k_r$.

Poslednji sastojak: pošto merenja u zadatku važe za obrtni rotor, EMS ukočenog rotora nije data
direktno, ali je iz mini-lekcije 3 znamo: $E_{rfk} = E_{rf}/s$. Uvrštavanjem:

$$m_e = \frac{E_{sf}}{E_{rfk}} = \frac{E_{sf}}{\dfrac{E_{rf}}{s}} = s\cdot\frac{E_{sf}}{E_{rf}}$$

## Rešenje, korak po korak

### Korak 1: Otpor rotorskog namotaja iz gubitaka u bakru

**Zašto ovaj korak:** Otpor $R_r$ nam treba za Omov zakon rotorskog kola (iz kog ćemo izvući
klizanje), a nije zadat direktno — ali jesu zadati gubici u bakru i struja, pa ga računamo iz
Džulovog zakona (mini-lekcija 6).

Opšti oblik (gubici u tri faze rotora):

$$P_{\mathrm{Cu}r} = 3\, R_r\, I_{rf}^{\,2}$$

Rešimo po $R_r$: podelimo obe strane sa $3 I_{rf}^{\,2}$:

$$R_r = \frac{P_{\mathrm{Cu}r}}{3\, I_{rf}^{\,2}}$$

Uvrstimo brojeve ($P_{\mathrm{Cu}r} = 300\ \mathrm{W}$, $I_{rf} = 100\ \mathrm{A}$):

$$R_r = \frac{300}{3 \cdot 100^2} = \frac{300}{3 \cdot 10\,000} = \frac{300}{30\,000} = 0{,}01\ \mathrm{\Omega}$$

**Šta smo dobili:** Otpor od svega jednog stotog dela oma — vrlo mala vrednost, ali tipična za
rotorske namotaje snažnijih mašina: kroz njih teku velike struje (ovde $100\ \mathrm{A}$), pa
provodnici moraju biti debeli, a debeo provodnik ima mali otpor.

### Korak 2: Reaktansa rasipanja rotora na statorskoj frekvenciji

**Zašto ovaj korak:** Druga stvar koja nam treba za Omov zakon rotora je reaktansa rasipanja.
Zadata je induktivnost $L_{\gamma r}$, a reaktansu na statorskoj frekvenciji (tj. reaktansu
ukočenog rotora, mini-lekcija 4) dobijamo iz opšte veze reaktanse i induktivnosti.

Opšti oblik:

$$X_{\gamma r} = \omega_s L_{\gamma r} = 2\pi f_s\, L_{\gamma r}$$

- $\omega_s = 2\pi f_s$ — ugaona učestanost statorskih (mrežnih) veličina u $\mathrm{rad/s}$.

Uvrstimo brojeve ($f_s = 50\ \mathrm{Hz}$, $L_{\gamma r} = 6{,}114\cdot 10^{-4}\ \mathrm{H}$):

$$X_{\gamma r} = 2\pi \cdot 50 \cdot 6{,}114\cdot 10^{-4} = 314{,}159 \cdot 6{,}114\cdot 10^{-4} \approx 0{,}1920\ \mathrm{\Omega}$$

**Šta smo dobili:** Reaktansa rasipanja ($0{,}192\ \mathrm{\Omega}$) je oko 19 puta veća od
aktivnog otpora ($0{,}01\ \mathrm{\Omega}$). To je važno zapaziti: pri većim klizanjima rotorskom
strujom dominira reaktansa, a ne otpor — što će se lepo videti u sledećem koraku.

### Korak 3: Klizanje iz Omovog zakona rotorskog kola

**Zašto ovaj korak:** Sada imamo sve elemente rotorskog kola ($E_{rf}$, $I_{rf}$, $R_r$,
$X_{\gamma r}$), a jedina nepoznata u Omovom zakonu rotora (mini-lekcija 5) ostaje klizanje —
rešavamo jednačinu po $s$.

Polazna jednačina:

$$I_{rf} = \frac{E_{rf}}{\sqrt{R_r^{\,2} + \left(s\, X_{\gamma r}\right)^2}}$$

Rešavamo po $s$, korak po korak. Prvo pomnožimo obe strane imeniocem i podelimo sa $I_{rf}$, da
korenu „oslobodimo" jednu stranu:

$$\sqrt{R_r^{\,2} + \left(s\, X_{\gamma r}\right)^2} = \frac{E_{rf}}{I_{rf}}$$

Kvadriramo obe strane da se oslobodimo korena:

$$R_r^{\,2} + \left(s\, X_{\gamma r}\right)^2 = \left(\frac{E_{rf}}{I_{rf}}\right)^2$$

Prebacimo $R_r^{\,2}$ na desnu stranu:

$$\left(s\, X_{\gamma r}\right)^2 = \left(\frac{E_{rf}}{I_{rf}}\right)^2 - R_r^{\,2}$$

Korenujemo obe strane (obe su pozitivne, pa je to dozvoljeno bez dvoznačnosti):

$$s\, X_{\gamma r} = \sqrt{\left(\frac{E_{rf}}{I_{rf}}\right)^2 - R_r^{\,2}}$$

i na kraju podelimo sa $X_{\gamma r}$:

$$s = \frac{\sqrt{\left(\dfrac{E_{rf}}{I_{rf}}\right)^2 - R_r^{\,2}}}{X_{\gamma r}}$$

Sada uvrštavamo brojeve, deo po deo. Količnik $E_{rf}/I_{rf}$ je ukupna (prividna) impedansa
rotorskog kola:

$$\frac{E_{rf}}{I_{rf}} = \frac{22}{100} = 0{,}22\ \mathrm{\Omega}$$

Njen kvadrat i kvadrat otpora:

$$\left(0{,}22\right)^2 = 0{,}0484\ \mathrm{\Omega^2}, \qquad \left(0{,}01\right)^2 = 0{,}0001\ \mathrm{\Omega^2}$$

Razlika pod korenom i koren:

$$0{,}0484 - 0{,}0001 = 0{,}0483\ \mathrm{\Omega^2}, \qquad \sqrt{0{,}0483} \approx 0{,}2198\ \mathrm{\Omega}$$

Konačno:

$$s = \frac{0{,}2198}{0{,}1920} = 1{,}1446$$

Klizanje je bezdimenziona veličina (om podeljen omom), pa nema jedinicu.

**Šta smo dobili:** Klizanje **veće od 1**! Po tabeli iz mini-lekcije 1 to znači da mašina u datom
pogonskom stanju **nije u motornom režimu**, nego u **kočionom**: rotor se obrće suprotno od smera
obrtnog polja. Podatak deluje neobično, ali je račun nedvosmislen — impedansa rotora
($0{,}22\ \mathrm{\Omega}$) veća je nego što bi ikako mogla biti pri $s \le 1$ (maksimalno
$\sqrt{0{,}01^2 + 0{,}192^2} \approx 0{,}192\ \mathrm{\Omega}$ pri $s = 1$), pa klizanje mora biti
veće od 1.

> **Napomena o zaokruživanju:** Original računa sa zaokruženom vrednošću
> $X_{\gamma r} = 0{,}1920\ \mathrm{\Omega}$ i dobija $s = 1{,}1446$. Ako se račun sprovede sa
> punom preciznošću ($X_{\gamma r} = 0{,}19208\ \mathrm{\Omega}$), dobija se $s = 1{,}1442$ —
> razlika je u četvrtoj decimali i potpuno je nebitna. Zadržavamo vrednosti iz zbirke.

### Korak 4: Rotorska frekvencija

**Zašto ovaj korak:** Rotorska frekvencija je direktno tražena, a sa poznatim klizanjem dobija se
jednim množenjem (mini-lekcija 2).

Opšti oblik:

$$f_r = s \cdot f_s$$

Uvrstimo brojeve:

$$f_r = 1{,}1446 \cdot 50 = 57{,}2324\ \mathrm{Hz}$$

**Šta smo dobili:** Rotorska frekvencija **veća od mrežne** ($57{,}23 > 50\ \mathrm{Hz}$) — što je
moguće jedino u kočionom režimu. Fizički: rotor se okreće u susret polju, pa polje preseca
rotorske provodnike brže nego kad rotor miruje, i indukovane veličine osciluju brže od mrežnih.
Kod običnog motornog režima rotorska frekvencija bi bila svega par herca.

### Korak 5: Fazni napon statora i statorska EMS

**Zašto ovaj korak:** Za koeficijent transformacije treba nam EMS po fazi statora $E_{sf}$
(mini-lekcija 8). Nju ne znamo direktno, ali znamo mrežni napon — pa koristimo spregu zvezda i
aproksimaciju iz mini-lekcije 7.

Fazni napon kod sprege zvezda:

$$U_{sf} = \frac{U_s}{\sqrt{3}} = \frac{380}{\sqrt{3}} = \frac{380}{1{,}732} \approx 220\ \mathrm{V}$$

Pošto nemamo podatke o otporu i reaktansi rasipanja statorskog namotaja (pa pad napona na njima ne
možemo izračunati), usvajamo:

$$E_{sf} \approx U_{sf} \approx 220\ \mathrm{V}$$

**Šta smo dobili:** Statorska EMS od oko $220\ \mathrm{V}$ — standardna fazna vrednost za mrežu
$380\ \mathrm{V}$. Aproksimacija je nužna i uobičajena: greška koju pravimo je reda pada napona na
statorskoj impedansi, tipično svega nekoliko procenata.

### Korak 6: Koeficijent transformacije

**Zašto ovaj korak:** Ovo je poslednja tražena veličina. Po definiciji (mini-lekcija 8) potreban
nam je odnos $E_{sf}$ i EMS **ukočenog** rotora $E_{rfk}$ — a pošto je zadata EMS obrtnog rotora,
prvo je klizanjem „vraćamo" na vrednost ukočenog rotora.

Definicija i veza sa zadatim veličinama, u jednom lancu:

$$m_e = \frac{N_s k_s}{N_r k_r} = \frac{E_{sf}}{E_{rfk}} = \frac{E_{sf}}{\dfrac{E_{rf}}{s}} = s \cdot \frac{E_{sf}}{E_{rf}}$$

Prvi znak jednakosti je definicija (odnos efektivnih brojeva navojaka jednak je odnosu EMS na istoj
frekvenciji); drugi koristi $E_{rfk} = E_{rf}/s$ iz mini-lekcije 3; treći je samo sređivanje
dvojnog razlomka (deljenje razlomkom = množenje recipročnom vrednošću).

Uvrstimo brojeve ($s = 1{,}1446$, $E_{sf} \approx 220\ \mathrm{V}$, $E_{rf} = 22\ \mathrm{V}$):

$$m_e = 1{,}1446 \cdot \frac{220}{22} = 1{,}1446 \cdot 10 = 11{,}446$$

Koeficijent transformacije je odnos dve EMS (volt kroz volt), pa je bezdimenzion.

**Šta smo dobili:** $m_e \approx 11{,}4$ — statorski namotaj ima oko 11 puta veći efektivni broj
navojaka po fazi od rotorskog. Usput vidimo i da je EMS ukočenog rotora
$E_{rfk} = E_{rf}/s = 22/1{,}1446 \approx 19{,}2\ \mathrm{V}$ — manja od zadate $E_{rf} = 22\ \mathrm{V}$,
baš zato što je u kočionom režimu ($s > 1$) obrtni rotor „prebrzo" presecan poljem pa mu je EMS
veća nego u mirovanju.

## Česte greške i zamke

1. **Uvrstiti zadatu EMS $E_{rf} = 22\ \mathrm{V}$ direktno u definiciju koeficijenta
   transformacije.** Definicija traži EMS **ukočenog** rotora $E_{rfk}$, a zadata je EMS u
   pogonskom stanju sa klizanjem $s$. Ko zaboravi da podeli sa $s$ dobija pogrešno
   $m_e = 220/22 = 10$ umesto ispravnih $11{,}446$. U motornom režimu bi ta greška bila u drugu
   stranu i mnogo veća (jer je tamo $s \ll 1$).

2. **Zaboraviti da reaktansa rasipanja rotora zavisi od klizanja.** U Omovom zakonu rotora mora
   stajati $s X_{\gamma r}$, a ne $X_{\gamma r}$. Ko piše $I_{rf} = E_{rf}/\sqrt{R_r^2 + X_{\gamma r}^2}$
   izgubio je jedinu nepoznatu ($s$) iz jednačine i zadatak ne može ni da postavi. Podsetnik:
   otpor NE zavisi od klizanja, reaktansa DA.

3. **Zaboraviti trojku u formuli za gubitke.** Gubici $300\ \mathrm{W}$ su za **sve tri faze**, pa
   je $R_r = P_{\mathrm{Cu}r}/(3 I_{rf}^2) = 0{,}01\ \mathrm{\Omega}$. Bez trojke ispada
   $R_r = 0{,}03\ \mathrm{\Omega}$, pa onda i pogrešno klizanje
   ($\sqrt{0{,}0484-0{,}0009}/0{,}192 \approx 1{,}135$) — greška koja se tiho provuče kroz ceo zadatak.

4. **Uplašiti se rezultata $s > 1$ i „popraviti" ga.** Klizanje veće od 1 nije računska greška —
   to je legitiman kočioni režim rada. Student koji očekuje $s$ između 0 i 1 pomisliće da je negde
   pogrešio i počeće da „štimuje" račun. Uvek prvo proveri fiziku: režimi $s<0$ i $s>1$ postoje i
   sasvim su regularni.

5. **Pomešati linijski i fazni napon.** Stator je u zvezdi, pa je na jednom faznom namotaju
   $380/\sqrt{3} \approx 220\ \mathrm{V}$, a ne $380\ \mathrm{V}$. Sa $380\ \mathrm{V}$ bi ispalo
   $m_e \approx 19{,}8$ — skoro dvostruka greška.

## Rezime rezultata

| Veličina | Oznaka | Vrednost |
|---|---|---|
| Otpor rotorskog namotaja (po fazi) | $R_r$ | $0{,}01\ \mathrm{\Omega}$ |
| Reaktansa rasipanja rotora (na $f_s$) | $X_{\gamma r}$ | $0{,}1920\ \mathrm{\Omega}$ |
| **Klizanje** | $s$ | $1{,}1446$ |
| **Rotorska frekvencija** | $f_r$ | $57{,}2324\ \mathrm{Hz}$ |
| Fazni napon statora $\approx$ EMS statora | $U_{sf} \approx E_{sf}$ | $\approx 220\ \mathrm{V}$ |
| **Koeficijent transformacije** | $m_e$ | $11{,}446$ |
| Režim rada | — | kočioni ($s > 1$) |

## Provera smisla

**1) Dimenziona provera klizanja.** Pod korenom u koraku 3 stoji
$(\mathrm{V/A})^2 - \mathrm{\Omega}^2 = \mathrm{\Omega}^2$, koren daje $\mathrm{\Omega}$, i to se
deli reaktansom u $\mathrm{\Omega}$ — rezultat je čist broj, kako klizanje i mora biti. Takođe
$f_r = s f_s$ ima jedinicu $\mathrm{Hz}$, ispravno.

**2) Unakrsna provera preko rotorske impedanse.** Vratimo dobijeno klizanje u Omov zakon rotora:
stvarna reaktansa je $s X_{\gamma r} = 1{,}1446 \cdot 0{,}1920 = 0{,}2198\ \mathrm{\Omega}$,
impedansa $\sqrt{0{,}01^2 + 0{,}2198^2} = \sqrt{0{,}0001+0{,}0483} = \sqrt{0{,}0484} = 0{,}22\ \mathrm{\Omega}$,
pa je struja $I_{rf} = 22/0{,}22 = 100\ \mathrm{A}$ — tačno zadata vrednost. Račun je konzistentan.

**3) Provera konzistentnosti režima.** Tri nezavisna pokazatelja pričaju istu priču: $s > 1$
(kočenje), $f_r > f_s$ (polje preseca rotor brže od sinhronog), i $E_{rf} > E_{rfk}$
($22 > 19{,}2\ \mathrm{V}$ — obrtnom rotoru se indukuje više nego ukočenom). Sve tri stvari su
moguće istovremeno **samo** u kočionom režimu — da je i jedna od njih ispala drugačije, imali
bismo kontradikciju.

**4) Red veličine koeficijenta transformacije.** $m_e \approx 11{,}4$ znači da rotorski namotaj
ima red veličine deset puta manje efektivnih navojaka od statorskog — tipično za mašine sa
kaveznim ili niskonaponskim namotanim rotorom: rotorska strana je „niskonaponska/velikostrujna"
($E_{rfk} \approx 19\ \mathrm{V}$, $I_{rf} = 100\ \mathrm{A}$), statorska „visokonaponska/malostrujna"
($220\ \mathrm{V}$). Proizvod napona i struje po strani ostaje istog reda veličine, kao kod
transformatora — očekivano.
