# Zadatak 17 — Mehanički moment pogonske mašine sinhronog generatora iz bilansa snaga

## Postavka

Šestopolni sinhroni generator vezan je na mrežu linijskog napona $380\ \mathrm{V}$ i frekvencije $50\ \mathrm{Hz}$, i toj mreži daje struju od $100\ \mathrm{A}$ uz faktor snage $0{,}8$. Pri tome generator ima gubitke u gvožđu od $2500\ \mathrm{W}$ i gubitke usled trenja i ventilacije od $1000\ \mathrm{W}$. Fazni namotaji statora vezani su u zvezdu i imaju otpor po fazi $0{,}1\ \mathrm{\Omega}$.

Koliki mehanički moment razvija pogonska mašina ovog sinhronog generatora?

> **Prevod na običan jezik:** Sinhroni generator ne pravi energiju ni iz čega — njega okreće neka *pogonska mašina* (na primer turbina ili dizel-motor). Ta pogonska mašina mora da preko vratila unese dovoljno mehaničke snage da pokrije: (1) električnu snagu koju generator predaje mreži i (2) sve gubitke koji se usput "potroše" unutar generatora (grejanje namotaja, grejanje gvožđa, trenje u ležajevima, ventilacija). Dato nam je koliko generator daje mreži (napon, struja, faktor snage) i koliki su pojedini gubici (ili podaci iz kojih ih računamo). Treba da saberemo sve to u ukupnu mehaničku snagu na vratilu, a zatim da tu snagu, preko brzine obrtanja, pretvorimo u **moment** — jer se pogonske mašine dimenzionišu upravo po momentu koji moraju da razviju.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Broj polova generatora | $2p$ | $6$ (tj. $p = 3$ pari polova) | Koliko magnetnih polova (naizmenično N i S) ima obrtno polje mašine; određuje brzinu obrtanja pri zadatoj frekvenciji |
| Linijski napon mreže | $U_{\mathrm{s}}$ | $380\ \mathrm{V}$ | Napon izmeren *između dva fazna provodnika* mreže na koju je generator vezan |
| Frekvencija mreže | $f$ | $50\ \mathrm{Hz}$ | Broj perioda naizmeničnog napona u sekundi; diktira brzinu obrtanja sinhrone mašine |
| Struja opterećenja | $I_{\mathrm{sf}}$ | $100\ \mathrm{A}$ | Struja koju generator šalje u mrežu; kod sprege u zvezdu linijska struja je ujedno i fazna struja namotaja |
| Faktor snage | $\cos\varphi$ | $0{,}8$ | Deo prividne snage koji je *aktivna* (korisna) snaga; $\varphi$ je fazni pomeraj između napona i struje |
| Gubici u gvožđu | $P_{\mathrm{Fe}}$ | $2500\ \mathrm{W}$ | Snaga koja se pretvara u toplotu u magnetnom kolu (limovima) zbog vrtložnih struja i histerezisa |
| Gubici trenja i ventilacije | $P_{\mathrm{trv}}$ | $1000\ \mathrm{W}$ | Mehanička snaga izgubljena na trenje u ležajevima i na pokretanje vazduha za hlađenje |
| Otpor statorskog namotaja po fazi | $R_{\mathrm{s}}$ | $0{,}1\ \mathrm{\Omega}$ | Omski (aktivni) otpor jednog faznog namotaja statora; kroz njega struja stvara Džulove gubitke |
| Sprega statorskih namotaja | — | zvezda (Y) | Način vezivanja tri fazna namotaja: svi imaju jedan zajednički kraj (zvezdište) |

**Traži se:** mehanički moment pogonske mašine $M$.

## Šta se traži i zašto

