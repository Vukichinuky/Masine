# Zadatak 9 — Podpobuđeni hidrogenerator sa istaknutim polovima: EMS praznog hoda, ugao opterećenja i struja u dva režima

## Postavka

Trofazni sinhroni hidrogenerator radi priključen na krutu mrežu nazivnog napona $6{,}6\ \mathrm{kV}$ i učestanosti $50\ \mathrm{Hz}$. Generator predaje u mrežu aktivnu snagu $2\ \mathrm{MW}$, a iz mreže uzima $1\ \mathrm{MVAr}$ reaktivne snage. Odrediti:

**a)** indukovanu elektromotornu silu (praznog hoda) i ugao opterećenja u ovom režimu;

**b)** struju generatora, elektromotornu silu (praznog hoda) i ugao opterećenja ako generator treba da odaje istu aktivnu snagu u mrežu uz faktor snage jednak jedinici.

Nazivni podaci hidrogeneratora su: $5\ \mathrm{MVA}$, $6{,}6\ \mathrm{kV}$, $1500\ \mathrm{o/min}$, sprega Y; reaktansa rasipanja iznosi $20\ \%$, reaktansa reakcije indukta po uzdužnoj osi iznosi $80\ \%$, a reaktansa reakcije indukta po poprečnoj osi iznosi $35\ \%$. Napomena: svi gubici u mašini se mogu zanemariti.

> **Prevod na običan jezik:** Imamo veliki generator u hidroelektrani, vezan na jaku elektroenergetsku mrežu koja mu nameće napon i učestanost. On u mrežu šalje "korisnu" (aktivnu) snagu od 2 MW, ali istovremeno iz mreže **povlači** reaktivnu snagu od 1 MVAr — što je znak da mu je pobuda (jednosmerna struja u rotoru) podešena slabije nego obično. Treba da izračunamo: koliki unutrašnji napon (elektromotornu silu $E_0$) njegova pobuda trenutno pravi, i za koliki se ugao rotor "iskosio" unapred u odnosu na napon mreže (ugao opterećenja $\delta$). Zatim isto to ponovimo za slučaj kada operater dotera pobudu tako da generator sa mrežom uopšte ne razmenjuje reaktivnu snagu ($\cos\varphi = 1$), a i dalje šalje istih 2 MW — tada treba naći i novu struju. Reaktanse mašine nisu date u omima, nego u procentima nazivnih veličina, pa ćemo ih prvo morati "prevesti" u ome.

## Podaci

| Veličina | Oznaka | Vrednost | Šta ta veličina fizički znači |
|---|---|---|---|
| Nazivna prividna snaga | $S_{\mathrm{n}}$ | $5\ \mathrm{MVA}$ | Najveća trajno dozvoljena "ukupna" snaga (kombinacija aktivne i reaktivne) za koju su namotaji i izolacija dimenzionisani. |
| Nazivni (linijski) napon | $U_{\mathrm{n}}$ | $6{,}6\ \mathrm{kV}$ | Napon između dva priključka (linijski); pošto je sprega Y, fazni napon je $U_{\mathrm{n}}/\sqrt{3}$. |
| Učestanost mreže | $f$ | $50\ \mathrm{Hz}$ | Kruta mreža nameće ovu učestanost; generator se mora vrteti sinhrono sa njom. |
| Brzina obrtanja | $n$ | $1500\ \mathrm{o/min}$ | Sinhrona brzina; iz $n = 60f/p$ sledi $p = 2$ para polova (4 pola). |
| Sprega statora | — | Y (zvezda) | Način vezivanja tri fazna namotaja; kod zvezde je linijska struja jednaka faznoj, a linijski napon $\sqrt{3}$ puta veći od faznog. |
| Predata aktivna snaga | $P$ | $2\ \mathrm{MW}$ | Snaga koju generator zaista isporučuje mreži (pretvara se u rad/toplotu kod potrošača). |
| Reaktivna snaga **uzeta iz mreže** | $Q$ | $1\ \mathrm{MVAr}$ | Snaga koja se samo "ljulja" napred–nazad između mreže i mašine; ovde je mašina uzima, što znači da je podpobuđena. |
| Relativna reaktansa rasipanja | $x_{\gamma}$ | $20\ \%$ | Reaktansa od fluksa statorskih namotaja koji se rasipa i ne stiže do rotora, izražena u procentima bazne impedanse. |
| Relativna reaktansa reakcije indukta, uzdužna (d) osa | $x_{ad}$ | $80\ \%$ | Reaktansa kojom se opisuje magnetno dejstvo statorske struje duž ose polova rotora (gde je vazdušni zazor mali). |
| Relativna reaktansa reakcije indukta, poprečna (q) osa | $x_{aq}$ | $35\ \%$ | Isto to, ali duž ose između polova (gde je zazor veliki, pa je reaktansa manja). |
| Gubici | — | zanemareni | Otpor namotaja, gubici u gvožđu i mehanički gubici se ne računaju; naponska jednačina nema član $R\cdot I$. |

## Šta se traži i zašto

**1. Indukovana elektromotorna sila praznog hoda $E_0$ (fazna $E_{0f}$ i linijska $E_{0l}$).** To je napon koji bi se pojavio na krajevima generatora kada bismo ga, sa istom pobudnom strujom, otkačili od mreže (struja statora nula). Ona je direktna "slika" pobudne struje: veća pobuda → veće $E_0$. Inženjera zanima jer preko nje zna koliko je pobuda podešena i koliko rezerve ima do granice stabilnosti; u elektrani se pobudom upravlja upravo da bi se postigla željena razmena reaktivne snage.

**2. Ugao opterećenja $\delta$.** To je ugao za koji unutrašnja EMS $E_0$ (vezana za rotor) prednjači naponu mreže $U$. On je "mera napregnutosti" elektromagnetne veze rotora i mreže: što više aktivne snage guramo, $\delta$ je veći; ako pređe kritičnu vrednost, mašina ispada iz sinhronizma. Zato se $\delta$ uvek proverava.

**3. Struja generatora u režimu b).** Struja određuje zagrevanje namotaja i gubitke; pri istoj aktivnoj snazi struja je najmanja baš pri $\cos\varphi = 1$, i to ćemo videti brojkama.

