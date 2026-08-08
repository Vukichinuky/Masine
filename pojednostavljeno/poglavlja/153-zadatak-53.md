# Zadatak 53 — Klosova jednačina: prevalno klizanje, nazivno klizanje i relativna polazna struja rotora

## Postavka

Trofazni asinhroni motor radi pri nazivnom naponu i nazivnoj učestanosti (frekvenciji). Poznato je da mu je **polazni moment** $1{,}65$ puta veći od nominalnog momenta, a **prevalni moment** $2{,}1$ puta veći od nominalnog momenta. Odrediti:

a) klizanje koje motor ima kada razvija moment jednak prevalnom (tzv. *prevalno klizanje*);

b) klizanje pri nazivnom momentu opterećenja (tzv. *nazivno klizanje*);

c) struju rotora pri pokretanju, izraženu relativno u odnosu na rotorsku struju pri nazivnom opterećenju.

Pri rešavanju zanemariti statorski omski otpor i gubitke usled trenja i ventilacije. Pretpostaviti da je omski otpor rotora konstantan (ne zavisi od klizanja).

> **Prevod na običan jezik:** O motoru ne znamo skoro ništa "u brojevima" — ni snagu, ni napon, ni struje. Znamo samo dva odnosa momenata sa njegove mehaničke karakteristike: koliki moment daje u trenutku uključenja (dok još stoji) i koliki mu je najveći moment koji uopšte može da razvije — oba izražena u odnosu na moment pri normalnom (nazivnom) radu. Samo iz ta dva broja treba da "rekonstruišemo" gde se na karakteristici nalaze dve važne tačke (pri kom klizanju je vrh karakteristike, a pri kom motor normalno radi), i još da procenimo koliko je puta struja rotora pri uključenju veća nego u normalnom radu. Alat koji to omogućava je Klosova jednačina — približna formula koja celu karakteristiku momenta opisuje pomoću samo dve veličine.

> **Napomena o originalu:** U originalnoj zbirci je treći deo rešenja greškom označen slovom **d)** umesto **c)** — sadržajno je to odgovor na tačku c) postavke i tako ga ovde i vodimo.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Odnos polaznog i nazivnog momenta | $M_{\mathrm{k}}/M_{\mathrm{n}}$ | $1{,}65$ | Koliko je puta moment koji motor razvija u trenutku pokretanja (dok rotor još stoji) veći od momenta pri nazivnom opterećenju. |
| Odnos prevalnog i nazivnog momenta | $M_{\mathrm{pr}}/M_{\mathrm{n}}$ | $2{,}1$ | Koliko je puta najveći moment koji motor uopšte može da razvije (vrh karakteristike) veći od nazivnog momenta. |
| Klizanje pri pokretanju | $s$ | $1$ | U trenutku uključenja rotor miruje, pa je klizanje po definiciji jednako jedinici (obrazloženje u teoriji ispod); u koracima rešenja uvrštavamo ga prosto kao $s = 1$. |
| Statorski omski otpor | $R_s$ | $\approx 0$ (zanemaren) | Pretpostavka zadatka — bez nje Klosova jednačina ne bi važila u ovom jednostavnom obliku. |
| Omski otpor rotora | $R'_r$ | konstantan | Pretpostavka: otpor rotorskog namotaja ne zavisi od klizanja (zanemaruje se potiskivanje struje u provodnicima rotora). |
| Gubici trenja i ventilacije | — | zanemareni | Mehanički gubici se ne uzimaju u obzir, pa je koristan moment jednak elektromagnetskom. |

Primeti: **svi podaci su bezdimenzioni odnosi.** Zato će i svi rezultati biti bezdimenzioni — klizanja (koja su ionako brojevi bez jedinice) i odnos dveju struja.

## Šta se traži i zašto

**a) Prevalno klizanje $s_{\mathrm{pr}}$.** To je klizanje pri kome motor razvija svoj najveći (prevalni) moment. Inženjera zanima jer deli karakteristiku momenta na **stabilni** deo (levo od vrha, gde motor normalno radi) i **nestabilni** deo (desno od vrha): ako opterećenje premaši prevalni moment, motor "prevali" — naglo se zaustavi. Plan: Klosovu jednačinu napišemo u obliku kvadratne jednačine, uvrstimo poznatu polaznu tačku ($s=1$, moment $M_{\mathrm{k}}$) i rešimo je po $s_{\mathrm{pr}}$.

**b) Nazivno klizanje $s_{\mathrm{n}}$.** To je klizanje pri kome motor razvija tačno nazivni moment — dakle klizanje u normalnom, projektovanom radnom režimu. Ono direktno određuje brzinu motora pod nazivnim opterećenjem i gubitke u rotoru. Plan: istu kvadratnu jednačinu sada rešimo po $s$, uz poznato $s_{\mathrm{pr}}$ iz tačke a) i poznat odnos $M_{\mathrm{pr}}/M_{\mathrm{n}} = 2{,}1$.

**c) Odnos polazne i nazivne struje rotora $I'_{r\mathrm{k}}/I'_{r\mathrm{n}}$.** Pri direktnom uključenju na mrežu motor vuče višestruko veću struju nego u normalnom radu — to zagreva namotaje i "obara" napon mreže, pa je ovaj odnos ključan podatak za izbor zaštite i načina pokretanja. Plan: iz ekvivalentne šeme napišemo izraz za struju rotora pri klizanju $s_{\mathrm{n}}$ i pri klizanju $s=1$, podelimo ih, i primetimo da se u količniku prirodno pojavljuje upravo prevalno klizanje $s_{\mathrm{pr}}$ — pa sve izračunamo iz već dobijenih $s_{\mathrm{pr}}$ i $s_{\mathrm{n}}$.

Plan rešavanja u celini:

1. Iz Klosove jednačine izvedemo kvadratnu jednačinu koja povezuje $s$, $s_{\mathrm{pr}}$ i odnos momenata.
2. Uvrstimo polaznu tačku ($s=1$) i dobijemo $s_{\mathrm{pr}}$ (od dva matematička rešenja biramo fizički smisleno).
3. Uvrstimo $s_{\mathrm{pr}}$ i odnos $M_{\mathrm{pr}}/M_{\mathrm{n}}$ i dobijemo $s_{\mathrm{n}}$ (opet biramo smisleno rešenje).
4. Napišemo kompleksne izraze za rotorsku struju pri nazivnom radu i pri polasku.
5. Njihov količnik svedemo na izraz u kome figurišu samo $s_{\mathrm{pr}}$ i $s_{\mathrm{n}}$, pa uvrstimo brojeve.

## Potrebna teorija — mini-lekcije

### 1. Klizanje

Asinhroni motor ima obrtno magnetsko polje statora koje se okreće **sinhronom brzinom** $n_{\mathrm{s}}$ (određenom učestanošću mreže i brojem pari polova). Rotor se okreće brzinom $n$, uvek nešto sporije od polja (zato se motor i zove *asinhroni*). Relativno zaostajanje rotora za poljem zove se **klizanje**:

$$s = \frac{n_{\mathrm{s}} - n}{n_{\mathrm{s}}}$$

- $s$ — klizanje (broj bez jedinice; često se izražava i u procentima);
- $n_{\mathrm{s}}$ — sinhrona brzina obrtnog polja;
- $n$ — stvarna brzina rotora.

Dve karakteristične vrednosti: kada rotor **miruje** ($n = 0$, trenutak uključenja), klizanje je $s = (n_{\mathrm{s}}-0)/n_{\mathrm{s}} = 1$; kada bi se rotor okretao tačno sinhronom brzinom ($n = n_{\mathrm{s}}$), bilo bi $s = 0$ (idealan prazan hod). Normalan rad motora odvija se pri malim klizanjima, tipično od par procenata do desetak procenata.

Intuicija: klizanje meri "koliko polje beži rotoru". Što rotor više zaostaje, to se u njegovim provodnicima indukuju veće struje — pa klizanje posredno određuje i moment i struju rotora.

### 2. Karakteristika momenta $M = f(s)$ i tri važne tačke

Elektromagnetski moment asinhronog motora zavisi od klizanja. Ako moment crtamo u funkciji klizanja, dobijamo krivu koja od $s=0$ (gde je $M=0$) raste, dostiže **maksimum**, pa prema $s=1$ opada. Na toj krivoj razlikujemo tri tačke:

- **Polazni (kratkospojni) moment $M_{\mathrm{k}}$** — moment pri $s = 1$, tj. u trenutku uključenja dok rotor još stoji. Indeks "k" potiče od "kratak spoj", jer zaustavljeni motor električno liči na transformator u kratkom spoju.
- **Prevalni moment $M_{\mathrm{pr}}$** — najveći moment koji motor može da razvije; javlja se pri **prevalnom klizanju $s_{\mathrm{pr}}$** (vrh krive).
- **Nazivni moment $M_{\mathrm{n}}$** — moment pri nazivnom (projektovanom) opterećenju; javlja se pri **nazivnom klizanju $s_{\mathrm{n}}$**, koje je malo (radna tačka je blizu $s=0$, na strmom levom delu krive).

Deo krive za $0 < s < s_{\mathrm{pr}}$ je **stabilna radna oblast**: ako se opterećenje malo poveća, motor malo uspori (klizanje poraste), moment poraste i uspostavi se nova ravnoteža. Desno od vrha ($s > s_{\mathrm{pr}}$) veće klizanje daje *manji* moment, pa se ravnoteža ne može održati — kroz tu oblast motor samo prolazi tokom zaleta.

Uz ovaj zadatak nema slike (nema je ni u originalu), pa krivu nacrtaj u glavi, kvazi-grafički: zamisli **brdo** gledano sa strane, sa klizanjem koje raste sleva nadesno. Levo podnožje brda je u $s = 0$ (moment nula), vrh je na $s = s_{\mathrm{pr}}$ (pokazaće se: oko $0{,}49$, dakle blizu sredine), a desna padina se spušta do $s = 1$, gde kriva još uvek ima pozitivnu visinu $M_{\mathrm{k}} = 1{,}65\,M_{\mathrm{n}}$ — nižu od vrha ($2{,}1\,M_{\mathrm{n}}$). Nazivna radna tačka ($s_{\mathrm{n}} \approx 0{,}12$) leži nisko na strmoj levoj padini, blizu podnožja. Povuci sada horizontalnu liniju na nekoj visini ispod vrha: ona seče krivu **dvaput** — jednom levo od vrha (stabilna padina) i jednom desno od njega (nestabilna padina; za dovoljno nisku liniju taj drugi presek pada čak desno od $s=1$, na matematičkom produžetku krive — baš kao odbačena rešenja $2{,}06$ i $1{,}91$ koja ćemo sresti u koracima 2 i 3). Upravo zato će nam svaka jednačina u ovom zadatku davati po dva rešenja, od kojih fizika bira jedno.

### 3. Odakle dolazi Klosova jednačina

Kada se statorski omski otpor zanemari ($R_s \approx 0$), izraz za moment asinhronog motora se izvodi iz ekvivalentne šeme (lekcija 5 dole detaljno opisuje šemu i njene simbole; ovde ih koristimo uz kratka objašnjenja ispod formule). Izvođenje ide u tri prikazana poteza:

1. **Moment iz snage obrtnog polja.** Snagu $P_{\mathrm{ob}}$ koju obrtno polje preko vazdušnog zazora prenese na rotor i moment vezuje sinhrona ugaona brzina polja: $M = P_{\mathrm{ob}}/\Omega_s$. Pošto motor radi na krutoj mreži stalne učestanosti, $\Omega_s$ je konstanta — dakle $M \propto P_{\mathrm{ob}}$.
2. **Snaga obrtnog polja iz struje.** U ekvivalentnoj šemi se sva snaga preneta rotoru razvija na "otporniku" $\sigma R'_r/s$, u sve tri faze: $P_{\mathrm{ob}} = 3\,|I'_r|^2 \cdot \dfrac{\sigma R'_r}{s}$.
3. **Struja iz šeme.** Rotorska grana šeme je redna veza otpornika $\sigma R'_r/s$ i ukupne reaktanse $X_{\gamma s} + \sigma X'_{\gamma r}$, pa je kvadrat modula struje napon na kvadrat kroz kvadrat modula impedanse: $|I'_r|^2 = \dfrac{U_{\mathrm{sf}}^2}{\left(\dfrac{\sigma R'_r}{s}\right)^{2} + \left(X_{\gamma s} + \sigma X'_{\gamma r}\right)^{2}}$.

Kada 3. uvrstimo u 2, pa rezultat u 1, i sve konstante srazmernosti ($3$ i $\Omega_s$) "sakrijemo" pod znak $\propto$, dobijamo:

$$M \;\propto\; U_{\mathrm{sf}}^2 \cdot \frac{\dfrac{\sigma R'_r}{s}}{\left(\dfrac{\sigma R'_r}{s}\right)^{2} + \left(X_{\gamma s} + \sigma X'_{\gamma r}\right)^{2}}$$

- $U_{\mathrm{sf}}$ — fazni napon statora (konstantan, jer motor radi na krutoj mreži);
- $R'_r$ — omski otpor rotora *sveden* na stator (preračunat kroz prenosni odnos namotaja, da bi se rotor i stator mogli crtati u istoj šemi);
- $X_{\gamma s}$, $X'_{\gamma r}$ — rasipna reaktansa statora i svedena rasipna reaktansa rotora (objašnjene u lekciji 5);
- $\sigma$ — koeficijent rasipanja (objašnjen u lekciji 5); za ovaj zadatak njegova brojna vrednost neće ni trebati;
- znak $\propto$ znači "srazmerno" — konstantu srazmernosti ne pišemo jer će se u svim količnicima skratiti.

Uvedimo skraćenicu $a = \sigma R'_r / s$ (to je "otporski" deo imenioca, jedini koji zavisi od klizanja) i $X = X_{\gamma s} + \sigma X'_{\gamma r}$ (ukupna reaktansa, konstanta). Tada je $M \propto a/(a^2+X^2)$. Da nađemo pri kom klizanju je moment najveći, tražimo maksimum funkcije $f(a) = a/(a^2+X^2)$. Izvod po $a$:

$$\frac{\mathrm{d}f}{\mathrm{d}a} = \frac{(a^2+X^2) - a\cdot 2a}{(a^2+X^2)^2} = \frac{X^2 - a^2}{(a^2+X^2)^2}$$

Izvod je nula kada je $a = X$, tj. kada je $\sigma R'_r/s = X$. Klizanje pri kome se to dešava je upravo prevalno klizanje:

$$s_{\mathrm{pr}} = \frac{\sigma R'_r}{X_{\gamma s} + \sigma X'_{\gamma r}}$$

Ovu formulu zapamti — trebaće nam ponovo u tački c)! Uvrštavanjem $a = X$ dobijamo najveći (prevalni) moment: $M_{\mathrm{pr}} \propto X/(2X^2) = 1/(2X)$. Sada podelimo moment pri proizvoljnom klizanju sa prevalnim momentom:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{\dfrac{a}{a^2+X^2}}{\dfrac{1}{2X}} = \frac{2aX}{a^2+X^2} = \frac{2}{\dfrac{a}{X} + \dfrac{X}{a}}$$

(u poslednjem koraku smo brojilac i imenilac podelili sa $aX$). Ostaje još da količnik $a/X$ izrazimo preko klizanja:

$$\frac{a}{X} = \frac{\sigma R'_r / s}{X} = \frac{1}{s}\cdot\frac{\sigma R'_r}{X} = \frac{s_{\mathrm{pr}}}{s}$$

pa dobijamo **Klosovu jednačinu**:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}} \tag{53.1}$$

- $M$ — moment koji motor razvija pri klizanju $s$ (bilo koja tačka na karakteristici $M=f(s)$);
- $M_{\mathrm{pr}}$ — prevalni moment;
- $s_{\mathrm{pr}}$ — prevalno klizanje.

Intuicija: Klosova jednačina kaže da je **cela karakteristika momenta određena samo jednom tačkom — svojim vrhom** $(s_{\mathrm{pr}}, M_{\mathrm{pr}})$. Sve ostalo (napon, reaktanse, otpori) "upakovano" je u ta dva broja. Zato je ovako moćna za zadatke poput našeg, gde o motoru znamo vrlo malo. Važno ograničenje: važi samo uz $R_s \approx 0$ i konstantne parametre rotora — upravo pretpostavke iz postavke zadatka.

Još jedno korisno zapažanje: izraz $\frac{s}{s_{\mathrm{pr}}} + \frac{s_{\mathrm{pr}}}{s}$ se **ne menja** ako $s/s_{\mathrm{pr}}$ zamenimo sa $s_{\mathrm{pr}}/s$ (sabirci samo zamene mesta). To znači da isti odnos momenata dobijamo za dva različita klizanja — jedno manje i jedno veće od $s_{\mathrm{pr}}$. Ta simetrija je razlog što će naše jednačine uvek imati **dva** rešenja, od kojih fizika bira jedno.

### 4. Klosova jednačina kao kvadratna jednačina i njena rešenja

Klosova jednačina u obliku (53.1) je nezgodna za rešavanje po klizanju. Preuredimo je. Uvedimo oznaku za odnos prevalnog momenta i momenta u posmatranoj tački:

$$\nu = \frac{M_{\mathrm{pr}}}{M}$$

- $\nu$ (grčko "ni") — čist broj, uvek $\nu \geq 1$, jer nijedan moment na karakteristici ne može biti veći od prevalnog.

Recipročna vrednost jednačine (53.1) glasi:

$$\nu = \frac{M_{\mathrm{pr}}}{M} = \frac{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}}{2}$$

Pomnožimo obe strane sa $2\,s\,s_{\mathrm{pr}}$ (time se svi razlomci "čiste": prvi sabirak $\frac{s}{s_{\mathrm{pr}}}\cdot s\,s_{\mathrm{pr}} = s^2$, drugi $\frac{s_{\mathrm{pr}}}{s}\cdot s\,s_{\mathrm{pr}} = s_{\mathrm{pr}}^2$):