**Mehanički moment pogonske mašine $M$** — to je obrtni moment (u njutn-metrima) koji turbina, motor SUS ili neka druga pogonska mašina mora stalno da razvija na vratilu da bi generator radio u opisanom režimu. Inženjera ovaj podatak zanima iz vrlo praktičnog razloga: pogonska mašina i spojnica (veza dva vratila) biraju se i dimenzionišu po momentu koji moraju da prenesu — premala pogonska mašina jednostavno ne bi mogla da "izgura" ovaj teret i generator bi ispao iz rada.

Plan rešavanja, običnim jezikom:

1. Iz linijskog napona mreže izračunamo **fazni napon** generatora (jer su namotaji u zvezdi, pa je napon na jednom namotaju manji od linijskog).
2. Iz faznog napona, struje i faktora snage izračunamo **izlaznu električnu snagu** $P$ — ono što generator zaista predaje mreži.
3. Iz otpora namotaja i struje izračunamo **gubitke u bakru statora** $P_{\mathrm{Cus}}$.
4. Saberemo **sve gubitke** u ukupnu snagu gubitaka $P_{\mathrm{g}}$ (bakar + gvožđe + trenje i ventilacija; gubitke pobude opravdano zanemarujemo — objašnjeno u teoriji).
5. **Bilans snage:** ulazna mehanička snaga $P_{\mathrm{M}}$ = izlazna snaga + svi gubici.
6. Iz broja polova i frekvencije nađemo **brzinu obrtanja**, pa iz $P_{\mathrm{M}}$ i brzine izračunamo traženi **moment** $M$.

## Potrebna teorija — mini-lekcije

### 1. Tok snage kroz sinhroni generator: ko kome šta daje

Sinhroni generator je pretvarač mehaničke energije u električnu. Na jednom kraju je **pogonska mašina** (turbina, motor) koja preko vratila unosi *mehaničku snagu* $P_{\mathrm{M}}$. Na drugom kraju su priključci statora preko kojih generator predaje mreži *električnu snagu* $P$. Između ta dva kraja deo snage se neizbežno gubi — pretvara se u toplotu unutar same mašine. Zakon održanja energije zato glasi:

$$P_{\mathrm{M}} = P + P_{\mathrm{g}}$$

gde je $P_{\mathrm{g}}$ ukupna snaga svih gubitaka. Ovo je "srce" celog zadatka: ako znamo izlaz i gubitke, ulaz dobijamo prostim sabiranjem. Intuicija: kao vodovodna cev koja curi — na izvoru moraš upumpati onoliko vode koliko izađe na slavini *plus* onoliko koliko iscuri usput.

### 2. Sprega u zvezdu: linijski i fazni napon (i struja)

Tri fazna namotaja statora mogu se vezati na dva načina: u **zvezdu** (Y) — svi namotaji jednim krajem spojeni u zajedničku tačku (zvezdište) — ili u **trougao** (D) — namotaji vezani "u krug". Kod zvezde, između dva linijska priključka mreže nalaze se *dva namotaja na red*, ali njihovi naponi nisu u fazi (pomereni su za $120^\circ$), pa se ne sabiraju prosto već vektorski. Rezultat tog vektorskog sabiranja je da je linijski napon $\sqrt{3}$ puta veći od faznog:

$$U_{\mathrm{sf}} = \frac{U_{\mathrm{s}}}{\sqrt{3}}$$

- $U_{\mathrm{s}}$ — linijski (međufazni) napon, ono što piše na natpisnoj pločici mreže,
- $U_{\mathrm{sf}}$ — fazni napon, tj. napon na *jednom* namotaju.

Za struju kod zvezde važi obrnuto pojednostavljenje: linijski provodnik se direktno nastavlja na fazni namotaj, pa je **linijska struja jednaka faznoj struji**. Zato struja od $100\ \mathrm{A}$ koju generator "daje mreži" jeste upravo struja kroz svaki fazni namotaj, $I_{\mathrm{sf}} = 100\ \mathrm{A}$ — nju koristimo i za snagu i za gubitke u bakru.

### 3. Aktivna snaga trofaznog sistema