**Plan rešavanja:**
1. Iz $P$ i $Q$ nađemo faktor snage i struju u režimu a).
2. Izračunamo baznu impedansu i pretvorimo procentualne reaktanse u ome; sastavimo sinhrone reaktanse $X_d$ i $X_q$.
3. Nacrtamo (opišemo) fazorski dijagram podpobuđenog generatora i iz njega izvučemo dve skalarne naponske jednačine (projekcije na d i q osu).
4. Iz jednačine po d osi rešimo ugao $\delta$, zatim komponentu struje $I_d$, pa iz jednačine po q osi elektromotornu silu $E_{0f}$ i njenu linijsku vrednost.
5. Za režim b) ($\cos\varphi = 1$) ponovimo postupak sa novim, jednostavnijim dijagramom: nova struja, novi $\delta$, novo $E_0$.

## Potrebna teorija — mini-lekcije

### Mini-lekcija 1: Kruta mreža

**Kruta (beskonačna) mreža** je idealizacija elektroenergetskog sistema: mreža toliko jaka da joj naš generator ne može promeniti ni napon ni učestanost, ma šta radio. Za nas to znači: napon na priključcima generatora je **konstantan**, $U_{\mathrm{n}} = 6{,}6\ \mathrm{kV}$, $f = 50\ \mathrm{Hz}$, i to su čvrste "referentne tačke" svih daljih računa. Generator na krutoj mreži može da menja samo dve stvari: koliko aktivne snage šalje (preko snage turbine) i koliko reaktivne snage razmenjuje (preko pobudne struje).

### Mini-lekcija 2: Aktivna, reaktivna i prividna snaga; faktor snage

Kod naizmeničnih sistema razlikujemo:
- **aktivnu snagu** $P$ $[\mathrm{W}]$ — onu koja se zaista pretvara u rad ili toplotu;
- **reaktivnu snagu** $Q$ $[\mathrm{VAr}]$ — onu koja se periodično preliva između izvora i magnetnih/električnih polja, ne vrši koristan rad, ali opterećuje vodove i namotaje strujom;
- **prividnu snagu** $S$ $[\mathrm{VA}]$ — njihovu "pitagorejsku" kombinaciju:

$$S = \sqrt{P^2 + Q^2}.$$

Ova formula dolazi iz trougla snaga: $P$ i $Q$ su katete, $S$ hipotenuza, jer su aktivna i reaktivna komponenta struje međusobno pomerene za $90^\circ$. **Faktor snage** je odnos

$$\cos\varphi = \frac{P}{S},$$

gde je $\varphi$ ugao između fazora napona i fazora struje. Za trofazni sistem sa linijskim naponom $U$ i linijskom strujom $I$ važi

$$P = \sqrt{3}\,U\,I\cos\varphi ,$$

pa kad znamo $P$, $U$ i $\cos\varphi$, struju dobijamo deljenjem. (Faktor $\sqrt{3}$ potiče od prelaska sa faznih na linijske veličine: $P = 3\,U_f I_f \cos\varphi = 3\cdot\frac{U}{\sqrt 3}\cdot I\cos\varphi = \sqrt3\,UI\cos\varphi$ kod sprege Y.)

### Mini-lekcija 3: Podpobuđen i natpobuđen generator; "kapacitivan" faktor snage

Pobudna (jednosmerna) struja u rotoru pravi glavni fluks mašine. Na krutoj mreži važi jednostavno pravilo:

- **Natpobuđen** generator (jaka pobuda, veliko $E_0$) **daje** reaktivnu snagu mreži — ponaša se kao kondenzatorska baterija; struja statora **kasni** za naponom (induktivan $\cos\varphi$ gledano iz mreže prema potrošačkoj konvenciji generatora).
- **Podpobuđen** generator (slaba pobuda, malo $E_0$) **uzima** reaktivnu snagu iz mreže; struja statora **prednjači** naponu — faktor snage je **kapacitivan**.

Intuicija: magnetno kolo mašine mora nekako da se namagnetiše. Ako pobuda ne da dovoljno "magnećenja", razliku mora da nadoknadi statorska struja iz mreže — a to je upravo uzimanje reaktivne snage. U našem zadatku generator **uzima** $1\ \mathrm{MVAr}$, dakle radi podpobuđen i struja mu prednjači naponu. Očekujemo zato da će ispasti $E_0 < U$ (unutrašnji napon manji od mrežnog) — to će nam kasnije poslužiti i kao provera.

### Mini-lekcija 4: Mašina sa istaknutim polovima i dvoosna (d–q) teorija

Hidrogeneratori imaju rotor sa **istaknutim polovima**: polovi štrče kao "pečurke", pa vazdušni zazor **nije svuda isti**. Duž ose polova (tzv. **uzdužna** ili **d osa**, od engl. *direct*) zazor je mali i magnetni put "lak"; između polova (tzv. **poprečna** ili **q osa**, od engl. *quadrature*, pomerena za $90^\circ$ električnih) zazor je veliki i magnetni put "težak".

Posledica: magnetno dejstvo statorske struje (tzv. **reakcija indukta**) zavisi od toga u kom pravcu deluje. Zato se u dvoosnoj (Blondelovoj) teoriji fazor statorske struje $\underline{I}_f$ razlaže na dve komponente:
- $I_d$ — komponenta duž d ose (deluje na glavni fluks: pojačava ga ili slabi),
- $I_q$ — komponenta duž q ose (stvara moment, "poprečno" izobličuje polje),

i svakoj komponenti se pridružuje **njena** reaktansa. Kod mašine sa okruglim (cilindričnim) rotorom ovo razlaganje ne bi bilo potrebno jer je zazor svuda isti ($X_d = X_q$); kod istaknutih polova je obavezno, i to je razlog što ovaj zadatak ima dve različite sinhrone reaktanse.

### Mini-lekcija 5: Od rasipanja i reakcije indukta do sinhronih reaktansi

Statorska struja pravi dva efekta, pa dve vrste reaktansi:

1. **Reaktansa rasipanja** $X_{\gamma}$ — obuhvata fluks koji se "rasipa" oko samih statorskih provodnika i uopšte ne prolazi kroz rotor. Ne zavisi od položaja rotora, ista je za obe ose.
2. **Reaktanse reakcije indukta** $X_{ad}$ (po d osi) i $X_{aq}$ (po q osi) — opisuju fluks koji statorska struja tera **kroz** mašinu, preko zazora. Pošto je zazor po d osi mali, $X_{ad}$ je velika; po q osi zazor je veliki, pa je $X_{aq}$ znatno manja ($80\ \%$ prema $35\ \%$ u našem zadatku — tipičan odnos za istaknute polove).

**Sinhrone reaktanse** su prosto zbirovi (rasipanje + reakcija po datoj osi):

$$X_d = X_{\gamma} + X_{ad}, \qquad X_q = X_{\gamma} + X_{aq}.$$

One su "ukupne" reaktanse kojima mašina reaguje na $I_d$ odnosno $I_q$ komponentu struje.

### Mini-lekcija 6: Relativne (procentualne) jedinice i bazna impedansa

Proizvođači reaktanse ne daju u omima nego u **procentima**, jer su tako uporedive među mašinama svih veličina. Procenat se odnosi na **baznu impedansu** $Z_B$ — impedansu koja bi pri nazivnom faznom naponu propuštala tačno nazivnu faznu struju:

$$Z_B = \frac{U_B}{I_B} = \frac{U_{\mathrm{n}f}}{I_{\mathrm{n}f}}.$$

Ovde je $U_{\mathrm{n}f} = U_{\mathrm{n}}/\sqrt{3}$ nazivni **fazni** napon (sprega Y), a $I_{\mathrm{n}f}$ nazivna fazna struja. Iz definicije nazivne prividne snage $S_{\mathrm{n}} = \sqrt{3}\,U_{\mathrm{n}} I_{\mathrm{n}f}$ izrazimo struju: $I_{\mathrm{n}f} = \dfrac{S_{\mathrm{n}}}{\sqrt{3}\,U_{\mathrm{n}}}$, pa uvrstimo:

$$Z_B = \frac{U_{\mathrm{n}}/\sqrt{3}}{S_{\mathrm{n}}/(\sqrt{3}\,U_{\mathrm{n}})} = \frac{U_{\mathrm{n}}}{\sqrt{3}}\cdot\frac{\sqrt{3}\,U_{\mathrm{n}}}{S_{\mathrm{n}}} = \frac{U_{\mathrm{n}}^2}{S_{\mathrm{n}}}.$$

Zapamti krajnji oblik: **bazna impedansa = kvadrat linijskog nazivnog napona podeljen nazivnom prividnom snagom.** Stvarna (omska) vrednost bilo koje reaktanse date u procentima je onda

$$X = \frac{x\,[\%]}{100}\cdot Z_B .$$

### Mini-lekcija 7: EMS praznog hoda i jednačina naponske ravnoteže

**Elektromotorna sila praznog hoda** $E_0$ je napon koji pobudni fluks indukuje u statorskom namotaju. Indeks "0" podseća: to je napon koji bismo izmerili na otkačenoj mašini (struja $=0$), kada nikakvi padovi napona ne "kvare" sliku. $E_{0f}$ je njena fazna, a $E_{0l} = \sqrt{3}\,E_{0f}$ linijska vrednost.

Kada mašina radi opterećena, između $E_0$ i napona na priključcima $U_f$ stoje padovi napona na reaktansama. Uz zanemaren omski otpor namotaja (dozvoljeno po postavci), naponska ravnoteža generatora sa istaknutim polovima glasi, fazorski:

$$\underline{E}_{0f} = \underline{U}_f + j X_d\,\underline{I}_d + j X_q\,\underline{I}_q .$$

Čitaj: unutrašnja EMS pokriva napon mreže **plus** reaktivne padove napona, i to svaka komponenta struje preko **svoje** reaktanse. Množenje sa $j$ znači "zarotiraj fazor za $+90^\circ$" — pad napona na čistoj reaktansi prednjači struji za četvrt periode. To je i poreklo jednačine: obična Kirhofova naponska jednačina za jednu fazu, u kojoj je pad napona razdvojen po osama zato što d i q komponenta struje "vide" različite reaktanse (mini-lekcija 4).

### Mini-lekcija 8: Fazorski dijagram, ugao opterećenja i projekcije na d i q osu

Fazorski dijagram sinhrone mašine crtamo u koordinatnom sistemu **vezanom za rotor**: **q osa vertikalno naviše, d osa horizontalno udesno**. Ključne činjenice:

- $\underline{E}_{0f}$ leži **tačno na q osi**. Zašto: pobudni fluks je po definiciji duž d ose, a indukovani napon kasni za fluksom koji ga stvara za $90^\circ$ — dakle pada na q osu. Zato je q osa "kažiprst" rotora na dijagramu.
- **Ugao opterećenja** $\delta$ je ugao između $\underline{E}_{0f}$ (q ose) i fazora napona $\underline{U}_f$. Kod generatora $E_0$ prednjači naponu ($\delta > 0$): rotor "vuče" mrežu za sobom.
- Fazor struje $\underline{I}_f$ zaklapa ugao $\varphi$ sa $\underline{U}_f$ (prednjači mu kod kapacitivnog, kasni kod induktivnog faktora snage).

Pošto je dijagram ravanski, svaka fazorska jednačina daje **dve skalarne**: projekciju na q osu i projekciju na d osu. Isto tako, struja se razlaže na $I_q$ (projekcija na q osu) i $I_d$ (projekcija na d osu). Ceo "trik" rešavanja zadataka sa istaknutim polovima je: iz geometrije dijagrama napisati te projekcije, pa iz njih redom izvući $\delta$, $I_d$, $E_{0f}$.

Za projekcije treba znati kako $j$ (rotacija za $+90^\circ$ suprotno kazaljci) preslikava ose: vektor duž $+d$ posle rotacije gleda duž $+q$; vektor duž $+q$ posle rotacije gleda duž $-d$; vektor duž $-d$ prelazi u $-q$. Ovim pravilom ćemo u rešenju, za svaki režim posebno, odrediti kuda "gledaju" padovi $jX_d\underline{I}_d$ i $jX_q\underline{I}_q$.

