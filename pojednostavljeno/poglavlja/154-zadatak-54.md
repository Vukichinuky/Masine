# Zadatak 54 — Iz odnosa gubitaka opterećenja do prevalnog klizanja, prevalnog i polaznog momenta

## Postavka

Gubici usled opterećenja trofaznog kaveznog asinhronog motora kod prevalnog momenta, pri nazivnom naponu i nazivnoj frekvenciji, **9 puta su veći** od gubitaka usled opterećenja kod nazivnog momenta. Nazivno klizanje iznosi $s_{\mathrm{n}} = 0{,}028$. Naći:

a) klizanje kod prevalnog momenta,
b) prevalni moment,
c) polazni moment.

Momente izraziti **relativno, u odnosu na nazivni moment**. Zanemariti statorski omski otpor i gubitke trenja i ventilacije. Pretpostaviti da su reaktanse i otpor rotora konstantni (nezavisni od klizanja).

**Podaci o motoru:** 18,4 kW, 230 V, 60 Hz.

> **Prevod na običan jezik:** Imamo kavezni asinhroni motor. Neko je izmerio (ili nam je rečeno) samo jedno: kada motor radi u tački prevalnog (maksimalnog) momenta, gubici koji zavise od opterećenja su tačno 9 puta veći nego kada motor radi u nazivnoj tački. Znamo još i nazivno klizanje (2,8 %). Iz ta dva podatka treba da "rekonstruišemo" ceo oblik momentne karakteristike motora: koliko iznosi klizanje u prevalnoj tački, koliki je maksimalni moment koji motor uopšte može da razvije (izražen kao "toliko i toliko puta nazivni moment") i koliki moment motor daje u trenutku polaska (kada rotor još stoji). Trik zadatka: gubici zavisni od opterećenja su, uz date pretpostavke, samo gubici u bakru rotora, a oni rastu sa kvadratom rotorske struje — pa nam odnos gubitaka odaje odnos struja, a odnos struja (preko ekvivalentne šeme) odaje odnos klizanja. Kad znamo klizanja, Klosova jednačina daje sve momente.

> **Napomena o originalu:** U originalnoj zbirci rešenje trećeg dela zadatka je greškom obeleženo slovom **d)** iako se postavka završava tačkom **c)** — ovde je ispravljeno u c). Takođe, original u jednom međukoraku odnos struja piše sa indeksom $I'_{\mathrm{sn}}$ (statorski indeks) umesto $I'_{\mathrm{rn}}$ (rotorski), a u konačnoj formuli za prevalno klizanje koristi oznake $I_{\mathrm{s,pr}}/I_{\mathrm{sn}}$ — reč je o nedoslednosti u indeksima, a ne o drugoj fizičkoj veličini: celo izvođenje je rađeno za **rotorsku** struju, pa ovde svuda dosledno pišemo $I'_{r,\mathrm{pr}}/I'_{r\mathrm{n}}$. Svi brojčani rezultati originala su tačni i ovde su potvrđeni računom.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna snaga motora | $P_{\mathrm{n}}$ | $18{,}4\ \mathrm{kW}$ | Mehanička snaga koju motor trajno daje na vratilu u nazivnoj radnoj tački. (U ovom zadatku se **ne koristi u računu** — vidi "Česte greške".) |
| Nazivni napon | $U_{\mathrm{n}}$ | $230\ \mathrm{V}$ | Linijski napon mreže za koji je motor projektovan. (Takođe se ne koristi brojčano — bitno je samo da je napon *nazivan i konstantan*.) |
| Nazivna frekvencija | $f_{\mathrm{n}}$ | $60\ \mathrm{Hz}$ | Frekvencija napona napajanja; određuje sinhronu brzinu. (Ne ulazi u račun jer radimo sa relativnim veličinama.) |
| Nazivno klizanje | $s_{\mathrm{n}}$ | $0{,}028$ | Relativno zaostajanje rotora za obrtnim poljem u nazivnoj tački: rotor se obrće $2{,}8\ \%$ sporije od polja. |
| Odnos gubitaka opterećenja | $P_{\mathrm{Cu,pr}}/P_{\mathrm{Cu,n}}$ | $9$ | Gubici u bakru rotora u prevalnoj tački su 9 puta veći nego u nazivnoj tački. |
| Statorski otpor | $R_s$ | $\approx 0$ (zanemaren) | Pretpostavka zadatka: omski otpor statorskog namotaja ne uzimamo u obzir. |
| Gubici trenja i ventilacije | — | zanemareni | Pretpostavka zadatka: mehanički gubici se ne računaju. |
| Parametri rotora | $R_r,\ X$ | konstantni | Pretpostavka zadatka: otpor i reaktanse ne zavise od klizanja (nema potiskivanja struje u štapovima kaveza). |

