# Zadatak 21 — Šta se dešava sa sinhronim generatorom kad mu prekinemo pobudu?

## Postavka

Dat je sinhroni generator sa istaknutim polovima, o kome znamo sledeće nazivne podatke:

- nazivna prividna snaga $S_{\mathrm{n}} = 20\ \mathrm{MVA}$,
- nazivni napon $U_{\mathrm{n}} = 10\ \mathrm{kV}$,
- nazivni faktor snage $\cos\varphi_{\mathrm{n}} = 0{,}9$,
- relativna podužna sinhrona reaktansa $x_d = 100\% = 1\ \mathrm{r.j.}$,
- relativna poprečna sinhrona reaktansa $x_q = 50\% = 0{,}5\ \mathrm{r.j.}$

Generator je priključen na krutu mrežu. Odrediti šta će se desiti ako mu **prekinemo pobudu** u sledeća dva radna režima:

**a)** opterećenje $10\ \mathrm{MVA}$ pri faktoru snage $0{,}7$ i naponu mreže $10\ \mathrm{kV}$;

**b)** opterećenje $8\ \mathrm{MVA}$ pri faktoru snage $0{,}9$ i naponu mreže $8\ \mathrm{kV}$.

*Napomena iz zbirke:* odgovor na pitanje „šta će se desiti" treba da uključi: da li je takav režim moguć, tj. kontinualno održiv; koliku aktivnu i reaktivnu snagu generator odaje/uzima iz mreže; i kolika je struja generatora.

> **Prevod na običan jezik:** Sinhroni generator normalno radi zahvaljujući jednosmernoj struji u rotorskom (pobudnom) namotaju — ona pravi magnetno polje rotora koje se „zakači" za obrtno polje statora i tako prenosi snagu. Pitanje glasi: ako ta pobudna struja iznenada nestane (prekid pobudnog kola — realan kvar u elektrani!), da li generator ispada iz sinhronizma i „pobegne", ili može da nastavi da radi zahvaljujući samoj **nesimetriji gvožđa rotora** (istaknuti polovi)? I ako može — kolike su mu tada snage i struja, tj. da li je preopterećen? Treba to proveriti za dva različita početna režima rada.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna prividna snaga | $S_{\mathrm{n}}$ | $20\ \mathrm{MVA}$ | Najveća „ukupna" snaga (kombinacija aktivne i reaktivne) za koju je mašina projektovana; ujedno je uzimamo za **baznu snagu** u relativnim jedinicama. |
| Nazivni napon | $U_{\mathrm{n}}$ | $10\ \mathrm{kV}$ | Linijski napon na priključcima za koji je mašina projektovana; ujedno **bazni napon**. |
| Nazivni faktor snage | $\cos\varphi_{\mathrm{n}}$ | $0{,}9$ | Odnos aktivne i prividne snage u nazivnom režimu (ovde nam služi samo kao nazivni podatak — u računu koristimo faktore snage iz režima a) i b)). |
| Podužna sinhrona reaktansa | $x_d$ | $1\ \mathrm{r.j.}$ ($100\%$) | Reaktansa koju mašina pokazuje struji čije polje deluje **duž ose polova** rotora (d-osa); tu je magnetni put kroz gvožđe pola, pa je reaktansa velika. |
| Poprečna sinhrona reaktansa | $x_q$ | $0{,}5\ \mathrm{r.j.}$ ($50\%$) | Reaktansa koju mašina pokazuje struji čije polje deluje **između polova** (q-osa); tu je magnetni put većim delom kroz vazduh, pa je reaktansa mala. |
| Režim a): opterećenje | $S$ | $10\ \mathrm{MVA}$ | Prividna snaga koju generator daje mreži pre prekida pobude. |
| Režim a): faktor snage | $\cos\varphi$ | $0{,}7$ | Udeo aktivne snage u opterećenju u režimu a). |
| Režim a): napon mreže | $U$ | $10\ \mathrm{kV}$ | Napon krute mreže u režimu a) — jednak nazivnom. |
| Režim b): opterećenje | $S$ | $8\ \mathrm{MVA}$ | Prividna snaga u režimu b). |
| Režim b): faktor snage | $\cos\varphi$ | $0{,}9$ | Udeo aktivne snage u opterećenju u režimu b). |
| Režim b): napon mreže | $U$ | $8\ \mathrm{kV}$ | Napon mreže u režimu b) — **snižen** na 80% nazivnog. |

(Oznake $S$, $\cos\varphi$, $U$ se ponavljaju za oba režima — iz konteksta koraka biće jasno koje vrednosti uvrštavamo.)

Oznaka $\mathrm{r.j.}$ znači „relativne jedinice" (objašnjeno u prvoj mini-lekciji).

## Šta se traži i zašto

Za svaki od dva režima traže se **četiri odgovora**:

