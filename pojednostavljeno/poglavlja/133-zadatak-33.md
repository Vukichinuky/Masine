# Zadatak 33 — Proizvedeni (elektromagnetni) moment asinhronog motora iz stepena korisnog dejstva i raspodele gubitaka

## Postavka

Trofazni osmopolni asinhroni motor napaja se iz mreže učestanosti $50\ \mathrm{Hz}$. Stepen korisnog dejstva motora je $0{,}85$, a motor na vratilu daje mehaničku snagu od $50\ \mathrm{kW}$. Koliki je proizvedeni (elektromagnetni) moment ovog motora, ako su ukupni gubici u njemu raspoređeni tako da $60\ \%$ otpada na stator, a $40\ \%$ na rotor?

> **Prevod na običan jezik:** Imamo asinhroni motor koji iz električne mreže uzima električnu snagu, a na vratilu daje $50\ \mathrm{kW}$ mehaničke snage. Znamo koliko je motor "efikasan" (od svake primljene električne snage 85 % stigne do vratila, a 15 % se izgubi kao toplota). Rečeno nam je i kako se ti gubici dele: 60 % nastaje u statoru (nepokretnom delu), a 40 % u rotoru (obrtnom delu). Treba da izračunamo **moment koji elektromagnetne sile zaista proizvode** unutar motora — to nije isto što i snaga, jer moment zavisi i od brzine obrtanja. Brzinu ćemo saznati iz broja polova (motor je osmopolni) i frekvencije mreže ($50\ \mathrm{Hz}$).

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Broj faza | $m$ | $3$ | Motor se napaja iz trofazne mreže (tri naizmenična napona pomerena za trećinu periode). |
| Broj polova | $2p$ | $8$ (tj. $p = 4$ para polova) | Koliko magnetnih polova (naizmenično sever–jug) obrtno polje statora ima po obimu mašine; određuje brzinu obrtnog polja. |
| Frekvencija napajanja | $f_{\mathrm{s}}$ | $50\ \mathrm{Hz}$ | Učestanost naizmeničnog napona mreže; koliko puta u sekundi struja statora promeni smer tamo-nazad. |
| Stepen korisnog dejstva | $\eta$ | $0{,}85$ | Odnos korisne (izlazne mehaničke) i primljene (ulazne električne) snage; mera efikasnosti motora. |
| Predata (izlazna) mehanička snaga | $P_{\mathrm{m}}$ | $50\ \mathrm{kW} = 50000\ \mathrm{W}$ | Snaga koju motor stvarno isporučuje pogonjenoj mašini preko vratila. |
| Udeo gubitaka u statoru | — | $60\ \%$ ukupnih gubitaka | Deo ukupnih gubitaka koji nastaje u nepokretnom delu (bakar statorskog namotaja + gvožđe). |
| Udeo gubitaka u rotoru | — | $40\ \%$ ukupnih gubitaka | Deo ukupnih gubitaka koji nastaje u obrtnom delu (bakar/kavez rotora; mehanički gubici se ovde zanemaruju). |

**Traži se:** proizvedeni (elektromagnetni) moment $M$.

## Šta se traži i zašto

**Proizvedeni moment $M$** (zove se još i *elektromagnetni moment* ili *moment konverzije*) jeste moment koji nastaje dejstvom obrtnog magnetnog polja na struje rotora — dakle, moment koji elektromagnetna konverzija energije zaista "proizvede" unutar mašine. Inženjera on zanima iz dva razloga: (1) to je moment koji mehanički napreže vratilo, spojnicu i konstrukciju mašine, pa se prema njemu dimenzionišu ti delovi; (2) preko njega se proverava da li motor može da pokrene i vuče zadati teret (moment tereta mora biti manji od raspoloživog momenta motora).

Plan rešavanja, običnim jezikom:

1. Iz izlazne snage i stepena korisnog dejstva izračunamo koliko električne snage motor **uzima iz mreže** ($P_{\mathrm{el}}$).
2. Razlika između onoga što uđe i onoga što izađe su **ukupni gubici** ($P_{\mathrm{g}}$).
3. Po zadatoj raspodeli, $40\ \%$ tih gubitaka pripišemo rotoru — to su **gubici u bakru rotora** ($P_{\mathrm{Cu,r}}$), jer mehaničke gubitke zanemarujemo.
4. Saberemo mehaničku snagu i rotorske gubitke i dobijemo **snagu obrtnog polja** ($P_{\delta}$) — snagu koja magnetnim putem prelazi iz statora u rotor.
5. Iz frekvencije i broja pari polova izračunamo **sinhronu brzinu** ($n_{\mathrm{s}}$), tj. brzinu obrtnog polja.
6. Podelimo snagu obrtnog polja sinhronom **ugaonom** brzinom i dobijemo traženi moment: $M = P_{\delta}/\Omega_{\mathrm{s}}$.

## Potrebna teorija — mini-lekcije

### 1. Kako asinhroni motor radi (najkraće moguće)

Asinhroni (indukcioni) motor ima dva glavna dela: **stator** (nepokretni deo sa trofaznim namotajem) i **rotor** (obrtni deo, najčešće sa "kaveznim" namotajem od aluminijumskih ili bakarnih šipki). Kada se statorski namotaj priključi na trofaznu mrežu, struje u njemu stvaraju **obrtno magnetno polje** — magnetno polje stalne jačine koje kruži po obimu mašine stalnom brzinom (tzv. *sinhronom brzinom*). To polje preseca provodnike rotora, u njima **indukuje** napone i struje (otud ime "indukcioni motor"), a na provodnike sa strujom u magnetnom polju deluje sila — i rotor počinje da se obrće. Rotor se uvek obrće **malo sporije** od polja (zato "asinhroni" — nesinhroni): kad bi ga sustigao, polje više ne bi presecalo rotorske provodnike, ne bi bilo indukovane struje, pa ni momenta.

### 2. Tok snage kroz motor (bilans snaga)

Snaga kroz asinhroni motor prolazi kao kroz kaskadu, i na svakom "spratu" se deo izgubi kao toplota:

$$P_{\mathrm{el}} \;\xrightarrow{\;-\,P_{\mathrm{Cu,s}}\;-\;P_{\mathrm{Fe}}\;}\; P_{\delta} \;\xrightarrow{\;-\,P_{\mathrm{Cu,r}}\;}\; P_{\mathrm{c}} \;\xrightarrow{\;-\,P_{\mathrm{tr+v}}\;}\; P_{\mathrm{m}}$$

Redom, znače:

- $P_{\mathrm{el}}$ — **primljena električna snaga**: ono što motor uzme iz mreže (u zbirci se obeležava i $P_{\mathrm{s}}$, "statorska", jer ulazi kroz stator).
- $P_{\mathrm{Cu,s}}$ — **gubici u bakru statora**: toplota koja se razvija u statorskom namotaju zbog njegovog omskog otpora ("Džulovi" gubici, $\sim RI^2$).
- $P_{\mathrm{Fe}}$ — **gubici u gvožđu**: toplota u magnetnom kolu statora zbog vihornih struja i histerezisa (stalnog premagnetisavanja lima). Nastaju praktično samo u statoru, jer je učestanost premagnetisavanja rotorskog gvožđa vrlo mala.
- $P_{\delta}$ — **snaga obrtnog polja** (objašnjena u mini-lekciji 4).
- $P_{\mathrm{Cu,r}}$ — **gubici u bakru rotora**: toplota u rotorskom namotaju/kavezu zbog proticanja indukovanih rotorskih struja.
- $P_{\mathrm{c}}$ — **proizvedena (konvertovana) mehanička snaga**: snaga koju su elektromagnetne sile pretvorile iz električnog u mehanički oblik.
- $P_{\mathrm{tr+v}}$ — **mehanički gubici**: trenje u ležajevima i ventilacija (otpor vazduha, pogon ventilatora za hlađenje).
- $P_{\mathrm{m}}$ — **predata (korisna) mehanička snaga**: ono što stvarno stigne na vratilo.

Ukupni gubici su prosto sve što "iscuri" usput:

$$P_{\mathrm{g}} = P_{\mathrm{el}} - P_{\mathrm{m}} = P_{\mathrm{Cu,s}} + P_{\mathrm{Fe}} + P_{\mathrm{Cu,r}} + P_{\mathrm{tr+v}}$$

### 3. Stepen korisnog dejstva

**Stepen korisnog dejstva** $\eta$ (grčko "eta") je odnos korisne i primljene snage:

$$\eta = \frac{P_{\mathrm{m}}}{P_{\mathrm{el}}}$$

Formula je zapravo definicija efikasnosti bilo koje mašine: "koliko dobiješ podeljeno sa koliko uložiš". Broj je uvek manji od 1, jer se deo snage neizbežno pretvori u toplotu. Kada su nam poznati $\eta$ i izlazna snaga $P_{\mathrm{m}}$, ulaznu snagu dobijamo preuređenjem — obe strane pomnožimo sa $P_{\mathrm{el}}$ i podelimo sa $\eta$:

$$P_{\mathrm{el}} = \frac{P_{\mathrm{m}}}{\eta}$$

**Intuicija:** pošto je $\eta < 1$, deljenje sa $\eta$ daje broj **veći** od $P_{\mathrm{m}}$ — motor mora iz mreže da uzme *više* nego što isporuči, jer usput nešto izgubi. Ako ti ispadne da je ulaz manji od izlaza, negde si pomnožio umesto podelio.

### 4. Raspodela gubitaka na stator i rotor — i šta znači "zanemarujemo mehaničke gubitke"

Pogledajmo kaskadu iz mini-lekcije 2 i grupišimo gubitke po tome **gde nastaju**:

- **statorski gubici** = $P_{\mathrm{Cu,s}} + P_{\mathrm{Fe}}$ (bakar statora + gvožđe),
- **rotorski gubici** = $P_{\mathrm{Cu,r}} + P_{\mathrm{tr+v}}$ (bakar rotora + mehanički gubici, jer se trenje i ventilacija fizički dešavaju na obrtnom delu).

Zadatak kaže: 60 % ukupnih gubitaka nastaje u statoru, 40 % u rotoru. Da bismo iz rotorskih gubitaka izdvojili baš gubitke u bakru rotora $P_{\mathrm{Cu,r}}$ (koji su nam potrebni za snagu obrtnog polja), morali bismo znati mehaničke gubitke — a oni nisu dati. Zbirka zato koristi standardno inženjersko uprošćenje: **gubici u bakru rotora su dominantni u odnosu na mehaničke gubitke**, pa se mehanički gubici, u nedostatku preciznijih podataka, zanemaruju. Tada je ceo rotorski deo gubitaka bakarni:

$$P_{\mathrm{Cu,r}} \approx 0{,}4 \cdot P_{\mathrm{g}}$$

Isto zanemarenje ima još jednu posledicu: bez mehaničkih gubitaka, proizvedena i predata mehanička snaga se poklapaju,

$$P_{\mathrm{c}} \approx P_{\mathrm{m}}$$

jer je jedina razlika između njih upravo $P_{\mathrm{tr+v}}$ (pogledaj poslednju strelicu u kaskadi).

### 5. Snaga obrtnog polja $P_{\delta}$

**Snaga obrtnog polja** je snaga koja **magnetnim putem, kroz vazdušni zazor, prelazi sa statora na rotor**. Stator i rotor nisu električki spojeni — jedina "veza" među njima je magnetno polje u uskom vazdušnom procepu (zazoru) između njih. Širina tog zazora se tradicionalno obeležava grčkim slovom $\delta$ (delta), pa otuda indeks: $P_{\delta}$ = "snaga koja prolazi kroz zazor" (u literaturi i: *air-gap power*).

Gledano **sa rotorske strane**, sve što je magnetnim putem stiglo u rotor mora negde da završi: deo se pretvori u mehaničku snagu, a deo izgori kao toplota u rotorskom bakru:

$$P_{\delta} = P_{\mathrm{c}} + P_{\mathrm{Cu,r}}$$

Ova jednačina je prosto zakon održanja energije primenjen na rotor. Uz zanemarenje mehaničkih gubitaka ($P_{\mathrm{c}} \approx P_{\mathrm{m}}$, mini-lekcija 4) dobijamo oblik koji ćemo koristiti:

$$P_{\delta} \approx P_{\mathrm{m}} + P_{\mathrm{Cu,r}}$$

Gledano **sa statorske strane**, do iste snage se stiže "odozgo": od primljene električne snage oduzmu se gubici koji nastaju pre zazora (bakar statora i gvožđe): $P_{\delta} = P_{\mathrm{el}} - P_{\mathrm{Cu,s}} - P_{\mathrm{Fe}}$. Ovaj drugi put ćemo iskoristiti kao nezavisnu proveru na kraju.

### 6. Sinhrona brzina i broj pari polova

Obrtno polje statora obrne se za **jednu punu magnetnu periodu** (jedan par polova sever–jug) za vreme jedne periode mrežnog napona. Ako mašina po obimu ima $p$ **pari polova**, polje za jednu periodu napona pređe samo $1/p$ punog kruga — kao da je krug "izdeljen" na $p$ magnetnih ponavljanja. Zato polje napravi $f_{\mathrm{s}}/p$ obrtaja u sekundi, odnosno, pomnoženo sa 60:

$$n_{\mathrm{s}} = \frac{60 \cdot f_{\mathrm{s}}}{p}\ \ \left[\mathrm{min^{-1}}\right]$$

gde je:
- $n_{\mathrm{s}}$ — **sinhrona brzina**: brzina obrtanja obrtnog polja, u obrtajima u minuti ($\mathrm{min^{-1}}$, tj. "o/min");
- $f_{\mathrm{s}}$ — frekvencija statorskog (mrežnog) napona u $\mathrm{Hz}$;
- $p$ — **broj pari polova** (ne broj polova!).

**Zamka sa polovima:** "osmopolni motor" znači $2p = 8$ **polova**, dakle $p = 4$ **para** polova. U formulu ide broj *pari* polova. Ovo je najčešći izvor greške u ovakvim zadacima.

Za momenat nam ne treba brzina u obrtajima u minuti nego **ugaona brzina** u radijanima u sekundi. Jedan obrtaj je ugao od $2\pi$ radijana, a jedan minut je 60 sekundi, pa je veza:

$$\Omega_{\mathrm{s}} = \frac{2\pi \cdot n_{\mathrm{s}}}{60}\ \ \left[\mathrm{rad/s}\right]$$

### 7. Proizvedeni (elektromagnetni) moment: zašto baš $M = P_{\delta} / \Omega_{\mathrm{s}}$

Osnovna veza mehanike: **snaga = moment × ugaona brzina** ($P = M \cdot \Omega$). Pitanje je samo *koja snaga* i *koja brzina* idu uz elektromagnetni moment.

Elektromagnetni moment $M$ deluje između obrtnog polja i rotora. Isti taj moment, gledan iz dva referentna sistema, prenosi dve različite snage:

- **Polje** se obrće sinhronom brzinom $\Omega_{\mathrm{s}}$ i preko momenta $M$ predaje rotoru snagu $M \cdot \Omega_{\mathrm{s}}$ — a to je upravo sva snaga koja kroz zazor pređe na rotor, dakle $P_{\delta} = M \cdot \Omega_{\mathrm{s}}$.
- **Rotor** se obrće svojom (manjom) brzinom $\Omega$ i taj isti moment na njemu razvija mehaničku snagu $M \cdot \Omega = P_{\mathrm{c}}$.

Razlika te dve snage, $M(\Omega_{\mathrm{s}} - \Omega)$, nije nestala — to je tačno onaj deo koji izgori u rotorskom bakru, $P_{\mathrm{Cu,r}}$. Vidi se da je slika potpuno saglasna sa bilansom $P_{\delta} = P_{\mathrm{c}} + P_{\mathrm{Cu,r}}$ iz mini-lekcije 5. Iz prve od dve jednačine sledi radna formula:

$$M = \frac{P_{\delta}}{\Omega_{\mathrm{s}}}$$