**Traži se:** a) prevalno klizanje $s_{\mathrm{pr}}$; b) prevalni moment $M_{\mathrm{pr}}/M_{\mathrm{n}}$; c) polazni moment $M_{\mathrm{k}}/M_{\mathrm{n}}$.

## Šta se traži i zašto

**a) Prevalno klizanje $s_{\mathrm{pr}}$.** To je klizanje pri kome momentna karakteristika $M(s)$ asinhronog motora dostiže svoj maksimum. Inženjera zanima jer razdvaja **stabilni** deo karakteristike (radni deo, $s < s_{\mathrm{pr}}$, gde porast opterećenja povećava moment) od **nestabilnog** dela ($s > s_{\mathrm{pr}}$, gde bi dodatno opterećenje "prevalilo" motor u zaustavljanje — otuda i naziv). Plan: odnos gubitaka $9$ pretvorićemo u odnos rotorskih struja $3$, zatim iz ekvivalentne šeme napisati rotorsku struju u obe tačke, formirati njihov količnik i iz njega izraziti $s_{\mathrm{pr}}$.

**b) Prevalni moment $M_{\mathrm{pr}}$.** To je najveći moment koji motor uopšte može da razvije pri nazivnom naponu i frekvenciji. On određuje **preopteretljivost** motora: ako radni mehanizam zatraži više od $M_{\mathrm{pr}}$, motor staje. Plan: kad znamo $s_{\mathrm{n}}$ i $s_{\mathrm{pr}}$, Klosova jednačina (veza $M$ i $s$ preko samo ta dva klizanja) primenjena u nazivnoj tački direktno daje odnos $M_{\mathrm{pr}}/M_{\mathrm{n}}$.

**c) Polazni moment $M_{\mathrm{k}}$.** To je moment koji motor razvija u prvom trenutku polaska, dok rotor još stoji ($s = 1$). Inženjera zanima jer odlučuje **da li motor uopšte može da pokrene** priključeni teret direktnim uključenjem na mrežu. Plan: ista Klosova jednačina, samo sa $s = 1$, daje $M_{\mathrm{k}}/M_{\mathrm{pr}}$, a množenjem sa rezultatom iz b) dobijamo traženi odnos $M_{\mathrm{k}}/M_{\mathrm{n}}$.

Plan rešavanja u celini (5 koraka, običnim jezikom):
1. Utvrdimo da su "gubici usled opterećenja" ovde tačno gubici u bakru rotora i iz odnosa $9$ izvučemo odnos struja $3$ (jer gubici idu sa kvadratom struje).
2. Napišemo rotorsku struju iz ekvivalentne šeme (bez $R_s$) za nazivno i za prevalno klizanje.
3. Podelimo te dve struje; u količniku se sve nepoznate impedanse skrate i ostane izraz koji zavisi **samo** od $s_{\mathrm{pr}}/s_{\mathrm{n}}$ — rešimo ga po $s_{\mathrm{pr}}$.
4. Klosova jednačina u nazivnoj tački → $M_{\mathrm{pr}}/M_{\mathrm{n}}$.
5. Klosova jednačina u polasku ($s=1$) → $M_{\mathrm{k}}/M_{\mathrm{pr}}$, pa ulančavanjem $M_{\mathrm{k}}/M_{\mathrm{n}}$.

## Potrebna teorija — mini-lekcije

### 1. Bilans snaga asinhronog motora i "gubici usled opterećenja"

Snaga u asinhronom motoru putuje ovako: motor iz mreže uzima električnu snagu $P_1$; deo se izgubi u bakru statora ($P_{\mathrm{Cu,s}} = q_s I_s^2 R_s$, gde je $q_s$ broj faza statora) i u gvožđu statora ($P_{\mathrm{Fe}}$, histerezis i vihorne struje); ostatak — **snaga obrtnog polja** $P_{\mathrm{ob}}$ (zove se i snaga vazdušnog zazora) — prelazi preko zazora na rotor. Na rotoru se $P_{\mathrm{ob}}$ deli na dva dela, i ta podela je jedna od najlepših formula teorije asinhronih mašina:

$$P_{\mathrm{Cu,r}} = s \cdot P_{\mathrm{ob}}, \qquad P_{\mathrm{meh}} = (1-s)\cdot P_{\mathrm{ob}}$$

- $P_{\mathrm{Cu,r}}$ — gubici u bakru (kod kaveznog motora: u aluminijumu/bakru štapova) rotora,
- $P_{\mathrm{meh}}$ — unutrašnja mehanička snaga (od nje se još oduzmu gubici trenja i ventilacije da se dobije korisna snaga na vratilu),
- $s$ — klizanje.