Jedna faza naizmeničnog sistema predaje aktivnu (korisnu, srednju) snagu $U_{\mathrm{sf}} \cdot I_{\mathrm{sf}} \cdot \cos\varphi$. Član $\cos\varphi$ (faktor snage) je tu zato što napon i struja u opštem slučaju nisu u fazi: samo komponenta struje koja je "u fazi" sa naponom prenosi korisnu snagu, a ta komponenta iznosi $I_{\mathrm{sf}}\cos\varphi$. Trofazni sistem ima tri jednake faze, pa je ukupna aktivna snaga prosto tri puta veća:

$$P = 3 \cdot U_{\mathrm{sf}} \cdot I_{\mathrm{sf}} \cdot \cos\varphi$$

Ovo je snaga koju generator zaista isporučuje mreži — "roba koju prodajemo".

### 4. Gubici u sinhronoj mašini — kompletan spisak

Ukupni gubici sinhronog generatora sastoje se od četiri glavne stavke:

$$P_{\mathrm{g}} = P_{\mathrm{Cur}} + P_{\mathrm{Cus}} + P_{\mathrm{Fe}} + P_{\mathrm{trv}}$$

1. **Gubici u pobudnom (rotorskom) kolu $P_{\mathrm{Cur}}$.** Sinhrona mašina na rotoru nosi pobudni namotaj kroz koji teče jednosmerna struja i pravi magnetno polje; taj namotaj ima otpor, pa se u njemu troši snaga. Iskustveno, ovi gubici su **obično svega oko 1 % nominalne snage generatora** — mali su, i kada (kao ovde) podaci o pobudi nisu dati, opravdano ih je zanemariti: $P_{\mathrm{Cur}} \approx 0$. (Ovo obrazloženje daje i originalna zbirka.)
2. **Gubici u bakru statora $P_{\mathrm{Cus}}$.** Džulovi (omski) gubici: struja $I_{\mathrm{sf}}$ kroz otpor $R_{\mathrm{s}}$ svake od tri faze greje namotaj. Iz Džulovog zakona ($P = R I^2$ za jedan otpornik), za tri faze:
   $$P_{\mathrm{Cus}} = 3 \cdot R_{\mathrm{s}} \cdot I_{\mathrm{sf}}^2$$
   Napomena iz originala: pored čistih Džulovih gubitaka postoje i tzv. *dodatni gubici* (od rasipnih polja, potiskivanja struje itd.), ali njih ovde zanemarujemo i celokupne gubitke u bakru poistovećujemo sa Džulovim.
3. **Gubici u gvožđu $P_{\mathrm{Fe}}$.** Magnetni fluks se u statorskim limovima naizmenično menja, pa nastaju vrtložne struje i histerezisni gubici — gvožđe se greje. Zavise od napona (fluksa) i frekvencije, ne od struje opterećenja; ovde su dati direktno: $2500\ \mathrm{W}$.
4. **Mehanički gubici $P_{\mathrm{trv}}$** (trenje i ventilacija). Trenje u ležajevima i snaga potrebna da rotor "melje" vazduh i tera ga kroz kanale za hlađenje. Zavise od brzine obrtanja; dati su direktno: $1000\ \mathrm{W}$.

### 5. Sinhrona brzina: zašto se generator obrće baš tako brzo

Sinhrona mašina se, po definiciji, obrće *sinhrono* sa obrtnim magnetnim poljem koje stvara mreža frekvencije $f$. Polje napravi jedan pun električni ciklus za jednu periodu napona; ako mašina ima $p$ **pari polova**, rotoru za jedan pun mehanički obrtaj treba $p$ električnih ciklusa. Zato je brzina obrtanja u obrtajima u minuti:

$$n = \frac{60 \cdot f}{p}$$

- $n$ — brzina obrtanja $[\mathrm{ob/min}]$; broj $60$ prevodi sekunde u minute,
- $f$ — frekvencija mreže $[\mathrm{Hz}]$,
- $p$ — broj **pari** polova (ne broj polova!).