### Mini-lekcija 9: Trigonometrijska podsetnica — adicione formule

U rešenju se javlja kosinus razlike uglova. Adicione formule glase:

$$\cos(\alpha - \beta) = \cos\alpha\cos\beta + \sin\alpha\sin\beta, \qquad \cos(\alpha + \beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta.$$

Obrati pažnju na znakove: kod **razlike** uglova u razvoju stoji **plus**, kod zbira minus. Ovo naglašavamo jer je upravo tu, kako ćemo videti, u originalnoj zbirci potkrala greška u znaku koja menja konačan rezultat dela a).

## Rešenje, korak po korak

### DEO a) — režim: $P = 2\ \mathrm{MW}$ predato, $Q = 1\ \mathrm{MVAr}$ uzeto iz mreže

### Korak 1: Priroda režima i faktor snage

**Zašto ovaj korak:** Pre bilo kakvog crtanja dijagrama moramo znati da li struja prednjači ili kasni naponu — o tome zavisi ceo oblik dijagrama. Usput nam faktor snage treba za izračunavanje struje.

Generator **uzima** reaktivnu snagu iz mreže, dakle radi **podpobuđen**, a faktor snage je **kapacitivan** — struja prednjači naponu (mini-lekcija 3).

Faktor snage računamo iz trougla snaga (mini-lekcija 2):

$$\cos\varphi = \frac{P}{S} = \frac{P}{\sqrt{P^2 + Q^2}} .$$

Prvo prividna snaga:

$$S = \sqrt{\left(2\cdot 10^6\right)^2 + \left(1\cdot 10^6\right)^2} = \sqrt{4\cdot 10^{12} + 1\cdot 10^{12}} = \sqrt{5}\cdot 10^{6} = 2{,}2361\cdot 10^6\ \mathrm{VA},$$

pa faktor snage:

$$\cos\varphi = \frac{2\cdot 10^6}{2{,}2361\cdot 10^6} = 0{,}8944\ \text{(kapacitivno)} .$$

Odgovarajući ugao je $\varphi = \arccos(0{,}8944) = 26{,}57^\circ$, a $\sin\varphi = \sin 26{,}57^\circ = 0{,}4472$ (trebaće nam u Koraku 6).

**Šta smo dobili:** Struja prednjači naponu za oko $26{,}6^\circ$. Faktor snage $0{,}89$ je pristojan — mašina nije ekstremno podpobuđena.

### Korak 2: Struja generatora u režimu a)

**Zašto ovaj korak:** Struja ulazi u sve naponske padove $X\cdot I$ na dijagramu; bez nje ne možemo dalje.

Iz izraza za trofaznu aktivnu snagu $P = \sqrt{3}\,U_{\mathrm{n}}\,I_f \cos\varphi$ izrazimo struju (delimo obe strane sa $\sqrt{3}\,U_{\mathrm{n}}\cos\varphi$):

$$I_f = \frac{P}{\sqrt{3}\cdot U_{\mathrm{n}}\cdot\cos\varphi} = \frac{2\cdot 10^6}{\sqrt{3}\cdot 6{,}6\cdot 10^3 \cdot 0{,}8944} = \frac{2\cdot 10^6}{10224{,}4} = 195{,}61\ \mathrm{A}.$$

(Ovde indeks "f" znači **fazna** struja statora — kod sprege Y ona je ujedno i linijska. Pazi: $I_f$ **nije** pobudna struja!)

**Šta smo dobili:** Oko $196\ \mathrm{A}$, što je znatno manje od nazivne struje ($I_{\mathrm{n}} = S_{\mathrm{n}}/(\sqrt3 U_{\mathrm{n}}) \approx 437\ \mathrm{A}$) — generator radi na oko $45\ \%$ strujnog opterećenja, sasvim normalno.

### Korak 3: Bazna impedansa

**Zašto ovaj korak:** Reaktanse su date u procentima; da bismo ih koristili u naponskim jednačinama (koje rade sa voltima i amperima), moramo ih pretvoriti u ome preko bazne impedanse (mini-lekcija 6).

$$Z_B = \frac{U_B}{I_B} = \frac{U_{\mathrm{n}f}}{I_{\mathrm{n}f}} = \frac{U_{\mathrm{n}}/\sqrt{3}}{I_{\mathrm{n}f}} = \frac{U_{\mathrm{n}}^2}{S_{\mathrm{n}}} = \frac{\left(6{,}6\cdot 10^3\right)^2}{5\cdot 10^6} = \frac{43{,}56\cdot 10^6}{5\cdot 10^6} = 8{,}712\ \Omega .$$

(Ceo lanac jednakosti izveden je u mini-lekciji 6: fazni napon podeljen faznom strujom, pa se $\sqrt{3}$ pokrati kada struju izrazimo preko $S_{\mathrm{n}}$.)

**Šta smo dobili:** "Merilo" od $8{,}712\ \Omega$ — impedansa koja bi na nazivnom naponu vukla tačno nazivnu struju. Svi procenti iz natpisne pločice se množe ovim brojem.

### Korak 4: Reaktanse u omima i sinhrone reaktanse

**Zašto ovaj korak:** Sastavljamo $X_d$ i $X_q$ koje ulaze u naponsku jednačinu.

Rasipna reaktansa:

$$X_{\gamma} = \frac{x_{\gamma}\,[\%]}{100}\cdot Z_B = \frac{20}{100}\cdot 8{,}712 = 1{,}74\ \Omega .$$

Reaktansa reakcije indukta po uzdužnoj (d) osi:

$$X_{ad} = \frac{x_{ad}\,[\%]}{100}\cdot Z_B = \frac{80}{100}\cdot 8{,}712 = 6{,}97\ \Omega .$$

Reaktansa reakcije indukta po poprečnoj (q) osi:

$$X_{aq} = \frac{x_{aq}\,[\%]}{100}\cdot Z_B = \frac{35}{100}\cdot 8{,}712 = 3{,}05\ \Omega .$$