Odakle ta podela? Moment $M$ koji polje prenosi na rotor isti je i za polje i za rotor, ali se polje obrće sinhronom ugaonom brzinom $\Omega_s$, a rotor brzinom $\Omega = (1-s)\Omega_s$. Snaga polja je $P_{\mathrm{ob}} = M\,\Omega_s$, mehanička snaga rotora $P_{\mathrm{meh}} = M\,\Omega = (1-s)\,M\,\Omega_s$, pa razlika $s\,M\,\Omega_s = s\,P_{\mathrm{ob}}$ nema gde da završi osim kao toplota u rotorskom kolu. Intuicija: klizanje je "procenat snage polja koji izgori u rotoru".

**Koji su gubici "usled opterećenja"?** Gubici u motoru se dele na one koji zavise od opterećenja i one koji (približno) ne zavise. Gubici u gvožđu zavise od napona i frekvencije (koji su ovde nazivni i konstantni), gubici trenja i ventilacije od brzine — obe grupe su praktično **konstantne** i ne računaju se u gubitke opterećenja. Od opterećenja zavise gubici u bakru, jer struje rastu sa opterećenjem: $P_{\mathrm{Cu}} \propto I^2$. Pošto zadatak izričito kaže da statorski otpor zanemarujemo ($R_s \approx 0 \Rightarrow P_{\mathrm{Cu,s}} \approx 0$), **jedini gubici usled opterećenja su gubici u bakru rotora**:

$$P_{\mathrm{Cu}} = q_r \cdot I_r^2 \cdot R_r$$

- $q_r$ — broj faza rotora (kod kaveza: ekvivalentni broj faza),
- $I_r$ — efektivna vrednost struje rotora,
- $R_r$ — otpor jedne faze rotora.

Ključna posledica: pošto su $q_r$ i $R_r$ konstante, odnos gubitaka u dve radne tačke jednak je **kvadratu odnosa struja**.

### 2. Rotorska struja iz ekvivalentne šeme (statorski otpor zanemaren)

Asinhroni motor se za račun predstavlja ekvivalentnom šemom po fazi, sličnom šemi transformatora: napon $\underline{U}_{\mathrm{sfn}}$ (nazivni **fazni** napon statora) tera struju kroz rasipnu reaktansu statora $X_{\gamma s}$, granu magnećenja i svedeno rotorsko kolo. Kada se otpor statora zanemari i šema svede na praktičan oblik (grana magnećenja pomerena na priključke, uz korekcioni **koeficijent rasipanja** $\sigma$ koji obuhvata činjenicu da statorsko i rotorsko polje nisu idealno spregnuti), rotorska struja svedena na stator, u kompleksnom (fazorskom) zapisu, iznosi:

$$\underline{I}'_r = \frac{\underline{U}_{\mathrm{sfn}}}{\sigma\cdot\dfrac{R'_r}{s} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

- $\underline{I}'_r$ — fazor rotorske struje **svedene na stator** (prim označava svođenje po broju navojaka, kao kod transformatora),
- $R'_r$ — svedeni otpor rotora; deljenje sa $s$ ($R'_r/s$) je standardni trik kojim se rotorsko kolo, koje stvarno radi na klizajućoj frekvenciji $s\cdot f$, preračuna na statorsku frekvenciju — tada član $R'_r/s$ automatski "u sebi nosi" i gubitke u bakru rotora i mehaničku snagu,
- $X_{\gamma s}$, $X'_{\gamma r}$ — rasipne reaktanse statora i (svedena) rotora: predstavljaju delove magnetnog fluksa koji obuhvate samo jedan namotaj i ne učestvuju u prenosu snage,
- $\sigma$ — koeficijent rasipanja (bezdimenzioni broj blizak jedinici); za ovaj zadatak njegova tačna vrednost je **potpuno nebitna**, jer će se u količniku struja skratiti,
- $j$ — imaginarna jedinica.

Struktura izraza je prosto Omov zakon za redno kolo: napon podeljen impedansom, gde impedansa ima realni (aktivni) deo $\sigma R'_r/s$, koji **zavisi od klizanja**, i imaginarni (reaktivni) deo $X_{\gamma s} + \sigma X'_{\gamma r}$, koji je **konstantan** (reaktanse su po pretpostavci zadatka konstantne, a frekvencija je nazivna). Upravo ta podela — jedan deo zavisi od $s$, drugi ne — omogućava ceo dalji račun.

### 3. Prevalno klizanje: gde je moment najveći i zašto