1. **Da li je rad održiv posle prekida pobude?** — Inženjera ovo zanima jer je gubitak pobude jedan od tipičnih kvarova sinhronog generatora; zaštita elektrane (tzv. zaštita od gubitka pobude) mora da „zna" da li mašina u takvom stanju može da preživi ili odmah ispada iz sinhronizma (počinje nekontrolisano da klizi u odnosu na mrežu, uz udarne struje i momente — to je opasno i mašina se mora isključiti).
2. **Aktivna snaga** koju generator odaje — da vidimo koliko mehaničke snage turbine mašina i dalje može da pretvori u električnu.
3. **Reaktivna snaga** koju generator razmenjuje sa mrežom — videćemo da bez pobude mašina mora da se **magneti iz mreže**, tj. postaje veliki potrošač reaktivne snage.
4. **Struja generatora** — da proverimo da li je namotaj statora preopterećen (struja veća od nazivne znači pregrevanje ako režim potraje).

**Plan rešavanja** (isti za oba režima):

1. Izračunamo aktivnu snagu $P = S\cos\varphi$ i prebacimo je u relativne jedinice: $p = P/S_{\mathrm{n}}$.
2. Napišemo ugaonu karakteristiku aktivne snage mašine sa istaknutim polovima i u nju ubacimo činjenicu da je pobuda prekinuta ($e_0 = 0$) — ostaje samo tzv. **reluktantna** komponenta snage.
3. Nađemo maksimum te karakteristike $p_{\mathrm{max}}$ pri datom naponu mreže i uporedimo ga sa $p$: ako je $p \le p_{\mathrm{max}}$, mašina ostaje u sinhronizmu; ako je $p > p_{\mathrm{max}}$, ispada.
4. Ako ostaje u sinhronizmu — iz karakteristike izračunamo ugao opterećenja $\delta$.
5. Pomoću $\delta$ izračunamo reaktivnu snagu $q$ koju mašina uzima iz mreže.
6. Iz $p$ i $q$ izračunamo prividnu snagu $s$, a iz nje struju $i$, pa zaključimo da li je mašina preopterećena.

## Potrebna teorija — mini-lekcije

### Mini-lekcija 1: Relativne jedinice (r.j.)

**Definicija.** Umesto da radimo sa voltima, amperima i megavatima, svaku veličinu podelimo njenom **baznom vrednošću** i dobijemo bezdimenzioni broj — relativnu jedinicu. Za bazne vrednosti se kod mašina uzimaju nazivne: bazna snaga $S_{\mathrm{b}} = S_{\mathrm{n}} = 20\ \mathrm{MVA}$ (i to je baza i za $P$ i za $Q$ i za $S$!), bazni napon $U_{\mathrm{b}} = U_{\mathrm{n}} = 10\ \mathrm{kV}$, a bazna struja sledi iz njih. Dakle:

$$p = \frac{P}{S_{\mathrm{b}}}, \qquad q = \frac{Q}{S_{\mathrm{b}}}, \qquad s = \frac{S}{S_{\mathrm{b}}}, \qquad u = \frac{U}{U_{\mathrm{b}}}, \qquad i = \frac{I}{I_{\mathrm{b}}}.$$

Malim slovima pišemo relativne veličine, velikim stvarne.

**Zašto je to zgodno?** Prvo, brojevi postaju „pitomi": $u = 1$ znači „napon je tačno nazivni", $i = 1{,}2$ znači „struja je 20% iznad nazivne" — odmah vidimo koliko je mašina opterećena. Drugo, reaktanse su nam ionako zadate u procentima ($x_d = 100\%$, $x_q = 50\%$), što su upravo relativne jedinice: $x_d = 1$, $x_q = 0{,}5$.

**Zašto iz formula za snagu nestaje koeficijent 3?** Trofazna snaga se sa faznim veličinama piše $S = 3\, U_f I_f$ ($U_f$, $I_f$ — fazni napon i struja). Ako za baznu snagu izaberemo baš trofaznu nazivnu snagu, $S_{\mathrm{b}} = 3\, U_{f\mathrm{b}} I_{f\mathrm{b}}$, onda pri deljenju trofazne formule baznom snagom trojka iz brojioca i trojka iz imenioca **skrate jedna drugu**. Zato sve formule za snagu u relativnom domenu izgledaju kao „jednofazne", bez trojke. Slično važi i za prividnu snagu:

$$s = \frac{S}{S_{\mathrm{b}}} = \frac{3\,U_f I_f}{3\,U_{f\mathrm{b}} I_{f\mathrm{b}}} = \frac{U_f}{U_{f\mathrm{b}}}\cdot\frac{I_f}{I_{f\mathrm{b}}} = u \cdot i.$$

Ovu malu formulu $s = u\,i$ koristićemo na kraju da iz snage dobijemo struju.

### Mini-lekcija 2: Mašina sa istaknutim polovima — zašto postoje dve reaktanse $x_d$ i $x_q$

Kod turbogeneratora rotor je gladak valjak, pa je magnetni otpor (reluktansa) vazdušnog zazora isti u svim pravcima — dovoljna je jedna sinhrona reaktansa. Kod **hidrogeneratora i drugih mašina sa istaknutim polovima** rotor liči na točak sa isturenim „pečurkama" (polovima). Zbog toga:

- duž ose polova (**podužna** ili **d-osa**) magnetni fluks ide kroz gvožđe pola — mali magnetni otpor, **velika induktivnost**, dakle velika reaktansa $x_d$;
- između polova (**poprečna** ili **q-osa**) fluks mora kroz široki vazdušni međuprostor — veliki magnetni otpor, **mala induktivnost**, dakle mala reaktansa $x_q$.

Zato je uvek $x_d > x_q$; kod nas $x_d = 1$, $x_q = 0{,}5$, tj. poprečno mašina „propušta" fluks upola teže. Analiza takve mašine radi se tako što se struja statora razloži na komponentu $i_d$ (deluje po d-osi, „vidi" $x_d$) i komponentu $i_q$ (deluje po q-osi, „vidi" $x_q$) — to je čuvena **dvoosovinska (dq) teorija**.

### Mini-lekcija 3: Ugao opterećenja $\delta$

Ugao opterećenja $\delta$ je ugao između fazora elektromotorne sile $E_0$ (koja je vezana za položaj rotora — leži u q-osi rotora) i fazora napona mreže $U$. Fizički: to je **ugaono zaostajanje/prednjačenje rotora u odnosu na obrtno polje mreže**. Kad generator gura aktivnu snagu u mrežu, rotor „vuče napred" i $\delta > 0$.

Važno za ovaj zadatak: čak i kad pobude nema ($E_0 = 0$, pa fazor $E_0$ „nestane"), rotor i dalje fizički postoji i ima svoje d- i q-ose, pa je $\delta$ i dalje dobro definisan — kao ugao između **q-ose rotora** i fazora napona mreže.

### Mini-lekcija 4: Ugaona karakteristika aktivne snage mašine sa istaknutim polovima

Za sinhronu mašinu sa istaknutim polovima, priključenu na mrežu faznog napona $U_f$, aktivna snaga u funkciji ugla opterećenja glasi (zanemaren otpor statora):

$$P(\delta) = 3\cdot\frac{E_{0f}\cdot U_f}{X_d}\cdot\sin\delta + \frac{3}{2}\cdot U_f^2\cdot\left(\frac{1}{X_q} - \frac{1}{X_d}\right)\cdot\sin(2\delta)$$

gde su: $E_{0f}$ — fazna elektromotorna sila indukovana pobudnim fluksom (proporcionalna pobudnoj struji), $U_f$ — fazni napon mreže, $X_d$ i $X_q$ — podužna i poprečna sinhrona reaktansa u omima, $\delta$ — ugao opterećenja.

**Odakle ova formula?** Struja statora se razloži na $I_d$ i $I_q$ (mini-lekcija 2). Iz naponskih jednačina mašine u ustaljenom stanju (bez otpora statora) slede komponente struje $I_d = (E_{0f} - U_f\cos\delta)/X_d$ i $I_q = U_f\sin\delta/X_q$, a kad se one uvrste u izraz za trofaznu aktivnu snagu $P = 3(U_{fd} I_d + U_{fq} I_q)$, gde su $U_{fd} = U_f\sin\delta$ i $U_{fq} = U_f\cos\delta$ projekcije napona na dve ose, posle sređivanja (uz trigonometrijski identitet $2\sin\delta\cos\delta = \sin 2\delta$) dobija se upravo gornji izraz.

Formula ima **dve komponente**:

1. **Sinhrona (osnovna) komponenta** $\;3\,\dfrac{E_{0f} U_f}{X_d}\sin\delta$ — posledica sprege pobudnog polja rotora i polja mreže. Nje **nema bez pobude**.
2. **Reluktantna komponenta** $\;\dfrac{3}{2} U_f^2 \left(\dfrac{1}{X_q} - \dfrac{1}{X_d}\right)\sin(2\delta)$ — posledica **magnetne nesimetrije rotora** ($X_d \ne X_q$). Nje nema kod mašine sa glatkim rotorom (tada je $X_d = X_q$ i zagrada je nula), ali kod istaknutih polova postoji **i bez ikakve pobude**, jer zavisi samo od napona mreže i oblika gvožđa.

**Intuicija za reluktantnu komponentu:** gvozdena šipka u magnetnom polju teži da se okrene tako da se poravna sa poljem (put fluksa kroz gvožđe je „lakši"). Rotor sa istaknutim polovima je takva „šipka" u obrtnom polju statora — polje ga vuče da polove drži poravnate sa sobom, i ako rotor pokušamo da zaostane/prednjači za ugao $\delta$, javlja se moment (i snaga) koji zavisi od $\sin(2\delta)$. Dvostruki ugao je tu zato što se šipka poravna sa poljem na svakih pola obrtaja (svejedno je koji kraj šipke gleda „napred") — nesimetrija se ponavlja sa periodom $180^\circ$, a ne $360^\circ$.

U relativnom domenu trojka nestaje (mini-lekcija 1) i karakteristika glasi:

$$p(\delta) = \frac{e_0\cdot u}{x_d}\cdot\sin\delta + \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right)\cdot\sin(2\delta)$$

gde je $e_0 = E_{0f}/U_{f\mathrm{b}}$ relativna elektromotorna sila.

### Mini-lekcija 5: Prekid pobude — ostaje samo reluktantna snaga

Kad se pobudno kolo prekine, pobudna struja padne na nulu, pa nema pobudnog fluksa i nema indukovane elektromotorne sile: $e_0 = 0$. Prva (sinhrona) komponenta snage nestaje i ostaje **samo reluktantna**:

$$p(\delta) = \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right)\cdot\sin(2\delta)$$

Mašina tada radi kao **reluktantni generator**: turbina i dalje gura rotor, a mreža ga preko „poravnavanja gvožđa" pridržava u sinhronizmu — sve dok je snaga turbine manja od maksimuma ove (znatno niže) karakteristike.

**Maksimum karakteristike.** Pošto je $\sin(2\delta)$ najveći (jednak 1) kada je $2\delta = \pi/2$, tj. $\delta = \pi/4 = 45^\circ$, maksimalna reluktantna snaga iznosi:

$$p_{\mathrm{max}} = \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right)$$

Obratite pažnju: $p_{\mathrm{max}}$ zavisi od **kvadrata napona** — ako napon mreže padne na 80%, maksimalna snaga pada na $0{,}8^2 = 0{,}64$, tj. na 64% svoje vrednosti pri nazivnom naponu. To će biti presudno u delu b).