$$2\,\nu\, s\, s_{\mathrm{pr}} = s^2 + s_{\mathrm{pr}}^2$$

Prebacivanjem svega na jednu stranu dobijamo **kvadratnu jednačinu**:

$$s^2 - 2\,\nu\, s\, s_{\mathrm{pr}} + s_{\mathrm{pr}}^2 = 0 \tag{53.2}$$

Lepota ove jednačine: potpuno je **simetrična** po $s$ i $s_{\mathrm{pr}}$ (zamena $s \leftrightarrow s_{\mathrm{pr}}$ je ne menja), pa je možemo rešavati po **bilo kojoj** od te dve veličine — po onoj koju ne znamo.

**Rešenje po $s_{\mathrm{pr}}$** (kada znamo $s$ i $\nu$). Gledajući (53.2) kao kvadratnu jednačinu po nepoznatoj $s_{\mathrm{pr}}$, sa koeficijentima $1$, $-2\nu s$ i $s^2$, obrazac za rešenja kvadratne jednačine daje:

$$s_{\mathrm{pr}1,2} = \frac{2\nu s \pm \sqrt{(2\nu s)^2 - 4\cdot 1\cdot s^2}}{2} = \frac{2\nu s \pm 2s\sqrt{\nu^2-1}}{2}$$

(pod korenom smo izvukli $4s^2$: $\sqrt{4\nu^2 s^2 - 4s^2} = \sqrt{4s^2(\nu^2-1)} = 2s\sqrt{\nu^2-1}$). Skraćivanjem sa 2:

$$s_{\mathrm{pr}1,2} = s\cdot\left(\nu \pm \sqrt{\nu^{2}-1}\,\right) \tag{53.3}$$

**Rešenje po $s$** (kada znamo $s_{\mathrm{pr}}$ i $\nu$) — zbog simetrije jednačine ima potpuno isti oblik, samo $s$ i $s_{\mathrm{pr}}$ zamene uloge:

$$s_{1,2} = s_{\mathrm{pr}}\cdot\left(\nu \pm \sqrt{\nu^{2}-1}\,\right) \tag{53.4}$$

Svaki od obrazaca daje **dva** rešenja (znak $+$ i znak $-$). To je matematički odraz simetrije Klosove krive o kojoj smo govorili: isti odnos momenata postoji u dve tačke karakteristike. Koje je rešenje fizički ispravno — odlučujemo u svakom koraku posebno, zdravorazumskim proverama (rešenje mora biti pozitivno, klizanje radne tačke mora biti malo i manje od prevalnog, prevalno klizanje realnog motora je manje od 1 itd.).

Uzgred, po Vietovim pravilima proizvod dva rešenja kvadratne jednačine $x^2+px+q=0$ jednak je slobodnom članu $q$. Za (53.3) to znači $s_{\mathrm{pr}1}\cdot s_{\mathrm{pr}2} = s^2$, a za (53.4) $s_1 \cdot s_2 = s_{\mathrm{pr}}^2$ — odlična besplatna kontrola računa, koju ćemo iskoristiti u "Proveri smisla".

### 5. Ekvivalentna šema i struja rotora; koeficijent rasipanja $\sigma$

Asinhroni motor se za proračune predstavlja **ekvivalentnom šemom** — električnim kolom koje se, gledano sa statorskih priključaka, ponaša isto kao motor. U njoj se pojavljuju: otpor statora $R_s$ (ovde zanemaren), rasipna reaktansa statora $X_{\gamma s}$ (predstavlja deo magnetskog fluksa statora koji se "rasipa" i ne obuhvata rotor), reaktansa magnećenja (predstavlja glavni fluks), te svedeni rotorski parametri $R'_r$ i $X'_{\gamma r}$. Ključni trik šeme: umesto stvarnog rotorskog otpora piše se $R'_r/s$ — deljenjem klizanjem se obuhvata i snaga koja se pretvara u mehaničku.

U ovoj zbirci se koristi tzv. **modifikovana (Γ) ekvivalentna šema**, u kojoj je grana magnećenja pomerena skroz na priključke. Cena tog pojednostavljenja je da se rotorski parametri koriguju **koeficijentom rasipanja** $\sigma$ — brojem malo većim od 1 (tipično $1{,}02$–$1{,}08$), koji uračunava to što ni fluks magnećenja ne obuhvata idealno oba namotaja. Za ovaj zadatak je bitno samo da je $\sigma$ **konstanta** koja ne zavisi od klizanja — videćemo da se u konačnom rezultatu potpuno skrati.

Γ-šema ima za nas još jednu ključnu posledicu: pošto grana magnećenja stoji direktno na naponu mreže, ona vuče svoju sopstvenu struju nezavisno od svega što se dešava u rotorskom kolu — pa se u izrazu za rotorsku struju **uopšte ne pojavljuje**. Rotorska grana je prosto napon podeljen sopstvenom impedansom, što je upravo ono što piše u sledećoj formuli (i zato u njoj "nema" reaktanse magnećenja).

Struja rotora (svedena na stator, u kompleksnom zapisu) iz te šeme, uz zanemaren $R_s$, pri proizvoljnom klizanju $s$ glasi:

$$\underline{I'}_r = \frac{U_{\mathrm{sf}}}{\sigma\cdot\dfrac{R'_r}{s} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