Moment motora je snaga obrtnog polja podeljena sinhronom brzinom, $M = P_{\mathrm{ob}}/\Omega_s$, a snaga obrtnog polja je snaga na "otporniku" $\sigma R'_r/s$ kroz koji teče $I'_r$. Uz oznaku $X = X_{\gamma s} + \sigma X'_{\gamma r}$ (ukupna konstantna reaktansa) i uz $I'_r = U_{\mathrm{sfn}}\big/\sqrt{(\sigma R'_r/s)^2 + X^2}$ (moduo izraza iz mini-lekcije 2):

$$M \propto {I'}_r^2\cdot\frac{\sigma R'_r}{s} = U_{\mathrm{sfn}}^2\cdot\frac{\dfrac{\sigma R'_r}{s}}{\left(\dfrac{\sigma R'_r}{s}\right)^2 + X^2}$$

Uvedimo skraćenicu $a = \sigma R'_r/s$ (aktivni deo impedanse; kad se menja klizanje, menja se samo $a$). Podelimo brojilac i imenilac sa $a$:

$$M \propto \frac{a}{a^2+X^2} = \frac{1}{a + \dfrac{X^2}{a}}$$

Moment je najveći kada je imenilac $a + X^2/a$ najmanji. Za pozitivne brojeve važi nejednakost aritmetičke i geometrijske sredine: $u + v \ge 2\sqrt{u v}$, sa jednakošću tačno kada je $u = v$. Uz $u = a$ i $v = X^2/a$ dobijamo $a + X^2/a \ge 2\sqrt{a\cdot X^2/a} = 2X$, sa minimumom kada je $a = X^2/a$, tj. $a = X$. Dakle, moment je maksimalan kada je **aktivni deo impedanse jednak reaktivnom**:

$$\frac{\sigma R'_r}{s_{\mathrm{pr}}} = X_{\gamma s} + \sigma X'_{\gamma r} \quad\Longrightarrow\quad \boxed{\ s_{\mathrm{pr}} = \frac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}}\ }$$

To klizanje zovemo **prevalno klizanje**. Zapamti fizičku sliku: pri malim klizanjima otpornički član $\sigma R'_r/s$ je ogroman i guši struju (mali moment); pri velikim klizanjima struja jeste velika, ali je gotovo čisto reaktivna (loš "faktor snage" rotorskog kola), pa opet mali moment; negde između — tačno tamo gde su aktivni i reaktivni deo jednaki — je maksimum.

### 4. Klosova jednačina

Iz istog izraza $M \propto 1/(a + X^2/a)$ sledi i čuvena **Klosova jednačina**. Ubacimo $a = \sigma R'_r/s$ i iskoristimo definiciju $s_{\mathrm{pr}} = \sigma R'_r/X$, iz koje je $\sigma R'_r = s_{\mathrm{pr}}\cdot X$, pa je $a = X\cdot s_{\mathrm{pr}}/s$:

$$a + \frac{X^2}{a} = X\cdot\frac{s_{\mathrm{pr}}}{s} + X\cdot\frac{s}{s_{\mathrm{pr}}} = X\cdot\left(\frac{s}{s_{\mathrm{pr}}} + \frac{s_{\mathrm{pr}}}{s}\right)$$

U prevalnoj tački ($s = s_{\mathrm{pr}}$) zagrada iznosi $1+1 = 2$, pa je imenilac $2X$. Odnos momenta pri proizvoljnom klizanju i prevalnog momenta je zato:

$$\frac{M}{M_{\mathrm{pr}}} = \frac{2X}{X\left(\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}\right)} = \frac{2}{\dfrac{s}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s}}$$