**Kriterijum održivosti.** Ako je opterećenje $p \le p_{\mathrm{max}}$, postoji ugao $\delta$ u stabilnoj oblasti ($0 \le \delta \le 45^\circ$, gde karakteristika raste) u kome se snaga turbine i električna snaga uravnotežuju — mašina ostaje u sinhronizmu. Ako je $p > p_{\mathrm{max}}$, ravnoteža ne postoji ni pri jednom uglu: turbina gura jače nego što magnetna „opruga" može da drži, rotor se ubrzava, ugao raste preko $45^\circ$ gde snaga počinje da **opada** (još manje drži!), i mašina **ispada iz sinhronizma** — rotor proklizava u odnosu na polje mreže, javljaju se udarne struje i njihanje momenta, i zaštita mora da isključi mašinu.

### Mini-lekcija 6: Reaktivna snaga pri prekinutoj pobudi

Bez pobude, magnetno polje u mašini nema ko da napravi osim — mreže. Zato mašina bez pobude obavezno **uzima reaktivnu snagu iz mreže** (magnetizuje se iz mreže), i to mnogo, jer sinhrona mašina ima veliki vazdušni zazor. Izvedimo koliko.

Sa $e_0 = 0$ komponente struje iz mini-lekcije 4 postaju čisto „magnetizacione":

$$I_d = \frac{U_f\cos\delta}{X_d}, \qquad I_q = \frac{U_f\sin\delta}{X_q}$$

(znak biramo tako da $I_d$, $I_q$ označavaju struje koje mašina **uzima** za magnećenje). Svaka od te dve komponente je čisto induktivna struja kroz „svoju" reaktansu — kao dva obična kalema priključena na komponente napona $U_f\cos\delta$ (duž q-ose) i $U_f\sin\delta$ (duž d-ose). Reaktivna snaga jednog kalema je $Q = U^2/X$, pa je ukupna reaktivna snaga koju trofazna mašina troši:

$$Q(\delta) = 3\cdot\left[\frac{(U_f\cos\delta)^2}{X_d} + \frac{(U_f\sin\delta)^2}{X_q}\right] = 3\cdot U_f^2\cdot\left(\frac{\cos^2\delta}{X_d} + \frac{\sin^2\delta}{X_q}\right)$$

(Formalno, isti rezultat daje uvrštavanje $I_d$, $I_q$ u opšti izraz $Q = 3(U_{fq} I_d - U_{fd} I_q)$ uz $e_0=0$ — dobije se $Q$ sa znakom minus, što upravo znači da generator reaktivnu snagu **ne odaje nego uzima**; mi ovde radimo sa njenim iznosom i rečima kažemo smer.)

U relativnom domenu (trojka opet nestaje):

$$q(\delta) = u^2\cdot\left(\frac{\cos^2\delta}{x_d} + \frac{\sin^2\delta}{x_q}\right)$$

**Kontrola smisla formule:** pri $\delta = 0$ (neopterećena mašina) dobijamo $q = u^2/x_d$ — mašina uzima čistu magnetizacionu struju kroz podužnu reaktansu, baš kao prazan hod asinhronog motora. Što je $\delta$ veći, veći deo magnećenja ide kroz „propustljiviju" q-osu (manje $x_q$), pa mašina vuče **još više** reaktivne snage.

### Mini-lekcija 7: Od $p$ i $q$ do struje

Aktivna i reaktivna snaga su dve upravne „stranice" trougla snaga, pa je prividna snaga (u relativnim jedinicama):

$$s = \sqrt{p^2 + q^2}$$

a struja sledi iz relacije $s = u\cdot i$ (mini-lekcija 1):

$$i = \frac{s}{u}$$