- $\underline{I'}_r$ — kompleksna (fazorska) vrednost svedene rotorske struje; podvlaka označava kompleksan broj;
- $U_{\mathrm{sf}}$ — fazni napon statora (uzet kao referentan, čisto realan);
- $j$ — imaginarna jedinica ($j^2 = -1$); član uz $j$ je reaktivni deo impedanse;
- ostale oznake kao u lekciji 3.

Fizički: imenilac je ukupna impedansa kola kroz koje teče rotorska struja — otporski deo $\sigma R'_r/s$ zavisi od klizanja (što je klizanje manje, otpor "izgleda" veći i struja je manja), a reaktivni deo je konstantan.

### 6. Moduo kompleksnog broja i količnik dve impedanse

Struje i impedanse u naizmeničnim kolima su kompleksni brojevi, ali ampermetar meri samo njihovu **efektivnu vrednost** — tj. **moduo** kompleksnog broja. Za kompleksan broj $z = x + jy$ moduo je:

$$|z| = \sqrt{x^2 + y^2}$$

Za količnik dva kompleksna broja važi da je moduo količnika jednak količniku modula:

$$\left|\frac{z_1}{z_2}\right| = \frac{|z_1|}{|z_2|}$$

To ćemo iskoristiti u tački c): odnos dve struje prvo sredimo kao količnik kompleksnih brojeva, a tek na kraju uzmemo module — tako dolazimo do odnosa onih vrednosti struja koje bi pokazao ampermetar.

## Rešenje, korak po korak

### Korak 1: Odnos $\nu$ za polaznu tačku karakteristike

**Zašto ovaj korak:** Da bismo iz (53.3) izračunali prevalno klizanje, potrebna nam je jedna *potpuno poznata* tačka karakteristike — tačka u kojoj znamo i klizanje i odnos momenta prema prevalnom. Jedina takva tačka je polazna: u njoj je klizanje sigurno $s=1$ (rotor miruje), a moment je $M_{\mathrm{k}}$.

Odnos $\nu$ za polaznu tačku je, po definiciji iz lekcije 4:

$$\nu = \frac{M_{\mathrm{pr}}}{M_{\mathrm{k}}}$$

Ali zadatak nam ne daje direktno $M_{\mathrm{pr}}/M_{\mathrm{k}}$, nego oba momenta u odnosu na *nazivni*. Zato količnik proširimo nazivnim momentom $M_{\mathrm{n}}$ (pomnožimo i podelimo njime — vrednost se ne menja):

$$\nu = \frac{M_{\mathrm{pr}}}{M_{\mathrm{k}}} = \frac{M_{\mathrm{n}}}{M_{\mathrm{k}}}\cdot\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}} = \frac{1}{M_{\mathrm{k}}/M_{\mathrm{n}}}\cdot\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}}$$

Uvrstimo zadate odnose $M_{\mathrm{k}}/M_{\mathrm{n}} = 1{,}65$ i $M_{\mathrm{pr}}/M_{\mathrm{n}} = 2{,}1$:

$$\nu = \frac{1}{1{,}65}\cdot 2{,}1 = \frac{2{,}1}{1{,}65} = 1{,}273$$

**Šta smo dobili:** Prevalni moment je $1{,}273$ puta veći od polaznog. Broj je veći od 1 (mora biti — prevalni moment je najveći na karakteristici), ali nije mnogo veći od 1, što nam kaže da je polazna tačka relativno "blizu" vrha karakteristike.

### Korak 2: Prevalno klizanje $s_{\mathrm{pr}}$ — rešenje tačke a)

**Zašto ovaj korak:** Sada imamo sve što obrazac (53.3) traži: klizanje poznate tačke ($s = 1$) i odnos $\nu = 1{,}273$. Rešavamo kvadratnu jednačinu (53.2) po nepoznatom prevalnom klizanju.

Obrazac (53.3):

$$s_{\mathrm{pr}1,2} = s\cdot\left(\nu \pm \sqrt{\nu^{2}-1}\,\right)$$

Prvo izračunajmo koren, deo po deo:

$$\nu^2 = 1{,}273^2 = 1{,}6205 \qquad \nu^2 - 1 = 0{,}6205 \qquad \sqrt{0{,}6205} = 0{,}7877$$

(namerno u korenu nosimo jednu decimalu više nego obično — odmah ćeš videti zašto). Sada oba rešenja, sa $s = 1$:

$$\begin{aligned}
s_{\mathrm{pr}1} &= 1\cdot\left(1{,}273 + 0{,}7877\right) = 2{,}0607 \approx 2{,}06\\
s_{\mathrm{pr}2} &= 1\cdot\left(1{,}273 - 0{,}7877\right) = 0{,}4853 \approx 0{,}485
\end{aligned}$$

(Da smo koren prerano zaokružili na tri decimale, $0{,}787$, oduzimanje bi dalo $1{,}273 - 0{,}787 = 0{,}486$ — pogrešna treća cifra samo zbog zaokruživanja. Sa neodsečenim decimalama izlazi $0{,}48543\ldots$, pa je $0{,}485$ iz zbirke ispravno zaokruženo.)

**Koje rešenje je ispravno?** Oba broja zadovoljavaju Klosovu jednačinu (to je ona simetrija iz lekcije 3), ali samo jedno opisuje naš motor. Rešenje $s_{\mathrm{pr}1} = 2{,}06$ bi značilo da se vrh karakteristike nalazi pri klizanju većem od 1 — tj. *van* celog opsega koji motor prolazi od uključenja ($s=1$) do radne tačke ($s$ blizu 0). Takav motor u toku zaleta nikada ne bi razvio moment veći od polaznog: njegov najveći moment u motorskom režimu bio bi baš $M_{\mathrm{k}} = 1{,}65\,M_{\mathrm{n}}$, pa tvrdnja iz postavke da motor ima prevalni moment $2{,}1\,M_{\mathrm{n}}$ ne bi imala smisla. Kod uobičajenih kaveznih motora vrh karakteristike leži između radne tačke i polaska, dakle $0 < s_{\mathrm{pr}} < 1$. Zato je fizički ispravno drugo rešenje:

$$\boxed{s_{\mathrm{pr}} = 0{,}485}$$

**Šta smo dobili:** Motor razvija najveći moment kada mu rotor zaostaje za poljem 48,5 % — tj. otprilike na polovini zaleta. To je prilično veliko prevalno klizanje (kod velikih motora je tipično $0{,}1$–$0{,}2$), što ukazuje na motor sa relativno velikim rotorskim otporom — dosledno tome, videćemo da mu je i nazivno klizanje veliko.