Ovo je Klosova jednačina (u obliku koji važi kada je $R_s$ zanemaren). Njena ogromna praktična vrednost: **cela momentna karakteristika zavisi samo od dva broja** — $M_{\mathrm{pr}}$ i $s_{\mathrm{pr}}$ — a svi ostali parametri motora ($U$, $R'_r$, reaktanse, $\sigma$…) su se skratili. Zato u ovom zadatku uopšte i možemo da rešimo sve tražene veličine bez ijednog oma ili henrija.

### 5. Kompleksni brojevi: moduo količnika

U rešenju delimo dva kompleksna izraza i tražimo odnos **efektivnih vrednosti** struja. Efektivna vrednost odgovara modulu (dužini) fazora. Za kompleksan broj $z = x + j\,y$ moduo je $|z| = \sqrt{x^2 + y^2}$ (Pitagorina teorema u kompleksnoj ravni). Za količnik važi $\left| z_1/z_2 \right| = |z_1|/|z_2|$ — moduo količnika je količnik modula. Konkretno će nam trebati:

$$\left|\frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j\right| = \sqrt{\left(\frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^2 + 1}, \qquad |1 + j| = \sqrt{1^2+1^2} = \sqrt{2}$$

Česta greška je "sabrati" realni i imaginarni deo umesto koreniti zbir kvadrata — vidi sekciju o greškama.

## Rešenje, korak po korak

### Korak 1: Odnos gubitaka pretvaramo u odnos rotorskih struja

**Zašto ovaj korak:** Jedini podatak o opterećenju je odnos gubitaka ($9$). Da bismo ga povezali sa klizanjem, prvo ga moramo pretvoriti u odnos struja, jer struja je ta koja u ekvivalentnoj šemi zavisi od klizanja.

Prema mini-lekciji 1, gubici usled opterećenja su (zbog $R_s \approx 0$ i zanemarenih mehaničkih gubitaka) samo gubici u bakru rotora:

$$P_{\mathrm{Cu}} = q_r \cdot I_r^2 \cdot R_r$$

Uslov zadatka glasi:

$$P_{\mathrm{Cu,pr}} = 9\cdot P_{\mathrm{Cu,n}}$$

gde indeks "pr" označava prevalnu, a "n" nazivnu radnu tačku. Raspišimo obe strane preko struja:

$$q_r \cdot I_{r,\mathrm{pr}}^2 \cdot R_r = 9\cdot q_r \cdot I_{r\mathrm{n}}^2 \cdot R_r$$

Broj faza $q_r$ i otpor $R_r$ su isti u obe tačke (otpor je po pretpostavci zadatka konstantan), pa se skraćuju:

$$I_{r,\mathrm{pr}}^2 = 9\cdot I_{r\mathrm{n}}^2 \quad\Longrightarrow\quad \frac{I_{r,\mathrm{pr}}}{I_{r\mathrm{n}}} = \sqrt{9} = 3$$

$$\boxed{\ I_{r,\mathrm{pr}} = 3\cdot I_{r\mathrm{n}}\ }$$

**Šta smo dobili:** Struja rotora u prevalnoj tački je 3 puta (ne 9 puta!) veća od nazivne. To je realan red veličine: motori u prevalnoj tački zaista vuku struje reda 2–4 nazivne.

### Korak 2: Rotorska struja u obe radne tačke iz ekvivalentne šeme

**Zašto ovaj korak:** Odnos struja iz Koraka 1 sam po sebi još ne govori ništa o klizanju. Vezu struja–klizanje daje ekvivalentna šema, pa struju zapisujemo u opštem obliku za obe tačke.

Prema mini-lekciji 2, rotorska struja (svedena na stator, fazorski), pri nazivnom klizanju $s_{\mathrm{n}}$:

$$\underline{I}'_{r\mathrm{n}} = \frac{\underline{U}_{\mathrm{sfn}}}{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{n}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

a pri prevalnom klizanju $s_{\mathrm{pr}}$:

$$\underline{I}'_{r,\mathrm{pr}} = \frac{\underline{U}_{\mathrm{sfn}}}{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{pr}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

Napon $\underline{U}_{\mathrm{sfn}}$ je u obe jednačine **isti**, jer zadatak kaže da motor u obe tačke radi pri nazivnom naponu i frekvenciji. Isti su i svi parametri ($\sigma$, $R'_r$, reaktanse) — jedino se klizanje razlikuje.

**Šta smo dobili:** Dve jednačine u kojima je jedina razlika broj u imeniocu ispod $R'_r$. To je idealna situacija za deljenje — sve zajedničko će se skratiti.

### Korak 3: Količnik struja i njegovo sređivanje do oblika sa $s_{\mathrm{pr}}/s_{\mathrm{n}}$

**Zašto ovaj korak:** Ne znamo ni $U_{\mathrm{sfn}}$ (fazno), ni $\sigma$, ni $R'_r$, ni reaktanse — ali nam i ne trebaju: u količniku dve struje sve te veličine se krate, a ostaje čista veza između klizanja.

Podelimo drugu jednačinu prvom (napon $\underline{U}_{\mathrm{sfn}}$ se skrati, a razlomci se "izvrnu" — imenilac prve struje dođe u brojilac):

$$\frac{\underline{I}'_{r,\mathrm{pr}}}{\underline{I}'_{r\mathrm{n}}} = \frac{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{n}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}{\sigma\cdot\dfrac{R'_r}{s_{\mathrm{pr}}} + j\cdot\left(X_{\gamma s} + \sigma\cdot X'_{\gamma r}\right)}$$

Obrati pažnju: u **brojiocu** stoji $s_{\mathrm{n}}$ (jer je to imenilac struje $\underline{I}'_{r\mathrm{n}}$ kojom delimo), a u **imeniocu** $s_{\mathrm{pr}}$.

Sada i brojilac i imenilac podelimo konstantom $X_{\gamma s} + \sigma\cdot X'_{\gamma r}$ (vrednost razlomka se time ne menja):

$$\frac{\underline{I}'_{r,\mathrm{pr}}}{\underline{I}'_{r\mathrm{n}}} = \frac{\dfrac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}}\cdot\dfrac{1}{s_{\mathrm{n}}} + j}{\dfrac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}}\cdot\dfrac{1}{s_{\mathrm{pr}}} + j}$$

U oba razlomka se pojavila ista grupa parametara — a nju smo u mini-lekciji 3 već prepoznali kao **prevalno klizanje**:

$$\frac{\sigma\cdot R'_r}{X_{\gamma s} + \sigma\cdot X'_{\gamma r}} = s_{\mathrm{pr}}$$