Pošto je $i$ izražena u relativnim jedinicama u odnosu na nazivnu struju, $i > 1$ direktno znači: **struja veća od nazivne**, tj. preopterećenje statorskog namotaja.

## Rešenje, korak po korak

### DEO a) — opterećenje 10 MVA, $\cos\varphi = 0{,}7$, napon mreže 10 kV

### Korak 1: Aktivna snaga generatora pre i posle prekida pobude

**Zašto ovaj korak:** Prekid pobude ne menja snagu turbine — turbina i dalje dovodi istu mehaničku snagu, pa generator i posle prekida mora da odaje istu aktivnu snagu (ako ostane u sinhronizmu). Zato prvo izračunamo koliko ta aktivna snaga iznosi.

Aktivna snaga je deo prividne snage određen faktorom snage:

$$P = S\cdot\cos\varphi$$

gde je $S$ prividna snaga opterećenja, a $\cos\varphi$ faktor snage. Uvrštavamo podatke režima a):

$$P = 10\ \mathrm{MVA}\cdot 0{,}7 = 7\ \mathrm{MW}$$

Prebacujemo u relativne jedinice deljenjem baznom snagom (mini-lekcija 1); bazna snaga za aktivnu snagu, koju zbirka označava sa $P_{\mathrm{b}}$, ista je kao i za sve ostale snage: $P_{\mathrm{b}} = S_{\mathrm{b}} = S_{\mathrm{n}} = 20\ \mathrm{MVA}$. Dakle:

$$p = \frac{P}{P_{\mathrm{b}}} = \frac{P}{S_{\mathrm{n}}} = \frac{7}{20} = 0{,}35\ \mathrm{r.j.}$$

**Šta smo dobili:** Generator odaje 35% svoje nazivne snage — umereno opterećenje. Pitanje je da li mašina **bez pobude** uopšte može da iznese i toliko.

### Korak 2: Ugaona karakteristika bez pobude

**Zašto ovaj korak:** Da bismo znali koliku snagu mašina može da prenese bez pobude, treba nam njena ugaona karakteristika u novom stanju ($e_0 = 0$).

Polazimo od pune ugaone karakteristike mašine sa istaknutim polovima u relativnom domenu (mini-lekcija 4):

$$p(\delta) = \frac{e_0\cdot u}{x_d}\cdot\sin\delta + \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right)\cdot\sin(2\delta)$$

Prekid pobude znači $e_0 = 0$, pa prvi sabirak otpada i ostaje samo reluktantna komponenta (mini-lekcija 5):

$$p(\delta) = \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right)\cdot\sin(2\delta)$$

Napon mreže je nazivni, $U = 10\ \mathrm{kV}$, pa je $u = U/U_{\mathrm{b}} = 10/10 = 1$. Uvrštavamo $u = 1$, $x_q = 0{,}5$, $x_d = 1$:

$$p(\delta) = \frac{1}{2}\cdot 1^2\cdot\left(\frac{1}{0{,}5} - \frac{1}{1}\right)\cdot\sin(2\delta) = \frac{1}{2}\cdot(2 - 1)\cdot\sin(2\delta) = 0{,}5\cdot\sin(2\delta)$$

**Šta smo dobili:** Karakteristiku snage mašine bez pobude — čist sinusni talas dvostrukog ugla sa amplitudom 0,5. Mašina bez pobude i dalje ume da prenosi snagu, ali joj je „plafon" znatno niži nego sa pobudom.

### Korak 3: Maksimalna snaga i provera održivosti

**Zašto ovaj korak:** Ovo je ključno pitanje zadatka — da li mašina ostaje u sinhronizmu. Kriterijum (mini-lekcija 5): ostaje ako je opterećenje manje ili jednako maksimumu karakteristike.

Maksimum se dobija kada je $\sin(2\delta) = 1$, tj. za $2\delta = \pi/2$, odnosno ugao opterećenja $\delta = \pi/4 = 45^\circ$:

$$p_{\mathrm{max}} = 0{,}5\cdot 1 = 0{,}5\ \mathrm{r.j.}$$

Poredimo sa opterećenjem iz Koraka 1:

$$p = 0{,}35\ \mathrm{r.j.} < p_{\mathrm{max}} = 0{,}5\ \mathrm{r.j.}$$

**Šta smo dobili:** Opterećenje je manje od maksimalne reluktantne snage, pa **generator ostaje u sinhronizmu** i nastavlja da odaje aktivnu snagu $0{,}35\ \mathrm{r.j.}$ ($7\ \mathrm{MW}$) — sada isključivo zahvaljujući istaknutim polovima. Režim je (barem po pitanju sinhronizma) moguć.

### Korak 4: Ugao opterećenja $\delta$

**Zašto ovaj korak:** Reaktivna snaga (sledeći korak) zavisi od ugla $\delta$, pa prvo moramo da nađemo pri kom uglu mašina radi. Ugao nalazimo iz uslova da karakteristika daje baš snagu $p = 0{,}35$.

$$p = 0{,}5\cdot\sin(2\delta) \;\Rightarrow\; \sin(2\delta) = \frac{p}{0{,}5} = \frac{0{,}35}{0{,}5} = 0{,}7$$