**Pažnja na formulaciju "šestopolni":** to znači da mašina ima $2p = 6$ polova, dakle $p = 3$ para polova. Ovo je klasična zamka — u formulu ide $p = 3$, a ne $6$.

### 6. Veza snage, momenta i brzine obrtanja

Osnovna mehanička relacija za sve obrtne mašine: snaga je proizvod momenta i ugaone brzine,

$$P_{\mathrm{M}} = M \cdot \Omega \quad\Longrightarrow\quad M = \frac{P_{\mathrm{M}}}{\Omega}$$

- $M$ — moment $[\mathrm{Nm}]$,
- $\Omega$ — mehanička ugaona brzina $[\mathrm{rad/s}]$.

Poreklo: moment je "obrtna sila", ugaona brzina je "obrtna brzina", a snaga je uvek sila puta brzina — ovo je samo obrtni analog poznatog $P = F \cdot v$ za pravolinijsko kretanje. Ugaona brzina i brzina u obrtajima u minuti vezane su preko punog kruga ($2\pi$ radijana po obrtaju) i minuta ($60$ sekundi):

$$\Omega = \frac{2\pi n}{60} = \frac{\pi n}{30}$$

Odatle sledi praktičan oblik koji koristi i zbirka:

$$M = \frac{P_{\mathrm{M}}}{\Omega} = \frac{P_{\mathrm{M}}}{\dfrac{\pi n}{30}} = \frac{30}{\pi}\cdot\frac{P_{\mathrm{M}}}{n}$$

### 7. Zašto je moment pogonske mašine jednak momentu generatora

U ustaljenom (stacionarnom) režimu brzina obrtanja je konstantna, pa je ukupan moment na vratilu nula: moment kojim pogonska mašina gura vratilo napred tačno je jednak momentu kojim mu se generator (elektromagnetno kočenje + trenje) opire. Zato je moment koji izračunamo iz *ulazne mehaničke snage* generatora ujedno i **traženi moment pogonske mašine** — to su dva imena za isti broj.

## Rešenje, korak po korak

### Korak 1: Fazni napon generatora

**Zašto ovaj korak:** Formula za trofaznu snagu (mini-lekcija 3) traži *fazni* napon, a mreža nam je zadala *linijski*. Pošto su namotaji u zvezdi, prelazimo sa linijskog na fazni deljenjem sa $\sqrt{3}$ (mini-lekcija 2).

Opšti oblik:

$$U_{\mathrm{sf}} = \frac{U_{\mathrm{s}}}{\sqrt{3}}$$

Uvrštavamo $U_{\mathrm{s}} = 380\ \mathrm{V}$:

$$U_{\mathrm{sf}} = \frac{380}{\sqrt{3}} = \frac{380}{1{,}732} \approx 220\ \mathrm{V}$$

> **Napomena o originalu:** Strogo računato, $380/\sqrt{3} = 219{,}4\ \mathrm{V}$. Zbirka (kao i sva inženjerska praksa za standardnu mrežu $380\ \mathrm{V}$) zaokružuje na standardnu vrednost faznog napona $220\ \mathrm{V}$ i sa njom nastavlja račun — i mi radimo isto, da bi se svi dalji brojevi poklopili. Razlika je ispod $0{,}3\ \%$ i na konačni rezultat praktično ne utiče.

**Šta smo dobili:** Napon na jednom faznom namotaju je $220\ \mathrm{V}$ — poznati par "$380/220\ \mathrm{V}$" klasične trofazne mreže: $380\ \mathrm{V}$ između faza, $220\ \mathrm{V}$ između faze i zvezdišta (neutralne tačke).

### Korak 2: Izlazna električna snaga generatora

**Zašto ovaj korak:** Ovo je "korisni" deo bilansa — snaga koju generator zaista predaje mreži. Bez nje ne možemo sastaviti bilans iz mini-lekcije 1.