Zamenimo:

$$\frac{\underline{I}'_{r,\mathrm{pr}}}{\underline{I}'_{r\mathrm{n}}} = \frac{\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j}{\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{pr}}} + j} = \frac{\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j}{1 + j}$$

**Šta smo dobili:** Svi nepoznati parametri motora su nestali. Odnos struja zavisi **samo** od odnosa klizanja $s_{\mathrm{pr}}/s_{\mathrm{n}}$ — upravo ono što nam treba, jer odnos struja već znamo (iznosi 3), a $s_{\mathrm{n}}$ je zadato.

### Korak 4: Prelazak na efektivne vrednosti i rešavanje po $s_{\mathrm{pr}}$

**Zašto ovaj korak:** Gubici (pa time i naš odnos 3) odnose se na **efektivne vrednosti** struja, a u Koraku 3 imamo odnos fazora (kompleksnih brojeva). Zato prelazimo na module.

Prema mini-lekciji 5, moduo količnika je količnik modula:

$$\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}} = \frac{\left|\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} + j\right|}{\left|1 + j\right|} = \frac{\sqrt{\left(\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^2 + 1}}{\sqrt{2}}$$

Ovaj odnos je, iz Koraka 1, jednak 3. Rešimo jednačinu po $s_{\mathrm{pr}}$, korak po korak. Prvo je zapišimo u opštem obliku (sa oznakom $I'_{r,\mathrm{pr}}/I'_{r\mathrm{n}}$ za odnos struja) i kvadrirajmo obe strane da se oslobodimo korena:

$$\left(\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}}\right)^2 = \frac{\left(\dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^2 + 1}{2}$$

Pomnožimo obe strane sa 2:

$$2\cdot\left(\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}}\right)^2 = \left(\frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^2 + 1$$

Prebacimo jedinicu na levu stranu:

$$\left(\frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}\right)^2 = 2\cdot\left(\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}}\right)^2 - 1$$

Korenujemo (obe strane su pozitivne, pa uzimamo pozitivan koren — klizanje je pozitivno) i pomnožimo sa $s_{\mathrm{n}}$:

$$s_{\mathrm{pr}} = s_{\mathrm{n}}\cdot\sqrt{2\cdot\left(\frac{I'_{r,\mathrm{pr}}}{I'_{r\mathrm{n}}}\right)^2 - 1}$$

Uvrstimo brojeve: $I'_{r,\mathrm{pr}}/I'_{r\mathrm{n}} = 3$ i $s_{\mathrm{n}} = 0{,}028$:

$$s_{\mathrm{pr}} = 0{,}028\cdot\sqrt{2\cdot 3^2 - 1} = 0{,}028\cdot\sqrt{18 - 1} = 0{,}028\cdot\sqrt{17} = 0{,}028\cdot 4{,}123$$

$$\boxed{\ s_{\mathrm{pr}} = 0{,}115\ }$$

**Šta smo dobili:** Prevalno klizanje je $11{,}5\ \%$, tj. oko $4{,}1$ puta veće od nazivnog. To je tipično za kavezne motore: nazivna tačka leži duboko u stabilnom delu karakteristike, daleko levo od prevala, pa motor podnosi znatna preopterećenja pre nego što se "prevali".

### Korak 5 (deo b): Klosova jednačina u nazivnoj tački → prevalni moment

**Zašto ovaj korak:** Sada znamo oba karakteristična klizanja, $s_{\mathrm{n}}$ i $s_{\mathrm{pr}}$. Klosova jednačina (mini-lekcija 4) povezuje moment i klizanje koristeći baš ta dva broja — primenimo je u nazivnoj tački, gde je $s = s_{\mathrm{n}}$ i $M = M_{\mathrm{n}}$.

$$\frac{M_{\mathrm{n}}}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{s_{\mathrm{n}}}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}}$$

Nama treba obrnut odnos, $M_{\mathrm{pr}}/M_{\mathrm{n}}$, pa razlomak "izvrnemo" (recipročna vrednost obe strane):

$$\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}} = \frac{\dfrac{s_{\mathrm{n}}}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{s_{\mathrm{n}}}}{2}$$

Izračunajmo oba sabirka posebno, pa uvrstimo:

$$\frac{s_{\mathrm{n}}}{s_{\mathrm{pr}}} = \frac{0{,}028}{0{,}115} = 0{,}2435, \qquad \frac{s_{\mathrm{pr}}}{s_{\mathrm{n}}} = \frac{0{,}115}{0{,}028} = 4{,}1071$$

$$\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}} = \frac{0{,}2435 + 4{,}1071}{2} = \frac{4{,}3506}{2} = 2{,}18$$

$$\boxed{\ M_{\mathrm{pr}} = 2{,}18\cdot M_{\mathrm{n}}\ }$$