Sinhrone reaktanse su zbir rasipne i odgovarajuće reakcije indukta (mini-lekcija 5):

$$X_d = X_{\gamma} + X_{ad} = 1{,}74 + 6{,}97 = 8{,}71\ \Omega ,$$
$$X_q = X_{\gamma} + X_{aq} = 1{,}74 + 3{,}05 = 4{,}79\ \Omega .$$

**Šta smo dobili:** $X_d$ je skoro dvostruko veća od $X_q$ — jasan potpis istaknutih polova (po d osi je zazor mali, magnećenje "lako", reaktansa velika). Da je rotor cilindričan, bilo bi $X_d = X_q$ i zadatak bi bio prostiji.

### Korak 5: Fazorski dijagram podpobuđenog generatora i naponske jednačine

**Zašto ovaj korak:** Iz geometrije dijagrama dobijamo sistem skalarnih jednačina iz kog ćemo izvući $\delta$, $I_d$ i $E_{0f}$.

Original ovde daje sliku (fazorski dijagram za kapacitivan faktor snage); opišimo je precizno da je možeš sam nacrtati:

- Nacrtaj **d osu horizontalno udesno** i **q osu vertikalno naviše**.
- $\underline{E}_{0f}$ leži na q osi (naviše).
- $\underline{U}_f$ je u prvom kvadrantu, zarotiran za ugao $\delta$ **udesno** od q ose (tj. $E_{0f}$ prednjači naponu — generator).
- $\underline{I}_f$ prednjači naponu $\underline{U}_f$ za ugao $\varphi$. Pošto je $\varphi > \delta$, struja "prebacuje" q osu i završava **levo** od nje, pod uglom $(\varphi - \delta)$ u odnosu na q osu.
- Komponente struje: $\underline{I}_q$ duž $+q$ (naviše), $\underline{I}_d$ duž $-d$ (**ulevo**). To što $I_d$ gleda u $-d$ smer je ključno: takva komponenta **pomaže** pobudi da magneti mašinu (magnetišuće dejstvo) — baš ono što očekujemo od podpobuđene mašine koja "doteže" magnećenje iz mreže.
- Padovi napona (pravilo rotacije za $j$ iz mini-lekcije 8): $\underline{I}_d$ gleda u $-d$, pa $jX_d\underline{I}_d$ gleda u $-q$ (**nadole**); $\underline{I}_q$ gleda u $+q$, pa $jX_q\underline{I}_q$ gleda u $-d$ (**ulevo**). Kreni od vrha fazora $\underline{U}_f$, dodaj strelicu $jX_q\underline{I}_q$ ulevo pa strelicu $jX_d\underline{I}_d$ nadole — stigao si tačno na vrh $\underline{E}_{0f}$ na q osi.

Dijagram je zapis jednačine naponske ravnoteže (uz zanemaren omski otpor namotaja):

$$\underline{E}_{0f} = \underline{U}_f + jX_d\,\underline{I}_d + jX_q\,\underline{I}_q .$$

Sada projektujemo. Napon $\underline{U}_f$ ima projekciju $U_f\cos\delta$ na q osu i $U_f\sin\delta$ na d osu. Prema opisu smerova: na q osi se sabiraju $E_{0f}$ (rezultat) i to mora biti jednako $U_f\cos\delta$ umanjenom za pad $X_d I_d$ koji gleda nadole; na d osi se projekcija napona $U_f\sin\delta$ tačno poništava sa padom $X_q I_q$ koji gleda ulevo. Tako dobijamo dve skalarne jednačine:

$$U_f\cos\delta = E_{0f} + X_d\,I_d \qquad (1)$$
$$U_f\sin\delta = X_q\,I_q \qquad (2)$$

(u jednačini (1) su $E_{0f}$ i $X_dI_d$ na istoj strani jer pad $jX_d\underline{I}_d$ gleda u $-q$: napon mreže po q osi pokriva i EMS i taj pad — posledica magnetišućeg smera $I_d$).

Komponente struje su projekcije fazora $\underline{I}_f$, koji sa q osom zaklapa ugao $(\varphi - \delta)$:

$$I_d = I_f\,\sin(\varphi - \delta) \qquad (3)$$
$$I_q = I_f\,\cos(\varphi - \delta) \qquad (4)$$

(projekcija na osu uz koju je ugao ide sa kosinusom — to je $I_q$; projekcija na normalnu osu sa sinusom — to je $I_d$).

**Šta smo dobili:** Četiri jednačine sa četiri nepoznate ($\delta$, $I_d$, $I_q$, $E_{0f}$) — sistem je rešiv, i to redom: prvo $\delta$, pa struje, pa EMS.

### Korak 6: Ugao opterećenja $\delta$

**Zašto ovaj korak:** Jednačina (2) sa uvrštenom (4) sadrži samo jednu nepoznatu — ugao $\delta$. Zato nju rešavamo prvu.

Uvrstimo (4) u (2):

$$U_f\sin\delta = X_q\,I_f\,\cos(\varphi - \delta).$$

Razvijemo kosinus razlike adicionom formulom (mini-lekcija 9): $\cos(\varphi-\delta) = \cos\varphi\cos\delta + \sin\varphi\sin\delta$, pa je

$$U_f\sin\delta = X_q I_f\left(\cos\varphi\cos\delta + \sin\varphi\sin\delta\right).$$