Odavde:

$$2\delta = \arcsin(0{,}7) = 44{,}43^\circ \;\Rightarrow\; \delta = \frac{44{,}43^\circ}{2} = 22{,}21^\circ$$

(Jednačina $\sin(2\delta) = 0{,}7$ ima u opsegu do $90^\circ$ i drugo rešenje, $2\delta = 180^\circ - 44{,}43^\circ$, tj. $\delta = 67{,}79^\circ$ — ali to je tačka na **opadajućem** delu karakteristike, iznad $45^\circ$, koja je nestabilna: mašina se u njoj ne može trajno zadržati. Fizički smisleno, stabilno rešenje je ono manje.)

**Šta smo dobili:** Rotor bez pobude radi na uglu opterećenja $\delta = 22{,}21^\circ$ — udobno ispod granice stabilnosti od $45^\circ$.

### Korak 5: Reaktivna snaga koju generator uzima iz mreže

**Zašto ovaj korak:** Bez pobude mašina mora da se magneti iz mreže (mini-lekcija 6) — treba da izračunamo koliko reaktivne snage to „košta", jer ona diže ukupnu struju.

Ugaona karakteristika reaktivne snage pri prekinutoj pobudi u relativnom domenu (mini-lekcija 6):

$$q(\delta) = u^2\cdot\left(\frac{\cos^2\delta}{x_d} + \frac{\sin^2\delta}{x_q}\right)$$

Uvrštavamo $u = 1$, $x_d = 1$, $x_q = 0{,}5$:

$$q(\delta) = 1^2\cdot\left(\frac{\cos^2\delta}{1} + \frac{\sin^2\delta}{0{,}5}\right) = \cos^2\delta + 2\cdot\sin^2\delta$$

Sredimo pomoću identiteta $\cos^2\delta = 1 - \sin^2\delta$:

$$q(\delta) = \left(1 - \sin^2\delta\right) + 2\cdot\sin^2\delta = 1 + \sin^2\delta$$

Za ugao opterećenja $\delta = 22{,}21^\circ$ iz Koraka 4, uz $\sin(22{,}21^\circ) = 0{,}378$:

$$q = 1 + \sin^2\left(22{,}21^\circ\right) = 1 + 0{,}378^2 = 1 + 0{,}143 = 1{,}143\ \mathrm{r.j.}$$

**Šta smo dobili:** Generator **uzima iz mreže** reaktivnu snagu od čak $1{,}143\ \mathrm{r.j.}$ — više od cele nazivne prividne snage mašine! To je očekivano: sinhrona mašina ima veliki vazdušni zazor, pa je magnećenje iz mreže vrlo „skupo". Primetite da je najveći deo ($q = 1$ pri $\delta = 0$) čista magnetizacija, a ostatak dolazi od opterećenja.

### Korak 6: Prividna snaga i struja generatora

**Zašto ovaj korak:** Struja statora zavisi od ukupne (prividne) snage, a nju sada čine mala aktivna i velika reaktivna komponenta. Ovo je poslednji traženi podatak — i test da li je mašina preopterećena.

Prividna snaga iz trougla snaga (mini-lekcija 7):

$$s = \sqrt{p^2 + q^2} = \sqrt{0{,}35^2 + 1{,}143^2} = \sqrt{0{,}1225 + 1{,}3064} = \sqrt{1{,}4289} = 1{,}195\ \mathrm{r.j.}$$

Struja iz relacije $s = u\cdot i$ (mini-lekcija 1), pri nazivnom naponu $u = 1$:

$$s = u\cdot i \;\Rightarrow\; i = \frac{s}{u} = \frac{1{,}195}{1} = 1{,}195\ \mathrm{r.j.}$$

**Šta smo dobili:** Struja generatora je $1{,}195$ puta veća od nazivne.

### Korak 7: Zaključak za režim a)

**Zašto ovaj korak:** Sklapamo sve delove odgovora koje zadatak traži.

Posle prekida pobude u režimu a):

- generator **ostaje da radi na mreži** (ne ispada iz sinhronizma), na uglu opterećenja $\delta = 22{,}21^\circ$;
- i dalje **odaje** aktivnu snagu $p = 0{,}35\ \mathrm{r.j.}$ ($7\ \mathrm{MW}$);
- **uzima iz mreže** reaktivnu snagu $q = 1{,}143\ \mathrm{r.j.}$;
- struja mu je $i = 1{,}195\ \mathrm{r.j.}$, tj. **za 19,5% veća od nazivne** — mašina je **preopterećena**.

Dakle, režim je moguć sa stanovišta sinhronizma, ali **nije trajno održiv bez posledica**: struja od 119,5% nazivne pregrevaće statorski namotaj, pa ovakav rad sme da potraje samo kratko — dok se pobuda ne popravi ili mašina ne rastereti/isključi.

### DEO b) — opterećenje 8 MVA, $\cos\varphi = 0{,}9$, napon mreže 8 kV

### Korak 8: Aktivna snaga u režimu b)