**Šta smo dobili:** Motor može da razvije najviše $2{,}18$ puta veći moment od nazivnog. To je zdrava, tipična preopteretljivost kaveznog motora (standardi obično traže bar $1{,}6$; uobičajene vrednosti su $1{,}8$–$3$).

### Korak 6 (deo c): Klosova jednačina u polasku → polazni prema prevalnom momentu

**Zašto ovaj korak:** Polazak motora je trenutak kada rotor stoji, dakle klizanje je $s = 1$ (rotor "kasni" za poljem punom sinhronom brzinom). Ista Klosova jednačina, samo sa $s = 1$, daje polazni moment — najpre u odnosu na prevalni.

$$\frac{M_{\mathrm{k}}}{M_{\mathrm{pr}}} = \frac{2}{\dfrac{1}{s_{\mathrm{pr}}} + \dfrac{s_{\mathrm{pr}}}{1}}$$

- $M_{\mathrm{k}}$ — polazni moment (indeks "k" od "kratak spoj": polazak je za motor režim sličan kratkom spoju transformatora — rotor stoji, struje su najveće).

Uvrstimo $s_{\mathrm{pr}} = 0{,}115$, računajući imenilac deo po deo:

$$\frac{1}{s_{\mathrm{pr}}} = \frac{1}{0{,}115} = 8{,}6957, \qquad \frac{1}{s_{\mathrm{pr}}} + s_{\mathrm{pr}} = 8{,}6957 + 0{,}115 = 8{,}8107$$

$$\frac{M_{\mathrm{k}}}{M_{\mathrm{pr}}} = \frac{2}{8{,}8107} = 0{,}227$$

**Šta smo dobili:** Polazni moment je svega $22{,}7\ \%$ prevalnog. Logično: pri $s = 1$ radna tačka je daleko desno od prevala, duboko u oblasti gde je rotorska struja ogromna ali gotovo čisto reaktivna, pa slabo doprinosi momentu.

### Korak 7 (deo c, nastavak): Polazni moment u odnosu na nazivni

**Zašto ovaj korak:** Zadatak traži momente u odnosu na **nazivni** moment, a Korak 6 nam je dao odnos prema prevalnom. Povezujemo ih ulančavanjem (množenjem) odnosa — $M_{\mathrm{pr}}$ se skrati:

$$\frac{M_{\mathrm{k}}}{M_{\mathrm{n}}} = \frac{M_{\mathrm{k}}}{M_{\mathrm{pr}}}\cdot\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}} = 0{,}227\cdot 2{,}18 = 0{,}49$$

$$\boxed{\ M_{\mathrm{k}} = 0{,}49\cdot M_{\mathrm{n}}\ }$$

**Šta smo dobili:** Pri direktnom uključenju na mrežu ovaj motor razvija samo oko polovine nazivnog momenta. Praktična posledica: motor bi bez problema zaleteo ventilator ili pumpu (kojima moment raste sa kvadratom brzine, pa je u polasku mali), ali **ne bi mogao** da pokrene teret koji već u startu traži pun nazivni moment (npr. punu transportnu traku).

## Česte greške i zamke

1. **Uvrstiti 9 umesto 3 u formulu za $s_{\mathrm{pr}}$.** Gubici su 9 puta veći, ali gubici rastu sa **kvadratom** struje, pa je struja $\sqrt{9} = 3$ puta veća. U formulu $s_{\mathrm{pr}} = s_{\mathrm{n}}\sqrt{2\,(I_{r,\mathrm{pr}}/I_{r\mathrm{n}})^2 - 1}$ ide odnos **struja** (3), ne odnos gubitaka (9). Ko uvrsti 9 dobija $s_{\mathrm{pr}} = 0{,}028\cdot\sqrt{161} = 0{,}355$ — više nego trostruko pogrešno.

2. **Sabiranje umesto Pitagore kod modula.** $\left|\,s_{\mathrm{pr}}/s_{\mathrm{n}} + j\,\right|$ nije $s_{\mathrm{pr}}/s_{\mathrm{n}} + 1$, nego $\sqrt{(s_{\mathrm{pr}}/s_{\mathrm{n}})^2 + 1}$. Realni i imaginarni deo se slažu pod pravim uglom, pa se "sabiraju" preko kvadrata i korena, ne direktno.

3. **Izvrnuta Klosova jednačina.** Klosova jednačina daje $M/M_{\mathrm{pr}}$, tj. moment u odnosu na **prevalni**. Zadatak traži odnose prema **nazivnom** momentu — mora se pažljivo izvrnuti razlomak (Korak 5) i ulančati odnose (Korak 7). Odgovor "$M_{\mathrm{k}} = 0{,}227\,M_{\mathrm{n}}$" je pogrešan: $0{,}227$ je odnos prema prevalnom, a prema nazivnom je $0{,}49$.