> **Napomena o originalu:** U zbirci na ovom mestu piše "Kad se u (53.3) uvrsti $s=1$ i $\nu = 1{,}45$" — to je štamparska greška: uvrštava se $\nu = 1{,}273$, kako je izračunato red iznad i kako pokazuju sami brojevi u nastavku originalnog računa ($1{,}273 \pm \sqrt{1{,}273^2 - 1}$). Konačni rezultati u zbirci su ispravni.

### Korak 3: Nazivno klizanje $s_{\mathrm{n}}$ — rešenje tačke b)

**Zašto ovaj korak:** Sada je situacija obrnuta nego u koraku 2: prevalno klizanje **znamo** ($s_{\mathrm{pr}} = 0{,}485$), a tražimo klizanje $s_{\mathrm{n}}$ one tačke u kojoj je moment jednak nazivnom. Za tu tačku je odnos momenata direktno zadat: $\nu = M_{\mathrm{pr}}/M_{\mathrm{n}} = 2{,}1$. Koristimo obrazac (53.4) — rešenje iste kvadratne jednačine, ovaj put po $s$.

Obrazac (53.4):

$$s_{1,2} = s_{\mathrm{pr}}\cdot\left(\nu \pm \sqrt{\nu^{2}-1}\,\right)$$

Koren, deo po deo:

$$\nu^2 = 2{,}1^2 = 4{,}41 \qquad \nu^2 - 1 = 3{,}41 \qquad \sqrt{3{,}41} = 1{,}847$$

Oba rešenja, sa $s_{\mathrm{pr}} = 0{,}485$:

$$\begin{aligned}
s_1 &= 0{,}485\cdot\left(2{,}1 + 1{,}847\right) = 0{,}485\cdot 3{,}947 = 1{,}91\\
s_2 &= 0{,}485\cdot\left(2{,}1 - 1{,}847\right) = 0{,}485\cdot 0{,}253 = 0{,}123
\end{aligned}$$

**Koje rešenje je ispravno?** Rešenje $s_1 = 1{,}91$ otpada iz dva razloga. Prvo, klizanje veće od 1 znači da se rotor okreće *suprotno* od obrtnog polja (režim kočenja), što sigurno nije normalan rad pod nazivnim opterećenjem. Drugo, nazivna radna tačka mora ležati na **stabilnom** delu karakteristike, tj. mora biti $s_{\mathrm{n}} < s_{\mathrm{pr}}$ — a $1{,}91 > 0{,}485$. Rešenje $s_2 = 0{,}123$ oba uslova ispunjava:

$$\boxed{s_{\mathrm{n}} = 0{,}123}$$

**Šta smo dobili:** Pod nazivnim opterećenjem rotor zaostaje za poljem 12,3 %. To je veliko nazivno klizanje (tipični motori imaju 2–8 %), ali potpuno saglasno sa velikim prevalnim klizanjem iz koraka 2 — sve govori da je reč o manjem motoru sa izraženim rotorskim otporom. Bitno je da je $s_{\mathrm{n}} = 0{,}123 < s_{\mathrm{pr}} = 0{,}485$, kao što na stabilnoj grani i mora biti.

> **Napomena o originalu:** U zbirci (str. 183) je prvo, odbačeno rešenje greškom označeno kao "$s_{\mathrm{n}} = 0{,}485\cdot\left(2{,}1+\sqrt{2{,}1^2-1}\right) = 1{,}91$", a drugo kao $s_2$ — ista oznaka $s_{\mathrm{n}}$ time je upotrebljena za dva različita broja. Ispravno obeležavanje je ono koje koristimo ovde: $1{,}91$ je samo prvi koren kvadratne jednačine ($s_1$), a nazivno klizanje je drugi koren — kako i sama zbirka odmah zatim ispravno zaključuje rečenicom "Nominalno klizanje motora iznosi $s_{\mathrm{n}} = 0{,}123$".

### Korak 4: Izrazi za rotorsku struju pri nazivnom radu i pri polasku