**Zašto ovaj korak:** Isto kao u Koraku 1 — snaga turbine se prekidom pobude ne menja, pa nam treba aktivna snaga koju mašina mora da iznese.

$$P = S\cdot\cos\varphi = 8\ \mathrm{MVA}\cdot 0{,}9 = 7{,}2\ \mathrm{MW}$$

U relativnim jedinicama (ista baza kao u Koraku 1, $P_{\mathrm{b}} = S_{\mathrm{n}} = 20\ \mathrm{MVA}$):

$$p = \frac{P}{P_{\mathrm{b}}} = \frac{P}{S_{\mathrm{n}}} = \frac{7{,}2}{20} = 0{,}36\ \mathrm{r.j.}$$

**Šta smo dobili:** Aktivno opterećenje je gotovo isto kao u režimu a) — jedva 1 procentni poen više (0,36 prema 0,35). Na prvi pogled očekivali bismo isti ishod... ali napon mreže sada nije isti!

### Korak 9: Maksimalna reluktantna snaga pri sniženom naponu

**Zašto ovaj korak:** Kriterijum održivosti poredi $p$ sa $p_{\mathrm{max}}$, a $p_{\mathrm{max}}$ zavisi od **kvadrata napona** (mini-lekcija 5) — pri sniženom naponu mreže granica je niža i moramo je ponovo izračunati.

Napon mreže je $U = 8\ \mathrm{kV}$, pa je relativni napon:

$$u = \frac{U}{U_{\mathrm{b}}} = \frac{U}{U_{\mathrm{n}}} = \frac{8}{10} = 0{,}8\ \mathrm{r.j.}$$

Maksimalna reluktantna snaga:

$$p_{\mathrm{max}} = \frac{1}{2}\cdot u^2\cdot\left(\frac{1}{x_q} - \frac{1}{x_d}\right) = \frac{1}{2}\cdot 0{,}8^2\cdot\left(\frac{1}{0{,}5} - \frac{1}{1}\right) = \frac{1}{2}\cdot 0{,}64\cdot(2-1) = 0{,}32\ \mathrm{r.j.}$$

**Šta smo dobili:** Pad napona na 80% oborio je „plafon" snage sa 0,5 na 0,32 r.j. — na samo 64% ranije vrednosti, jer napon ulazi na kvadrat ($0{,}8^2 = 0{,}64$).

### Korak 10: Provera održivosti i zaključak za režim b)

**Zašto ovaj korak:** Poredimo opterećenje sa novom, nižom granicom.

$$p = 0{,}36\ \mathrm{r.j.} > p_{\mathrm{max}} = 0{,}32\ \mathrm{r.j.}$$

Opterećenje je **veće** od maksimalne snage koju mašina bez pobude pri ovom naponu može da prenese. Ravnotežni ugao ne postoji: turbina gura rotor jače nego što reluktantni mehanizam može da ga drži, rotor se ubrzava i ugao $\delta$ neograničeno raste.

**Šta smo dobili:** Generator će u režimu b) pri prekidu pobude **ispasti iz sinhronizma** — neće moći da nastavi rad na mreži. Zato za ovaj režim nema smisla računati ustaljene vrednosti $q$, $s$ i $i$: ustaljeno sinhrono stanje ne postoji, pa te veličine nisu definisane (tu se, iz istog razloga, zaustavlja i originalna zbirka); mašinu mora da isključi zaštita. Odgovor na pitanje zadatka: režim **nije moguć/održiv**.

## Česte greške i zamke

1. **Zaboravljen kvadrat napona u $p_{\mathrm{max}}$.** Najčešća greška baš na ovom zadatku: student u delu b) uvrsti $u = 0{,}8$ linearno (ili ga sasvim zaboravi) i dobije $p_{\mathrm{max}} = 0{,}4$ ili $0{,}5$, pa pogrešno zaključi da mašina ostaje u sinhronizmu. Napon ulazi **na kvadrat**: $0{,}8^2 = 0{,}64$, pa je $p_{\mathrm{max}} = 0{,}32 < p = 0{,}36$ — mašina ispada.
2. **Pogrešna baza za aktivnu snagu.** Relativna aktivna snaga se računa deljenjem **nazivnom prividnom snagom** $S_{\mathrm{n}} = 20\ \mathrm{MVA}$, a ne nazivnom aktivnom snagom $S_{\mathrm{n}}\cos\varphi_{\mathrm{n}} = 18\ \mathrm{MW}$. Baza je jedna te ista za $P$, $Q$ i $S$ — inače relacije poput $s = \sqrt{p^2+q^2}$ ne bi važile.
3. **Ugao iz $\sin(2\delta)$.** Iz $\sin(2\delta) = 0{,}7$ prvo sledi $2\delta = 44{,}43^\circ$, pa **tek onda** deljenje sa 2: $\delta = 22{,}21^\circ$. Ko požuri i napiše $\delta = \arcsin(0{,}7) = 44{,}43^\circ$, dobiće pogrešnu (i to nestabilnu!) radnu tačku, a zatim i pogrešno $q$.
4. **„Bez pobude nema snage."** Netačno za mašinu sa **istaknutim polovima**: reluktantna komponenta postoji i bez pobude, jer potiče od magnetne nesimetrije rotora, a ne od pobudne struje. (Za turbogenerator sa glatkim rotorom, $x_d = x_q$, tvrdnja bi bila tačna — tamo bi prekid pobude uvek značio ispadanje iz sinhronizma pri bilo kom opterećenju.)
5. **Pogrešan smer reaktivne snage.** Posle gubitka pobude generator ne „proizvodi" reaktivnu snagu — on je **uzima iz mreže** (magneti se iz mreže). U delu a) to je ogromnih $1{,}143\ \mathrm{r.j.}$; upravo po naglom skoku potrošnje reaktivne snage zaštita od gubitka pobude i prepoznaje ovaj kvar.
6. **Zaključak „radi na mreži = sve je u redu."** U delu a) mašina jeste ostala u sinhronizmu, ali sa strujom 19,5% iznad nazivne — to je preopterećenje koje se sme tolerisati samo kratkotrajno.