> **Napomena o originalu:** U zbirci je kosinus razlike razvijen sa **pogrešnim znakom**, kao $\cos\varphi\cos\delta - \sin\varphi\sin\delta$ (to je u stvari razvoj za $\cos(\varphi+\delta)$). Zbog toga original dobija $\mathrm{tg}\,\delta = 838{,}03/4229{,}6 = 0{,}1981$, tj. $\delta = 11{,}21^\circ$, pa zatim $I_d = 51{,}81\ \mathrm{A}$, $E_{0f} = 3286{,}55\ \mathrm{V}$ i $E_{0l} = 5692{,}47\ \mathrm{V}$. Da su te vrednosti pogrešne lako je proveriti unazad: ako se iz $\delta = 11{,}21^\circ$ i $E_{0f}=3286{,}55\ \mathrm{V}$ rekonstruiše struja i snaga na priključcima, dobija se $P = 1{,}62\ \mathrm{MW}$ umesto zadatih $2\ \mathrm{MW}$ (i $Q = 0{,}92\ \mathrm{MVAr}$ umesto $1\ \mathrm{MVAr}$); takođe, originalne vrednosti ne zadovoljavaju ni sopstvenu jednačinu (2): $U_f\sin 11{,}21^\circ = 740{,}8\ \mathrm{V}$, a $X_q I_q = 4{,}79\cdot 195{,}61\cdot\cos(26{,}57^\circ - 11{,}21^\circ) = 903{,}5\ \mathrm{V}$ — nisu jednaki. Sa ispravnim znakom (kako je izvedeno ovde) rekonstrukcija vraća tačno $P = 2\ \mathrm{MW}$ i $Q = 1\ \mathrm{MVAr}$. U nastavku dajemo ispravan račun, a originalne (pogrešne) brojeve navodimo samo radi poređenja.

Sada rešavamo po $\delta$. Prebacimo član sa $\sin\delta$ sa desne strane na levu (oduzmemo ga od obe strane):

$$U_f\sin\delta - X_q I_f\sin\varphi\,\sin\delta = X_q I_f\cos\varphi\,\cos\delta ,$$

izvučemo $\sin\delta$ kao zajednički činilac:

$$\sin\delta\left(U_f - X_q I_f\sin\varphi\right) = X_q I_f\cos\varphi\,\cos\delta ,$$

pa podelimo obe strane sa $\cos\delta$ i sa zagradom $\left(U_f - X_q I_f\sin\varphi\right)$; koristeći $\dfrac{\sin\delta}{\cos\delta} = \mathrm{tg}\,\delta$:

$$\mathrm{tg}\,\delta = \frac{X_q I_f\cos\varphi}{U_f - X_q I_f\sin\varphi}.$$

Uvrstimo brojeve. Fazni napon je $U_f = \dfrac{6{,}6\cdot 10^3}{\sqrt{3}} = 3810{,}51\ \mathrm{V}$. Dalje:

$$X_q I_f = 4{,}79\cdot 195{,}61 = 936{,}97\ \mathrm{V},$$
$$X_q I_f\cos\varphi = 936{,}97\cdot 0{,}8944 = 838{,}03\ \mathrm{V}, \qquad X_q I_f\sin\varphi = 936{,}97\cdot 0{,}4472 = 419{,}01\ \mathrm{V},$$

$$\mathrm{tg}\,\delta = \frac{838{,}03}{3810{,}51 - 419{,}01} = \frac{838{,}03}{3391{,}50} = 0{,}2471 ,$$

$$\delta = \mathrm{arctg}\,(0{,}2471) = 13{,}88^\circ .$$

**Šta smo dobili:** Ugao opterećenja od oko $14^\circ$ — mala vrednost, daleko od granice stabilnosti, što i priliči mašini opterećenoj sa svega $40\ \%$ nazivne snage. (Original zbog greške u znaku dobija $11{,}21^\circ$.)

### Korak 7: Komponenta struje po d osi

**Zašto ovaj korak:** Za jednačinu (1), iz koje sledi $E_{0f}$, treba nam $I_d$.

Po jednačini (3), sa $\varphi = 26{,}57^\circ$ i $\delta = 13{,}88^\circ$:

$$I_d = I_f\sin(\varphi - \delta) = 195{,}61\cdot\sin\left(26{,}57^\circ - 13{,}88^\circ\right) = 195{,}61\cdot\sin 12{,}69^\circ = 195{,}61\cdot 0{,}2196 = 42{,}96\ \mathrm{A}.$$

Usput, po (4): $I_q = 195{,}61\cdot\cos 12{,}69^\circ = 195{,}61\cdot 0{,}9756 = 190{,}84\ \mathrm{A}$ (koristićemo je u proveri).

**Šta smo dobili:** Oko $43\ \mathrm{A}$ struje deluje magnetišuće duž d ose — to je onaj deo struje kojim mreža "domagnetiše" podpobuđenu mašinu. (Original: $51{,}81\ \mathrm{A}$, posledica pogrešnog $\delta$.)

### Korak 8: EMS praznog hoda — fazna i linijska

**Zašto ovaj korak:** Ovo je i cilj dela a): iz jednačine (1) izražavamo $E_{0f}$.

Iz (1) oduzmemo $X_d I_d$ od obe strane:

$$E_{0f} = U_f\cos\delta - X_d\,I_d .$$

Uvrstimo brojeve:

$$E_{0f} = 3810{,}51\cdot\cos 13{,}88^\circ - 8{,}71\cdot 42{,}96 = 3810{,}51\cdot 0{,}9708 - 374{,}2 = 3699{,}3 - 374{,}2 = 3325{,}1\ \mathrm{V}.$$

Linijska vrednost (sprega Y, mini-lekcija 2):

$$E_{0l} = \sqrt{3}\cdot E_{0f} = \sqrt{3}\cdot 3325{,}1 = 5759{,}3\ \mathrm{V}.$$

**Šta smo dobili:** $E_{0f} = 3325\ \mathrm{V} < U_f = 3810{,}5\ \mathrm{V}$, odnosno linijski $5759\ \mathrm{V} < 6600\ \mathrm{V}$ — unutrašnja EMS je **manja** od napona mreže, tačno kako mora biti kod podpobuđene mašine (mini-lekcija 3). (Original: $E_{0f} = 3286{,}55\ \mathrm{V}$, $E_{0l} = 5692{,}47\ \mathrm{V}$ — kvalitativno ista slika, ali brojčano pogrešno zbog greške u znaku iz Koraka 6.)

### DEO b) — režim: $P = 2\ \mathrm{MW}$, $\cos\varphi = 1$

### Korak 9: Struja generatora pri $\cos\varphi = 1$

**Zašto ovaj korak:** Novi režim — nova struja; sve ostalo ($U_{\mathrm{n}}$, reaktanse) ostaje isto.