Opšti oblik (mini-lekcija 3):

$$P = 3 \cdot U_{\mathrm{sf}} \cdot I_{\mathrm{sf}} \cdot \cos\varphi$$

Struja od $100\ \mathrm{A}$ koju generator daje mreži je, zbog sprege u zvezdu, ujedno i fazna struja: $I_{\mathrm{sf}} = 100\ \mathrm{A}$ (mini-lekcija 2). Uvrštavamo:

$$P = 3 \cdot 220 \cdot 100 \cdot 0{,}8 = 66000 \cdot 0{,}8 = 52800\ \mathrm{W} = 52{,}8\ \mathrm{kW}$$

**Šta smo dobili:** Generator isporučuje mreži $52{,}8\ \mathrm{kW}$ aktivne snage. To je red veličine manjeg industrijskog agregata — razuman broj za mašinu koja pri $380\ \mathrm{V}$ daje $100\ \mathrm{A}$.

### Korak 3: Gubici u bakru statora

**Zašto ovaj korak:** Od četiri vrste gubitaka, dva su nam data direktno ($P_{\mathrm{Fe}}$, $P_{\mathrm{trv}}$), gubitke pobude zanemarujemo, a gubitke u bakru moramo *izračunati* iz datog otpora po fazi i struje.

Opšti oblik (Džulov zakon za tri faze, mini-lekcija 4):

$$P_{\mathrm{Cus}} = 3 \cdot R_{\mathrm{s}} \cdot I_{\mathrm{sf}}^2$$

- $R_{\mathrm{s}} = 0{,}1\ \mathrm{\Omega}$ — otpor jednog faznog namotaja,
- $I_{\mathrm{sf}} = 100\ \mathrm{A}$ — struja kroz taj namotaj,
- množilac $3$ — jer se greju sva tri fazna namotaja jednako.

Uvrštavamo, pazeći da se struja kvadrira:

$$P_{\mathrm{Cus}} = 3 \cdot 0{,}1 \cdot 100^2 = 3 \cdot 0{,}1 \cdot 10000 = 3000\ \mathrm{W} = 3\ \mathrm{kW}$$

Pri tome, po originalu, *dodatne gubitke* zanemarujemo i sve gubitke u bakru poistovećujemo sa Džulovim (mini-lekcija 4).

**Šta smo dobili:** U grejanje statorskih namotaja odlazi $3\ \mathrm{kW}$ — oko $5{,}7\ \%$ isporučene snage, što je tipičan red veličine za mašinu ove klase.

### Korak 4: Ukupni gubici snage generatora

**Zašto ovaj korak:** Bilans snage traži *zbir svih* gubitaka — sada ih imamo sve na broju pa ih sabiramo.

Opšti oblik (mini-lekcija 4):

$$P_{\mathrm{g}} = P_{\mathrm{Cur}} + P_{\mathrm{Cus}} + P_{\mathrm{Fe}} + P_{\mathrm{trv}}$$

Gubici pobude $P_{\mathrm{Cur}}$ nisu dati, a kako su obično svega oko $1\ \%$ nominalne snage generatora, zanemarujemo ih: $P_{\mathrm{Cur}} \approx 0$ (mini-lekcija 4). Uvrštavamo:

$$P_{\mathrm{g}} = 0 + 3000 + 2500 + 1000 = 6500\ \mathrm{W} = 6{,}5\ \mathrm{kW}$$

**Šta smo dobili:** Ukupno se u generatoru "izgubi" (pretvori u toplotu) $6{,}5\ \mathrm{kW}$. Najveća stavka su gubici u bakru, zatim gvožđe, pa mehanika — uobičajen raspored kod opterećene mašine.

### Korak 5: Ulazna mehanička snaga generatora

**Zašto ovaj korak:** Sada sklapamo bilans iz mini-lekcije 1: pogonska mašina mora da unese i ono što izlazi u mrežu i ono što se usput izgubi.