## Rezime rezultata

| Veličina | Oznaka | Režim a) | Režim b) |
|---|---|---|---|
| Aktivna snaga generatora | $P$, $p$ | $7\ \mathrm{MW} = 0{,}35\ \mathrm{r.j.}$ | $7{,}2\ \mathrm{MW} = 0{,}36\ \mathrm{r.j.}$ |
| Relativni napon mreže | $u$ | $1$ | $0{,}8$ |
| Maksimalna reluktantna snaga | $p_{\mathrm{max}}$ | $0{,}5\ \mathrm{r.j.}$ | $0{,}32\ \mathrm{r.j.}$ |
| Održivost rada bez pobude | — | **DA** ($p < p_{\mathrm{max}}$) | **NE** ($p > p_{\mathrm{max}}$) — ispada iz sinhronizma |
| Ugao opterećenja | $\delta$ | $22{,}21^\circ$ | ne postoji (nema ravnoteže) |
| Reaktivna snaga (uzima iz mreže) | $q$ | $1{,}143\ \mathrm{r.j.}$ | — |
| Prividna snaga | $s$ | $1{,}195\ \mathrm{r.j.}$ | — |
| Struja generatora | $i$ | $1{,}195\ \mathrm{r.j.}$ (preopterećenje $19{,}5\%$) | — |

## Provera smisla

**1. Provera reaktivne snage nezavisnim putem.** Umesto sređene formule $q = 1 + \sin^2\delta$, uvrstimo $\delta = 22{,}21^\circ$ direktno u polazni oblik: $\cos(22{,}21^\circ) = 0{,}926$, $\sin(22{,}21^\circ) = 0{,}378$, pa je $q = \cos^2\delta/x_d + \sin^2\delta/x_q = 0{,}857/1 + 0{,}143/0{,}5 = 0{,}857 + 0{,}286 = 1{,}143\ \mathrm{r.j.}$ — poklapa se. Usput i kontrola trigonometrije: $0{,}857 + 0{,}143 = 1 = \cos^2\delta + \sin^2\delta$.

**2. Prevod u stvarne jedinice.** U režimu a): $Q = q\cdot S_{\mathrm{n}} = 1{,}143\cdot 20 = 22{,}86\ \mathrm{MVAr}$ i $S = s\cdot S_{\mathrm{n}} = 1{,}195\cdot 20 = 23{,}9\ \mathrm{MVA}$ — mašina od 20 MVA nosi 23,9 MVA, što je tačno onih 19,5% preopterećenja koje pokazuje i struja. Nazivna struja je $I_{\mathrm{n}} = S_{\mathrm{n}}/(\sqrt{3}\,U_{\mathrm{n}}) = 20\cdot 10^6/(\sqrt{3}\cdot 10^4) \approx 1155\ \mathrm{A}$, pa je stvarna struja $I = 1{,}195\cdot 1155 \approx 1380\ \mathrm{A}$. Dimenziono i brojčano sve konzistentno.

**3. Granični slučaj — glatki rotor.** Ako bi bilo $x_q = x_d$ (turbogenerator), zagrada $\left(1/x_q - 1/x_d\right)$ postaje nula, pa je $p_{\mathrm{max}} = 0$: mašina bez pobude ne bi mogla da prenese **nikakvu** aktivnu snagu i ispala bi iz sinhronizma u oba režima. Naša formula se, dakle, ponaša ispravno u graničnom slučaju, a rezultat dela a) je moguć isključivo zahvaljujući istaknutim polovima ($x_q = 0{,}5 < x_d = 1$).

**4. Zašto a) prolazi a b) ne, iako su opterećenja skoro ista?** Opterećenja se razlikuju za samo 0,01 r.j. (0,35 prema 0,36), ali granica $p_{\mathrm{max}}$ padne sa 0,5 na 0,32 zbog kvadrata sniženog napona. Fizički smisleno: reluktantna „opruga" koja drži rotor pravi se od polja mreže, pa slabija mreža (niži napon) znači kvadratno slabije držanje.