**Zašto ovaj korak:** Tačka c) traži odnos struja, a struje zavise od parametara šeme ($R'_r$, reaktanse, $\sigma$) koje *ne znamo brojčano*. Ipak, napišimo oba izraza — u sledećem koraku će se pokazati da se sve nepoznate skrate i da odnos zavisi samo od klizanja, koja smo već izračunali.

Iz izraza za rotorsku struju (lekcija 5), pri nazivnom radu klizanje je $s = s_{\mathrm{n}}$:

$$\underline{I'}_{r\mathrm{n}} = \frac{U_{\mathrm{sf}}}{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{n}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

Pri polasku je klizanje $s = 1$, pa se $R'_r/s$ svodi prosto na $R'_r$:

$$\underline{I'}_{r\mathrm{k}} = \frac{U_{\mathrm{sf}}}{\sigma\cdot R'_r + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

- $\underline{I'}_{r\mathrm{n}}$ — svedena rotorska struja pri nazivnom opterećenju;
- $\underline{I'}_{r\mathrm{k}}$ — svedena rotorska struja pri pokretanju (indeks "k" — kratak spoj, jer zaustavljeni motor liči na transformator u kratkom spoju).

Napon $U_{\mathrm{sf}}$ je u oba slučaja isti, jer motor i pri polasku i u radu visi na istoj mreži nazivnog napona.

**Šta smo dobili:** Dva izraza koja se razlikuju **samo** u otporskom članu imenioca: pri nazivnom radu on je $\sigma R'_r/s_{\mathrm{n}}$ (veliki, jer je $s_{\mathrm{n}}$ mali broj), a pri polasku samo $\sigma R'_r$ (mali). Zato je polazna struja veća — imenilac joj je manji. Koliko tačno veća, računamo dalje.

### Korak 5: Odnos struja — svođenje na $s_{\mathrm{pr}}$ i $s_{\mathrm{n}}$

**Zašto ovaj korak:** Podelimo dva izraza iz koraka 4. Cilj koraka: pokazati da se svi nepoznati parametri skraćuju.

Označimo, radi preglednosti, imenioce (impedanse) iz koraka 4 sa $\underline{Z}_{\mathrm{k}}$ (pri polasku) i $\underline{Z}_{\mathrm{n}}$ (pri nazivnom radu); struje su tada $\underline{I'}_{r\mathrm{k}} = U_{\mathrm{sf}}/\underline{Z}_{\mathrm{k}}$ i $\underline{I'}_{r\mathrm{n}} = U_{\mathrm{sf}}/\underline{Z}_{\mathrm{n}}$. Deljenje razlomkom je množenje njegovom recipročnom vrednošću:

$$\frac{\underline{I'}_{r\mathrm{k}}}{\underline{I'}_{r\mathrm{n}}} = \frac{U_{\mathrm{sf}}/\underline{Z}_{\mathrm{k}}}{U_{\mathrm{sf}}/\underline{Z}_{\mathrm{n}}} = \frac{U_{\mathrm{sf}}}{\underline{Z}_{\mathrm{k}}}\cdot\frac{\underline{Z}_{\mathrm{n}}}{U_{\mathrm{sf}}} = \frac{\underline{Z}_{\mathrm{n}}}{\underline{Z}_{\mathrm{k}}}$$

— napon $U_{\mathrm{sf}}$ se skratio, jer je isti u obe radne tačke. Ostao je količnik impedansi, i to *obrnut*: impedansa nazivne tačke ($\underline{Z}_{\mathrm{n}}$, imenilac struje $\underline{I'}_{r\mathrm{n}}$) došla je u brojilac, a impedansa polazne tačke u imenilac. Ispisano sa punim impedansama:

$$\frac{\underline{I'}_{r\mathrm{k}}}{\underline{I'}_{r\mathrm{n}}} = \frac{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{n}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}{\sigma\cdot R'_r + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

Sada i brojilac i imenilac ovog izraza podelimo konstantom $X_{\gamma s} + \sigma X'_{\gamma r}$ — time uz $j$ ostaje čista jedinica:

$$\frac{\underline{I'}_{r\mathrm{k}}}{\underline{I'}_{r\mathrm{n}}} = \frac{\dfrac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}}\cdot\dfrac{1}{s_{\mathrm{n}}} + j}{\dfrac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}} + j}$$

Pogledaj količnik koji se pojavio na oba mesta:

$$\frac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}}$$

To je **tačno prevalno klizanje** $s_{\mathrm{pr}}$ — formula koju smo izveli u lekciji 3 (prevalno klizanje uz zanemaren otpor statora)! Dakle:

$$\frac{\underline{I'}_{r\mathrm{k}}}{\underline{I'}_{r\mathrm{n}}} = \frac{\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j}{s_{\mathrm{pr}} + j}$$

**Šta smo dobili:** Svi nepoznati parametri motora ($R'_r$, obe reaktanse, koeficijent $\sigma$, pa i sam napon) su nestali iz izraza — odnos struja zavisi **isključivo** od dva klizanja koja smo već izračunali. Ovo je i glavna "poenta" zadatka: prevalno klizanje nije samo tačka na krivoj momenta, ono je i mera odnosa otpora i reaktanse rotorskog kola, pa prirodno iskače u svakom računu sa strujama.

### Korak 6: Brojčani odnos polazne i nazivne struje — rešenje tačke c)

**Zašto ovaj korak:** Izraz iz koraka 5 je kompleksan broj, a nas zanima odnos efektivnih vrednosti struja (ono što pokazuje ampermetar) — dakle moduo tog kompleksnog broja. Koristimo pravila iz lekcije 6.

Moduo količnika je količnik modula. Brojilac je kompleksan broj sa realnim delom $s_{\mathrm{pr}}/s_{\mathrm{n}}$ i imaginarnim delom 1; imenilac ima realni deo $s_{\mathrm{pr}}$ i imaginarni deo 1:

$$I'_{r\mathrm{k}} = \frac{\left|\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j\right|}{\left|s_{\mathrm{pr}} + j\right|}\cdot I'_{r\mathrm{n}} = \frac{\sqrt{\left(\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^{2} + 1}}{\sqrt{s_{\mathrm{pr}}^{2} + 1}}\cdot I'_{r\mathrm{n}}$$

Uvrstimo $s_{\mathrm{pr}} = 0{,}485$ i $s_{\mathrm{n}} = 0{,}123$, računajući deo po deo. Prvo količnik klizanja:

$$\frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} = \frac{0{,}485}{0{,}123} = 3{,}943$$

Zatim brojilac:

$$\sqrt{3{,}943^2 + 1} = \sqrt{15{,}55 + 1} = \sqrt{16{,}55} = 4{,}068$$

Pa imenilac:

$$\sqrt{0{,}485^2 + 1} = \sqrt{0{,}235 + 1} = \sqrt{1{,}235} = 1{,}111$$

I konačno:

$$I'_{r\mathrm{k}} = \frac{4{,}068}{1{,}111}\cdot I'_{r\mathrm{n}} = 3{,}66\cdot I'_{r\mathrm{n}} \approx \boxed{3{,}7\cdot I'_{r\mathrm{n}}}$$

**Šta smo dobili:** Pri direktnom uključenju na mrežu rotorska struja je oko 3,7 puta veća od one u nazivnom radu. Za asinhrone motore je to relativno *umeren* skok (mnogi motori imaju polaznu struju 5–7 puta veću od nazivne) — što se opet slaže sa slikom motora sa velikim rotorskim otporom: veliki otpor ograničava polaznu struju, ali "plaća" velikim nazivnim klizanjem.

> **Napomena o originalu:** Zbirka rezultat navodi kao $3{,}7$; preciznija vrednost je $3{,}66$, pa je $3{,}7$ prosto zaokruživanje na jednu decimalu — nema neslaganja.

## Česte greške i zamke

1. **Pogrešan $\nu$ u tački a).** Najčešća greška: u obrazac (53.3) se uvrsti $\nu = M_{\mathrm{pr}}/M_{\mathrm{n}} = 2{,}1$ umesto $\nu = M_{\mathrm{pr}}/M_{\mathrm{k}} = 1{,}273$. Zapamti: $\nu$ je odnos prevalnog momenta i momenta **u tački čije klizanje koristiš**. Pošto u tački a) koristimo polaznu tačku ($s=1$), moramo koristiti i njen moment — $M_{\mathrm{k}}$, ne $M_{\mathrm{n}}$. Odnos $2{,}1$ dolazi na red tek u tački b), gde radimo sa tačkom nazivnog momenta.