Uvrstimo li $\Omega_{\mathrm{s}} = 2\pi n_{\mathrm{s}}/60$, dobijamo i praktični oblik sa brzinom u $\mathrm{min^{-1}}$:

$$M = \frac{P_{\delta}}{\dfrac{2\pi}{60} \cdot n_{\mathrm{s}}} = \frac{30}{\pi} \cdot \frac{P_{\delta}}{n_{\mathrm{s}}} \approx 9{,}55 \cdot \frac{P_{\delta}}{n_{\mathrm{s}}}$$

Broj $30/\pi = 9{,}5493\ldots \approx 9{,}55$ je čest "inženjerski faktor" koji vredi zapamtiti: moment u $\mathrm{Nm}$ je približno $9{,}55$ puta snaga u vatima podeljena brzinom u $\mathrm{min^{-1}}$.

**Još jedna posledica zanemarenja mehaničkih gubitaka:** korisni moment na vratilu je $M_{\mathrm{kor}} = P_{\mathrm{m}}/\Omega$. Pošto je $P_{\mathrm{c}} \approx P_{\mathrm{m}}$ i $P_{\mathrm{c}} = M \cdot \Omega$, sledi $M_{\mathrm{kor}} \approx M$ — proizvedeni moment je ujedno (približno) i korisni moment. Zato je rezultat ovog zadatka odmah upotrebljiv i kao moment koji motor daje teretu.

## Rešenje, korak po korak

### Korak 1: Primljena električna snaga $P_{\mathrm{el}}$

**Zašto ovaj korak:** Sve u ovom zadatku vrti se oko bilansa snaga, a bilans počinje od onoga što u motor *uđe*. Ulaznu snagu ne znamo direktno, ali je znamo posredno — preko izlazne snage i stepena korisnog dejstva (mini-lekcija 3).

Opšti oblik i preuređenje (obe strane definicije $\eta = P_{\mathrm{m}}/P_{\mathrm{el}}$ pomnožimo sa $P_{\mathrm{el}}$, pa podelimo sa $\eta$):

$$\eta = \frac{P_{\mathrm{m}}}{P_{\mathrm{el}}} \quad\Longrightarrow\quad P_{\mathrm{el}} = \frac{P_{\mathrm{m}}}{\eta}$$

Uvrštavanje brojeva:

$$P_{\mathrm{el}} = \frac{50000\ \mathrm{W}}{0{,}85} = 58823{,}5294\ \mathrm{W} \approx 58{,}82\ \mathrm{kW}$$

**Šta smo dobili:** Motor iz mreže uzima oko $58{,}8\ \mathrm{kW}$ da bi isporučio $50\ \mathrm{kW}$. Ulaz je veći od izlaza, kako i mora biti — razlika će se u sledećem koraku pokazati kao gubici.

### Korak 2: Ukupni gubici $P_{\mathrm{g}}$

**Zašto ovaj korak:** Raspodela "60 % stator / 40 % rotor" odnosi se na *ukupne* gubitke, pa prvo moramo znati koliko ukupni gubici iznose. Oni su, po zakonu održanja energije, prosto razlika ulazne i izlazne snage (mini-lekcija 2).

$$P_{\mathrm{g}} = P_{\mathrm{el}} - P_{\mathrm{m}}$$

Uvrštavanje brojeva:

$$P_{\mathrm{g}} = 58823{,}5294\ \mathrm{W} - 50000\ \mathrm{W} = 8823{,}5294\ \mathrm{W} \approx 8{,}82\ \mathrm{kW}$$

**Šta smo dobili:** U motoru se kao toplota gubi oko $8{,}8\ \mathrm{kW}$ — tačno 15 % primljene snage, što se slaže sa $\eta = 0{,}85$ (jer je $1 - \eta = 0{,}15$, a $0{,}15 \cdot 58823{,}5 = 8823{,}5$).

### Korak 3: Gubici u bakru rotora $P_{\mathrm{Cu,r}}$

**Zašto ovaj korak:** Za snagu obrtnog polja (sledeći korak) treba nam rotorski bakarni gubitak. Po zadatoj raspodeli, na rotor otpada 40 % ukupnih gubitaka; pošto mehaničke gubitke zanemarujemo (mini-lekcija 4), sav taj rotorski deo pripisujemo bakru rotora.