$$I_f = \frac{P}{\sqrt{3}\cdot U_{\mathrm{n}}\cdot\cos\varphi} = \frac{2\cdot 10^6}{\sqrt{3}\cdot 6{,}6\cdot 10^3\cdot 1} = \frac{2\cdot 10^6}{11431{,}5} = 174{,}95\ \mathrm{A}.$$

**Šta smo dobili:** Struja je manja nego u režimu a) ($174{,}95\ \mathrm{A}$ prema $195{,}61\ \mathrm{A}$) iako je aktivna snaga ista — jer sada ne teče "višak" struje za prenos reaktivne snage. Pri istoj $P$, struja je najmanja upravo pri $\cos\varphi = 1$.

### Korak 10: Fazorski dijagram za $\cos\varphi = 1$ i nove jednačine

**Zašto ovaj korak:** Geometrija dijagrama se promenila (struja je sada u fazi sa naponom), pa se menjaju i skalarne jednačine — ne smemo slepo prepisati (1)–(4).

Opis dijagrama (original ga daje kao drugu sliku): ose kao ranije (d udesno, q naviše), $\underline{E}_{0f}$ na q osi, $\underline{U}_f$ pod uglom $\delta$ udesno od q ose. Razlika: $\underline{I}_f$ je sada **kolinearna** sa $\underline{U}_f$ (u fazi, jer $\varphi = 0$), dakle i ona je pod uglom $\delta$ udesno od q ose. Njene komponente: $\underline{I}_q$ duž $+q$ naviše, ali $\underline{I}_d$ sada duž $+d$ (**udesno**) — struja po d osi sada deluje **razmagnetišuće** (suprotstavlja se pobudnom fluksu). Padovi: $\underline{I}_d$ gleda u $+d$, pa $jX_d\underline{I}_d$ gleda u $+q$ (**naviše**); $jX_q\underline{I}_q$ i dalje ulevo. Od vrha $\underline{U}_f$ idi naviše za $X_dI_d$, pa ulevo za $X_qI_q$ — stižeš na vrh $\underline{E}_{0f}$, koji je sada **iznad** projekcije napona.

Projekcijom naponske jednačine $\underline{E}_{0f} = \underline{U}_f + jX_d\underline{I}_d + jX_q\underline{I}_q$ na q i d osu (isti postupak kao u Koraku 5, samo sa novim smerom $I_d$):

$$U_f\cos\delta = E_{0f} - X_d\,I_d \qquad (5)$$
$$U_f\sin\delta = X_q\,I_q \qquad (6)$$

(u (5) je sada minus: pad $jX_d\underline{I}_d$ gleda u $+q$, pa EMS mora biti **veća** od q-projekcije napona — razmagnetišuću struju pobuda mora da "pregura").

Struja zaklapa ugao $\delta$ sa q osom (jer je u fazi sa naponom), pa su projekcije:

$$I_d = I_f\,\sin\delta \qquad (7)$$
$$I_q = I_f\,\cos\delta \qquad (8)$$

**Šta smo dobili:** Sistem analogan onom iz dela a), ali prostiji — u njemu figuriše samo ugao $\delta$, bez $\varphi$.

### Korak 11: Ugao opterećenja u režimu b)

**Zašto ovaj korak:** Kao i ranije, jednačina po d osi daje ugao direktno.

Uvrstimo (8) u (6):

$$U_f\sin\delta = X_q\,I_f\cos\delta .$$

Podelimo obe strane sa $U_f\cos\delta$:

$$\mathrm{tg}\,\delta = \frac{X_q\,I_f}{U_f} = \frac{4{,}79\cdot 174{,}95}{6{,}6\cdot 10^3/\sqrt{3}} = \frac{838{,}01}{3810{,}51} = 0{,}2199 ,$$

$$\delta = \mathrm{arctg}\,(0{,}2199) = 12{,}4^\circ .$$

**Šta smo dobili:** Ugao sličan onom iz dela a) — logično, jer je aktivna snaga (glavni "krivac" za ugao opterećenja) ista, a promenila se samo reaktivna komponenta.

### Korak 12: EMS praznog hoda u režimu b)

**Zašto ovaj korak:** Završni cilj dela b).

Iz (5) izrazimo $E_{0f}$ (dodamo $X_dI_d$ obema stranama), pa uvrstimo (7) umesto $I_d$:

$$E_{0f} = U_f\cos\delta + X_d\,I_d = U_f\cos\delta + X_d\,I_f\sin\delta .$$

Uvrstimo brojeve:

$$E_{0f} = \frac{6{,}6\cdot 10^3}{\sqrt{3}}\cdot\cos 12{,}4^\circ + 8{,}71\cdot 174{,}95\cdot\sin 12{,}4^\circ = 3810{,}51\cdot 0{,}9767 + 1523{,}81\cdot 0{,}2147 ,$$

$$E_{0f} = 3721{,}6 + 327{,}2 = 4048{,}84\ \mathrm{V}.$$

Linijska vrednost:

$$E_{0l} = \sqrt{3}\cdot E_{0f} = \sqrt{3}\cdot 4048{,}84 = 7012{,}8\ \mathrm{V}.$$

**Šta smo dobili:** Sada je $E_{0f} = 4049\ \mathrm{V} > U_f = 3810{,}5\ \mathrm{V}$. Da bi prestao da uzima reaktivnu snagu iz mreže, generator je morao da **pojača pobudu** (linijski ekvivalent EMS skočio je sa $5759\ \mathrm{V}$ na $7013\ \mathrm{V}$). Pri $\cos\varphi=1$ EMS je nešto veća od mrežnog napona zato što pobuda sada sama pokriva reaktivnu snagu koju "pojedu" sopstvene reaktanse mašine.

## Česte greške i zamke