2. **Slepo uzimanje jednog od dva korena.** Obrasci (53.3) i (53.4) uvek daju dva rešenja i nijedno nije "automatski" ono sa znakom minus ili plus — bira se fizičkim rasuđivanjem. Ovde smo u oba slučaja zadržali manje rešenje ($0{,}485$ umesto $2{,}06$; $0{,}123$ umesto $1{,}91$), ali obrazloženje je bilo fizičko: prevalno klizanje realnog motora je između 0 i 1, a nazivna radna tačka mora biti na stabilnoj grani ($s_{\mathrm{n}} < s_{\mathrm{pr}}$).

3. **Ignorisanje imaginarne jedinice u odnosu struja.** Primamljivo je (a pogrešno) reći: "otpor u imeniocu se promenio sa $\sigma R'_r/s_{\mathrm{n}}$ na $\sigma R'_r$, dakle struja poraste $1/s_{\mathrm{n}} = 8{,}1$ puta". To zanemaruje reaktansu: impedansa ima i imaginarni deo, koji pri polasku (kada je otporski deo mali) postaje dominantan i bitno ograničava struju. Ispravan račun preko modula kompleksnih brojeva daje $3{,}7$, ne $8{,}1$.

4. **Mešanje $M_{\mathrm{k}}$ i $M_{\mathrm{pr}}$.** Polazni moment je moment pri $s=1$; prevalni je maksimalni moment. Kod ovog motora polazni ($1{,}65\,M_{\mathrm{n}}$) je manji od prevalnog ($2{,}1\,M_{\mathrm{n}}$), kao i kod većine motora — ali to su dve različite tačke karakteristike i ne smeju se poistovetiti.

5. **Zaboravljanje uslova važenja Klosove jednačine.** Jednačina (53.1) u ovom obliku važi samo uz zanemaren statorski otpor i konstantne parametre rotora — zato postavka te pretpostavke izričito navodi. Kod stvarnih motora (naročito manjih, gde $R_s$ nije zanemarljiv, i kaveznih sa izraženim potiskivanjem struje) Klosova jednačina je samo aproksimacija.

## Rezime rezultata

| Tražena veličina | Oznaka | Rezultat |
|---|---|---|
| a) Prevalno klizanje | $s_{\mathrm{pr}}$ | $0{,}485$ |
| b) Nazivno klizanje | $s_{\mathrm{n}}$ | $0{,}123$ |
| c) Polazna struja rotora u odnosu na nazivnu | $I'_{r\mathrm{k}}/I'_{r\mathrm{n}}$ | $3{,}66 \approx 3{,}7$ |

## Provera smisla

**1. Vietina kontrola korenova.** Za kvadratnu jednačinu (53.2) proizvod dva rešenja mora biti jednak slobodnom članu. U koraku 2 (rešavanje po $s_{\mathrm{pr}}$, slobodni član $s^2 = 1$):

$$s_{\mathrm{pr}1}\cdot s_{\mathrm{pr}2} = 2{,}06 \cdot 0{,}485 = 1{,}00 = s^2 \checkmark$$

U koraku 3 (rešavanje po $s$, slobodni član $s_{\mathrm{pr}}^2 = 0{,}485^2 = 0{,}235$):

$$s_1\cdot s_2 = 1{,}91\cdot 0{,}123 = 0{,}235 = s_{\mathrm{pr}}^2 \checkmark$$

Oba računa prolaze — korenovi su izračunati ispravno.

**2. Vraćanje rezultata u Klosovu jednačinu.** Ako su $s_{\mathrm{pr}} = 0{,}485$ i $s_{\mathrm{n}} = 0{,}123$ tačni, Klosova jednačina mora u nazivnoj tački vratiti odnos $M_{\mathrm{n}}/M_{\mathrm{pr}} = 1/2{,}1 = 0{,}476$:

$$\frac{M_{\mathrm{n}}}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{0{,}123}{0{,}485} + \dfrac{0{,}485}{0{,}123}} = \frac{2}{0{,}254 + 3{,}943} = \frac{2}{4{,}197} = 0{,}4765 \approx 0{,}476 \checkmark$$

(sitna razlika na trećoj decimali — $0{,}4765$ umesto tačno $0{,}476$ — potiče od zaokruživanja $s_{\mathrm{pr}}$ i $s_{\mathrm{n}}$ na tri cifre; sa nezaokruženim klizanjima dobija se tačno $0{,}47619 = 1/2{,}1$). Isto tako, u polaznoj tački ($s=1$) mora se dobiti $M_{\mathrm{k}}/M_{\mathrm{pr}} = 1{,}65/2{,}1 = 0{,}786$:

$$\frac{M_{\mathrm{k}}}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{1}{0{,}485} + \dfrac{0{,}485}{1}} = \frac{2}{2{,}062 + 0{,}485} = \frac{2}{2{,}547} = 0{,}785 \approx 0{,}786 \checkmark$$

(sitna razlika na trećoj decimali potiče od zaokruživanja $s_{\mathrm{pr}}$ na tri cifre).

**3. Poredak veličina.** Dobijeno je $0 < s_{\mathrm{n}} = 0{,}123 < s_{\mathrm{pr}} = 0{,}485 < 1$ — tačno onakav raspored kakav mora imati svaki normalan asinhroni motor: radna tačka na stabilnoj grani, vrh karakteristike između radne tačke i polaska. Odnos struja $3{,}7$ je bezdimenzion i veći od 1 (polazna struja mora biti veća od nazivne, jer je pri polasku otporski deo impedanse najmanji), a manji od grubog gornjeg limita $1/s_{\mathrm{n}} = 8{,}1$ koji bi važio kad reaktansi ne bi bilo — sve je u očekivanim granicama.