Opšti oblik:

$$P_{\mathrm{M}} = P + P_{\mathrm{g}}$$

Uvrštavamo:

$$P_{\mathrm{M}} = 52800 + 6500 = 59300\ \mathrm{W} = 59{,}3\ \mathrm{kW}$$

> **Napomena o originalu:** U zbirci na ovom mestu piše "$59{,}33\ \mathrm{[kW]}$" — to je očigledna štamparska greška, jer je $59300\ \mathrm{W}$ tačno $59{,}3\ \mathrm{kW}$. U vatima je vrednost u zbirci ispravna ($59300\ \mathrm{W}$) i sa njom se dalje računa, pa greška ne utiče na konačni rezultat.

**Šta smo dobili:** Pogonska mašina mora na vratilo da isporučuje $59{,}3\ \mathrm{kW}$ mehaničke snage — više od izlazne snage tačno za iznos gubitaka, kako i mora biti.

### Korak 6: Brzina obrtanja i traženi mehanički moment

**Zašto ovaj korak:** Snagu na vratilu sada pretvaramo u moment. Za to nam treba brzina obrtanja, a nju kod sinhrone mašine jednoznačno određuju frekvencija mreže i broj pari polova (mini-lekcija 5).

Prvo brzina. Šestopolna mašina ima $p = 6/2 = 3$ para polova, pa je:

$$n = \frac{60 \cdot f}{p} = \frac{60 \cdot 50}{3} = \frac{3000}{3} = 1000\ \mathrm{ob/min}$$

Sada moment. Krećemo od opšteg oblika $M = P_{\mathrm{M}}/\Omega$ i u njega, korak po korak, uvrštavamo $\Omega = \pi n/30$ pa $n = 60f/p$ (mini-lekcije 5 i 6) — tako nastaje lanac jednakosti koji koristi i zbirka:

$$M = \frac{30}{\pi}\cdot\frac{P_{\mathrm{M}}}{n} = \frac{30}{\pi}\cdot\frac{P_{\mathrm{M}}}{\dfrac{60\cdot f}{p}} = \frac{30 \cdot p \cdot P_{\mathrm{M}}}{60 \cdot \pi \cdot f} = \frac{p \cdot P_{\mathrm{M}}}{2\pi f}$$

(u poslednjem prelazu skratili smo $30/60 = 1/2$). Uvrštavamo $p = 3$, $P_{\mathrm{M}} = 59300\ \mathrm{W}$ i $f = 50\ \mathrm{Hz}$:

$$M = \frac{3 \cdot 59300}{2 \cdot \pi \cdot 50} = \frac{177900}{314{,}16} = 566{,}273\ \mathrm{Nm}$$

Ista vrednost dobija se i "školskim" putem preko ugaone brzine: $\Omega = \pi n/30 = \pi \cdot 1000/30 = 104{,}72\ \mathrm{rad/s}$, pa $M = 59300/104{,}72 = 566{,}27\ \mathrm{Nm}$ — brojevi se poklapaju, što je dobra unutrašnja kontrola.

**Šta smo dobili:** Pogonska mašina mora da razvija moment od približno $566\ \mathrm{Nm}$ pri $1000\ \mathrm{ob/min}$. Pošto je u ustaljenom režimu moment pogonske mašine jednak momentu kojim joj se generator opire (mini-lekcija 7), ovo je ujedno i mehanički moment sinhronog generatora — **traženi rezultat**.

## Česte greške i zamke