4. **Traženje gde da se upotrebe 18,4 kW, 230 V i 60 Hz.** Ne treba ih uvrštavati nigde — svi traženi rezultati su relativni (klizanja i odnosi momenata), pa se apsolutni podaci motora krate. Oni bi zatrebali tek ako bi se tražio moment u $\mathrm{N\,m}$ (tada bi iz $P_{\mathrm{n}}$, $f_{\mathrm{n}}$ i broja polova sledio $M_{\mathrm{n}}$). Podatak da su napon i frekvencija **nazivni i isti u obe tačke** jeste bitan — zbog njega se $U_{\mathrm{sfn}}$ skratio u Koraku 3 — ali brojčane vrednosti ne ulaze u račun.

5. **Zaboraviti pod kojim pretpostavkama sve ovo važi.** Oblik Klosove jednačine bez dodatnih članova važi samo uz $R_s \approx 0$; formula $s_{\mathrm{pr}} = \sigma R'_r/(X_{\gamma s}+\sigma X'_{\gamma r})$ i ceo račun važe samo ako su $R_r$ i reaktanse konstantni. Kod stvarnih kaveznih motora potiskivanje struje (skin-efekat) u polasku povećava $R_r$, pa je stvarni polazni moment po pravilu veći od ovako izračunatog — vidi "Proveru smisla".

## Rezime rezultata

| Tražena veličina | Oznaka | Rezultat |
|---|---|---|
| a) Klizanje kod prevalnog momenta | $s_{\mathrm{pr}}$ | $0{,}115$ |
| b) Prevalni moment (relativno) | $M_{\mathrm{pr}}/M_{\mathrm{n}}$ | $2{,}18$, tj. $M_{\mathrm{pr}} = 2{,}18\cdot M_{\mathrm{n}}$ |
| c) Polazni prema prevalnom momentu (međurezultat) | $M_{\mathrm{k}}/M_{\mathrm{pr}}$ | $0{,}227$ |
| c) Polazni moment (relativno) | $M_{\mathrm{k}}/M_{\mathrm{n}}$ | $0{,}49$, tj. $M_{\mathrm{k}} = 0{,}49\cdot M_{\mathrm{n}}$ |

## Provera smisla

**1. Nezavisna provera prevalnog momenta preko bilansa snaga.** Iz mini-lekcije 1 znamo $P_{\mathrm{Cu,r}} = s\cdot P_{\mathrm{ob}}$ i $M = P_{\mathrm{ob}}/\Omega_s$, pa je $M = P_{\mathrm{Cu,r}}/(s\,\Omega_s)$ — moment je srazmeran gubicima u rotoru podeljenim klizanjem. Odnos momenata u dve tačke je onda:

$$\frac{M_{\mathrm{pr}}}{M_{\mathrm{n}}} = \frac{P_{\mathrm{Cu,pr}}}{P_{\mathrm{Cu,n}}}\cdot\frac{s_{\mathrm{n}}}{s_{\mathrm{pr}}} = 9\cdot\frac{0{,}028}{0{,}1154} = 9\cdot 0{,}2425 = 2{,}18$$

Potpuno drugačiji put (bilans snaga umesto Klosove jednačine) daje isti rezultat $2{,}18$ — račun je konzistentan.

**2. Granični slučaj formule za $s_{\mathrm{pr}}$.** Ako bi gubici u obe tačke bili jednaki (odnos struja 1), formula daje $s_{\mathrm{pr}} = s_{\mathrm{n}}\sqrt{2\cdot 1 - 1} = s_{\mathrm{n}}$ — obe tačke se poklapaju, kako i mora biti. Ako se uvrsti $s = s_{\mathrm{pr}}$ u Klosovu jednačinu, dobija se $M/M_{\mathrm{pr}} = 2/(1+1) = 1$ — u prevalnoj tački moment je jednak prevalnom. Obe formule prolaze test graničnih slučajeva.

**3. Dimenziona i "zdravorazumska" provera.** Sve tražene veličine su bezdimenzioni odnosi, kao što i treba (klizanje je odnos brzina, momenti su relativni). Vrednosti su tipične za kavezne motore: $s_{\mathrm{pr}}/s_{\mathrm{n}} \approx 4$, preopteretljivost $2{,}18$ (uobičajeno $1{,}8$–$3$), polazni moment ispod nazivnog. Jedina "neintuitivna" vrednost je $M_{\mathrm{k}} = 0{,}49\,M_{\mathrm{n}}$ — stvarni kavezni motori pri polasku obično daju $1$–$2{,}5\,M_{\mathrm{n}}$, ali upravo zahvaljujući potiskivanju struje u dubokim/dvostrukim žlebovima kaveza, koje povećava $R_r$ pri $s = 1$. Naš zadatak izričito pretpostavlja **konstantan** otpor rotora, pa je niži polazni moment očekivana posledica te idealizacije, a ne greška u računu.