$$P_{\mathrm{Cu,r}} = 0{,}4 \cdot P_{\mathrm{g}}$$

Uvrštavanje brojeva:

$$P_{\mathrm{Cu,r}} = 0{,}4 \cdot 8823{,}5294\ \mathrm{W} = 3529{,}4117\ \mathrm{W} \approx 3{,}53\ \mathrm{kW}$$

**Šta smo dobili:** U rotorskom kavezu se gubi oko $3{,}5\ \mathrm{kW}$. To je snaga koju obrtno polje "donese" u rotor, a koja se ne pretvori u mehanički rad nego u toplotu.

### Korak 4: Snaga obrtnog polja $P_{\delta}$

**Zašto ovaj korak:** Elektromagnetni moment se računa iz snage obrtnog polja (mini-lekcija 7), pa nju moramo sastaviti. Gledano sa rotorske strane, ona je zbir proizvedene mehaničke snage i rotorskih bakarnih gubitaka (mini-lekcija 5); a proizvedena mehanička snaga je, uz zanemarene mehaničke gubitke, jednaka datoj predatoj snazi.

$$P_{\delta} = P_{\mathrm{c}} + P_{\mathrm{Cu,r}} \approx P_{\mathrm{m}} + P_{\mathrm{Cu,r}}$$

Uvrštavanje brojeva:

$$P_{\delta} = 50000\ \mathrm{W} + 3529{,}4117\ \mathrm{W} = 53529{,}4117\ \mathrm{W} \approx 53{,}53\ \mathrm{kW}$$

**Šta smo dobili:** Kroz vazdušni zazor sa statora na rotor magnetnim putem prelazi oko $53{,}5\ \mathrm{kW}$. Broj je logično između ulazne ($58{,}8\ \mathrm{kW}$) i izlazne ($50\ \mathrm{kW}$) snage — zazor je "na pola puta" kaskade: pre njega su otpali statorski gubici, posle njega otpadaju rotorski.

### Korak 5: Sinhrona brzina $n_{\mathrm{s}}$ i sinhrona ugaona brzina $\Omega_{\mathrm{s}}$

**Zašto ovaj korak:** Moment je snaga podeljena ugaonom brzinom — a za elektromagnetni moment to mora biti baš brzina obrtnog polja (mini-lekcija 7). Nju računamo iz frekvencije i broja pari polova (mini-lekcija 6). Motor je osmopolni, dakle $2p = 8$, pa je broj **pari** polova $p = 8/2 = 4$.

$$n_{\mathrm{s}} = \frac{60 \cdot f_{\mathrm{s}}}{p}$$

Uvrštavanje brojeva:

$$n_{\mathrm{s}} = \frac{60 \cdot 50}{4} = \frac{3000}{4} = 750\ \mathrm{min^{-1}}$$

Pretvaranje u ugaonu brzinu (jedan obrtaj $= 2\pi$ radijana, jedan minut $= 60$ sekundi):

$$\Omega_{\mathrm{s}} = \frac{2\pi \cdot n_{\mathrm{s}}}{60} = \frac{2\pi \cdot 750}{60} = 25\pi = 78{,}5398\ \mathrm{rad/s}$$

**Šta smo dobili:** Obrtno polje ovog motora kruži brzinom $750$ obrtaja u minuti. To je relativno sporo (dvopolni motor na istoj mreži imao bi $3000\ \mathrm{min^{-1}}$) — više polova znači sporije polje. Sporija mašina za istu snagu mora da razvije veći moment, što ćemo odmah i videti.

### Korak 6: Proizvedeni (elektromagnetni) moment $M$

**Zašto ovaj korak:** Ovo je cilj zadatka. Proizvedeni moment je odnos snage obrtnog polja i ugaone brzine obrtnog polja (mini-lekcija 7). Uz zanemarene mehaničke gubitke, dobijena vrednost je ujedno i korisni moment na vratilu.