1. **Pogrešan znak u adicionoj formuli.** $\cos(\varphi - \delta) = \cos\varphi\cos\delta \boldsymbol{+} \sin\varphi\sin\delta$ — sa plusom! Razvoj sa minusom važi za $\cos(\varphi+\delta)$. Ova greška se potkrala i samoj zbirci u delu a) i pomerila sve rezultate (v. Napomenu o originalu u Koraku 6). Pouka: posle rešavanja uvek vrati brojeve u polaznu jednačinu — mi smo u Proveri smisla pokazali da (2) "štima" tek sa ispravnim znakom.
2. **Mešanje faznih i linijskih veličina.** U naponskim jednačinama (1)–(8) figuriše **fazni** napon $U_f = U_{\mathrm{n}}/\sqrt{3} = 3810{,}5\ \mathrm{V}$, a dobijeno $E_{0f}$ je **fazna** EMS koju na kraju treba pomnožiti sa $\sqrt{3}$ za linijsku vrednost. Ko uvrsti $6600\ \mathrm{V}$ direktno, dobiće besmisleno velike rezultate.
3. **Procenti pravo u formulu.** Reaktansa od "$80\ \%$" nije $80\ \Omega$ niti $0{,}8\ \Omega$ — mora se pomnožiti baznom impedansom: $X_{ad} = 0{,}8\cdot 8{,}712 = 6{,}97\ \Omega$. Takođe, u jednačine idu **sinhrone** reaktanse $X_d = X_{\gamma}+X_{ad}$ i $X_q = X_{\gamma}+X_{aq}$, a ne same reaktanse reakcije indukta ($X_{ad}$, $X_{aq}$) — rasipanje se ne sme zaboraviti.
4. **Prepisivanje jednačina iz pogrešnog režima.** Predznak uz $X_dI_d$ zavisi od smera $I_d$: kod podpobuđene mašine (deo a) $I_d$ je magnetišuća i važi $E_{0f} = U_f\cos\delta - X_dI_d$; pri $\cos\varphi=1$ (deo b) $I_d$ je razmagnetišuća i važi $E_{0f} = U_f\cos\delta + X_dI_d$. Jednačine se **uvek** čitaju sa fazorskog dijagrama za konkretan režim, ne napamet.
5. **Oznaka $I_f$.** Ovde "f" znači *fazna* statorska struja, a ne pobudna (*field*) struja. Pobudna struja se u ovom zadatku uopšte ne računa — o njoj posredno svedoči $E_0$.
6. **Kalkulator u pogrešnom modu.** Uglovi su u stepenima ($26{,}57^\circ$, $13{,}88^\circ$…); ako kalkulator radi u radijanima, svi sinusi i kosinusi će biti pogrešni.

## Rezime rezultata

| Veličina | Oznaka | Režim a) $\left(\cos\varphi = 0{,}8944\ \mathrm{kap.}\right)$ | Režim b) $\left(\cos\varphi = 1\right)$ |
|---|---|---|---|
| Struja generatora | $I_f$ | $195{,}61\ \mathrm{A}$ | $174{,}95\ \mathrm{A}$ |
| Ugao opterećenja | $\delta$ | $13{,}88^\circ$ | $12{,}4^\circ$ |
| EMS praznog hoda, fazna | $E_{0f}$ | $3325{,}1\ \mathrm{V}$ | $4048{,}84\ \mathrm{V}$ |
| EMS praznog hoda, linijska | $E_{0l}$ | $5759{,}3\ \mathrm{V}$ | $7012{,}8\ \mathrm{V}$ |

> **Napomena o originalu (rezime):** za režim a) zbirka usled greške u znaku adicione formule navodi $\delta = 11{,}21^\circ$, $I_d = 51{,}81\ \mathrm{A}$, $E_{0f} = 3286{,}55\ \mathrm{V}$ i $E_{0l} = 5692{,}47\ \mathrm{V}$; ispravne vrednosti su u tabeli (obrazloženje i dokaz u Koraku 6 i Proveri smisla). Svi rezultati režima b) poklapaju se sa zbirkom.

## Provera smisla

**1. Vraćanje rezultata u polazne jednačine (režim a).** Jednačina (2) kaže $U_f\sin\delta = X_qI_q$. Leva strana: $3810{,}51\cdot\sin 13{,}88^\circ = 3810{,}51\cdot 0{,}2399 = 914{,}1\ \mathrm{V}$. Desna strana: $4{,}79\cdot 190{,}84 = 914{,}1\ \mathrm{V}$. Poklapanje je potpuno — sistem je zadovoljen. (Sa originalnim $\delta = 11{,}21^\circ$ dobilo bi se $740{,}8\ \mathrm{V}$ prema $903{,}5\ \mathrm{V}$ — jednačina pada, što je nezavisna potvrda da je u zbirci greška.) Još jača provera: rekonstrukcija snage iz naših $\delta$ i $E_{0f}$ vraća tačno $P = 2\ \mathrm{MW}$ i $Q = 1\ \mathrm{MVAr}$ uzeto — baš zadate vrednosti.

**2. Podpobuđeno/natpobuđeno ponašanje EMS.** U režimu a) (uzima $1\ \mathrm{MVAr}$): $E_{0l} = 5759\ \mathrm{V} < U_{\mathrm{n}} = 6600\ \mathrm{V}$ — podpobuđena mašina ima EMS manju od napona mreže ✓. U režimu b) ($Q=0$): $E_{0l} = 7013\ \mathrm{V} > 6600\ \mathrm{V}$, pobuda pojačana ✓. Trend je fizički ispravan: više pobude → manje uzete (više date) reaktivne snage.

**3. Poređenje sa nazivnim vrednostima i dimenzije.** Nazivna struja je $I_{\mathrm{n}} = \dfrac{S_{\mathrm{n}}}{\sqrt{3}\,U_{\mathrm{n}}} = \dfrac{5\cdot 10^6}{\sqrt{3}\cdot 6600} = 437{,}4\ \mathrm{A}$; naše struje ($195{,}6\ \mathrm{A}$ i $175{,}0\ \mathrm{A}$) su na $44{,}7\ \%$ odnosno $40{,}0\ \%$ nazivne — razumno za mašinu koja daje $2\ \mathrm{MW}$ od mogućih $5\ \mathrm{MVA}$ (odnos $I_b/I_{\mathrm{n}} = 0{,}40 = P/S_{\mathrm{n}}$ tačno, jer je pri $\cos\varphi=1$ struja čisto aktivna) ✓. Dimenziono: svi članovi naponskih jednačina su oblika $\Omega\cdot\mathrm{A} = \mathrm{V}$, saglasno sa $U_f$ i $E_{0f}$ u voltima ✓.