1. **"Šestopolni" pročitano kao $p = 6$.** U formulu za sinhronu brzinu ide broj *pari* polova, $p = 3$, a ne broj polova $6$. Ko uvrsti $p = 6$ dobije $n = 500\ \mathrm{ob/min}$ i duplo veći moment ($\approx 1132{,}5\ \mathrm{Nm}$) — greška od tačno faktora $2$.
2. **Linijski napon ubačen u formulu $P = 3\,U I\cos\varphi$.** Sa množiocem $3$ ide *fazni* napon ($220\ \mathrm{V}$). Ako želiš da radiš sa linijskim naponom, formula glasi $P = \sqrt{3}\,U_{\mathrm{s}} I \cos\varphi$ — obe daju isto, ali mešanje ("$3 \cdot 380 \cdot \ldots$") daje $\sqrt{3}$ puta preveliku snagu.
3. **Oduzimanje umesto sabiranja gubitaka.** Kod *generatora* je mehanička snaga ULAZ, pa je $P_{\mathrm{M}} = P + P_{\mathrm{g}}$ — gubici se *dodaju* na izlaznu snagu. (Kod motora je obrnuto: izlazna mehanička snaga je ulazna električna *minus* gubici.) Ko oduzme, dobije $46{,}3\ \mathrm{kW}$ i premali moment.
4. **Zaboravljen kvadrat ili trojka u gubicima u bakru.** $P_{\mathrm{Cus}} = 3 R_{\mathrm{s}} I_{\mathrm{sf}}^2$: bez kvadrata ispadne smešnih $30\ \mathrm{W}$, bez trojke $1000\ \mathrm{W}$ — oba pogrešna.
5. **Mešanje $\Omega$ (rad/s) i $n$ (ob/min).** U $M = P/\Omega$ ide ugaona brzina u $\mathrm{rad/s}$. Ko podeli $P_{\mathrm{M}}$ direktno sa $n = 1000$, dobije $59{,}3\ \mathrm{Nm}$ — tačno $30/\pi \approx 9{,}55$ puta premalo.

## Rezime rezultata

| Veličina | Oznaka | Vrednost |
|---|---|---|
| Fazni napon generatora | $U_{\mathrm{sf}}$ | $220\ \mathrm{V}$ |
| Izlazna električna snaga | $P$ | $52800\ \mathrm{W} = 52{,}8\ \mathrm{kW}$ |
| Gubici u bakru statora | $P_{\mathrm{Cus}}$ | $3000\ \mathrm{W} = 3\ \mathrm{kW}$ |
| Ukupni gubici | $P_{\mathrm{g}}$ | $6500\ \mathrm{W} = 6{,}5\ \mathrm{kW}$ |
| Ulazna mehanička snaga | $P_{\mathrm{M}}$ | $59300\ \mathrm{W} = 59{,}3\ \mathrm{kW}$ |
| Brzina obrtanja | $n$ | $1000\ \mathrm{ob/min}$ |
| **Mehanički moment pogonske mašine** | $M$ | $\approx 566{,}273\ \mathrm{Nm}$ |

## Provera smisla

**1. Dimenziona provera momenta.** U formuli $M = p\,P_{\mathrm{M}}/(2\pi f)$ veličina $p$ je neimenovan broj, $2\pi$ takođe, pa dimenzije daju $\mathrm{W}/\mathrm{Hz} = \mathrm{W\cdot s} = \mathrm{J} = \mathrm{Nm}$ — džul je njutn-metar, dakle jedinica momenta izlazi ispravno.

**2. Stepen iskorišćenja.** Odnos izlazne i ulazne snage je $\eta = P/P_{\mathrm{M}} = 52800/59300 = 0{,}89$, tj. oko $89\ \%$. Za sinhroni generator ove veličine (desetine kilovata) to je sasvim realan stepen iskorišćenja — da smo dobili npr. $50\ \%$ ili $99{,}9\ \%$, znali bismo da smo negde pogrešili u bilansu.

**3. Gruba provera reda veličine momenta.** Snaga od $\approx 59\ \mathrm{kW}$ pri $\approx 105\ \mathrm{rad/s}$ mora dati moment reda $59000/105 \approx 560\ \mathrm{Nm}$ — dobili smo $566\ \mathrm{Nm}$, u punom saglasju. Rezultat prolazi sve tri provere.