Formula, pa razvoj do praktičnog oblika (u imenilac uvrstimo $\Omega_{\mathrm{s}} = \frac{2\pi}{60} n_{\mathrm{s}}$, pa dvojni razlomak sredimo množenjem brojioca i imenioca sa $\frac{60}{2\pi} = \frac{30}{\pi}$):

$$M = \frac{P_{\delta}}{\Omega_{\mathrm{s}}} = \frac{P_{\delta}}{\dfrac{2\pi}{60} \cdot n_{\mathrm{s}}} = \frac{30}{\pi} \cdot \frac{P_{\delta}}{n_{\mathrm{s}}} \approx 9{,}55 \cdot \frac{P_{\delta}}{n_{\mathrm{s}}}$$

Uvrštavanje brojeva (može na oba načina — prvo direktno preko $\Omega_{\mathrm{s}}$):

$$M = \frac{53529{,}4117\ \mathrm{W}}{78{,}5398\ \mathrm{rad/s}} = 681{,}5576\ \mathrm{Nm}$$

a isto daje i praktični oblik:

$$M = 9{,}55 \cdot \frac{53529{,}4117}{750} = 681{,}56\ \mathrm{Nm}$$

> **Napomena o originalu:** Zbirka piše faktor kao $9{,}55$, ali konačni rezultat $681{,}5576\ \mathrm{Nm}$ dobijen je tačnom vrednošću $30/\pi = 9{,}5493$. Sa zaokruženim $9{,}55$ dobilo bi se $681{,}61\ \mathrm{Nm}$ — razlika je zanemarljiva i potiče samo od zaokruživanja faktora, ne od greške u postupku.

**Šta smo dobili:** Elektromagnetne sile u ovom motoru proizvode moment od oko $682\ \mathrm{Nm}$. To je veliki moment — očekivano za sporohodu (osmopolnu) mašinu od $50\ \mathrm{kW}$: pri manjoj brzini ista snaga zahteva srazmerno veći moment.

## Česte greške i zamke

1. **Broj polova umesto broja pari polova.** "Osmopolni" znači $2p = 8$, dakle $p = 4$. Ko uvrsti $p = 8$ u $n_{\mathrm{s}} = 60 f_{\mathrm{s}}/p$, dobije $n_{\mathrm{s}} = 375\ \mathrm{min^{-1}}$ i dvostruko veći moment ($\approx 1363\ \mathrm{Nm}$) — pogrešno.
2. **Množenje umesto deljenja stepenom korisnog dejstva.** $P_{\mathrm{el}} = P_{\mathrm{m}} \cdot \eta = 42500\ \mathrm{W}$ je besmislica: ispalo bi da motor iz mreže uzima *manje* nego što daje, tj. da stvara energiju ni iz čega. Ulaz se dobija **deljenjem**: $P_{\mathrm{el}} = P_{\mathrm{m}}/\eta$. Brza provera: ulaz mora biti veći od izlaza.
3. **Deljenje snage brzinom u $\mathrm{min^{-1}}$ umesto u $\mathrm{rad/s}$.** Račun $53529{,}4/750 = 71{,}4$ nije moment u $\mathrm{Nm}$ — brzina prvo mora u ugaonu brzinu ($\Omega_{\mathrm{s}} = 2\pi n_{\mathrm{s}}/60$), ili se koristi gotov faktor $30/\pi \approx 9{,}55$.
4. **Pogrešna snaga uz sinhronu brzinu.** $M = P_{\mathrm{m}}/\Omega_{\mathrm{s}} = 636{,}6\ \mathrm{Nm}$ je pogrešno: uz sinhronu brzinu ide snaga obrtnog polja $P_{\delta}$, a uz mehaničku snagu išla bi brzina *rotora* $\Omega$ (koja je manja od sinhrone). Mešanje ta dva para daje broj koji nije nijedan od momenata.
5. **Zamena procenata.** Na rotor otpada $40\ \%$ gubitaka, ne $60\ \%$. Ko uzme $0{,}6 \cdot P_{\mathrm{g}} = 5294{,}1\ \mathrm{W}$ za rotorske gubitke, dobiće $P_{\delta} = 55294{,}1\ \mathrm{W}$ i $M = 704{,}0\ \mathrm{Nm}$ — pogrešno.

## Rezime rezultata

| Veličina | Oznaka | Vrednost |
|---|---|---|
| Primljena električna snaga | $P_{\mathrm{el}}$ | $58823{,}5294\ \mathrm{W} \approx 58{,}82\ \mathrm{kW}$ |
| Ukupni gubici | $P_{\mathrm{g}}$ | $8823{,}5294\ \mathrm{W} \approx 8{,}82\ \mathrm{kW}$ |
| Gubici u bakru rotora | $P_{\mathrm{Cu,r}}$ | $3529{,}4117\ \mathrm{W} \approx 3{,}53\ \mathrm{kW}$ |
| Snaga obrtnog polja | $P_{\delta}$ | $53529{,}4117\ \mathrm{W} \approx 53{,}53\ \mathrm{kW}$ |
| Sinhrona brzina | $n_{\mathrm{s}}$ | $750\ \mathrm{min^{-1}}$ |
| Sinhrona ugaona brzina | $\Omega_{\mathrm{s}}$ | $78{,}5398\ \mathrm{rad/s}$ |
| **Proizvedeni (elektromagnetni) moment** | $M$ | $\mathbf{681{,}5576\ \mathrm{Nm} \approx 681{,}6\ \mathrm{Nm}}$ |

## Provera smisla

**1. Dimenziona provera.** Vat je $\mathrm{W} = \mathrm{J/s} = \mathrm{Nm/s}$, a radijan je bezdimenzion, pa je

$$\frac{P_{\delta}}{\Omega_{\mathrm{s}}} = \frac{\mathrm{Nm/s}}{\mathrm{1/s}} = \mathrm{Nm}$$

— jedinica momenta, kako i treba.

**2. Nezavisan put do $P_{\delta}$ — sa statorske strane.** Snaga obrtnog polja mora se dobiti i "odozgo": od primljene snage oduzmemo statorskih $60\ \%$ gubitaka:

$$P_{\delta} = P_{\mathrm{el}} - 0{,}6 \cdot P_{\mathrm{g}} = 58823{,}5294 - 0{,}6 \cdot 8823{,}5294 = 58823{,}5294 - 5294{,}1176 = 53529{,}4118\ \mathrm{W}$$

Ista vrednost kao u Koraku 4 (do zaokruživanja) — bilans se zatvara sa obe strane zazora.

**3. Provera preko klizanja i korisnog momenta.** Iz teorije (mini-lekcija 7) sledi $P_{\mathrm{Cu,r}} = M(\Omega_{\mathrm{s}} - \Omega) = s \cdot P_{\delta}$, gde je $s$ *klizanje* — relativno zaostajanje rotora za poljem. Iz naših brojeva: $s = P_{\mathrm{Cu,r}}/P_{\delta} = 3529{,}4117/53529{,}4117 = 0{,}0659$, pa se rotor obrće brzinom $n = n_{\mathrm{s}}(1-s) = 750 \cdot 0{,}9341 = 700{,}5\ \mathrm{min^{-1}}$, tj. $\Omega = 2\pi \cdot 700{,}5/60 = 73{,}361\ \mathrm{rad/s}$. Korisni moment je tada

$$M_{\mathrm{kor}} = \frac{P_{\mathrm{m}}}{\Omega} = \frac{50000}{73{,}361} = 681{,}56\ \mathrm{Nm}$$

— identičan proizvedenom momentu, tačno kako teorija predviđa kad su mehanički gubici zanemareni. Usput, klizanje od $\approx 6{,}6\ \%$ je razumna vrednost za opterećen asinhroni motor.

**4. Red veličine.** Brza "džepna" procena: $M \approx 9{,}55 \cdot P/n = 9{,}55 \cdot 53529/750 \approx 682\ \mathrm{Nm}$. Za poređenje, dvopolni motor iste snage ($n_{\mathrm{s}} = 3000\ \mathrm{min^{-1}}$) imao bi četvrtinu ovog momenta ($\approx 170\ \mathrm{Nm}$) — veliki moment našeg motora je direktna posledica male brzine osmopolne mašine, pa je rezultat očekivan.
