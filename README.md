# Opstanak znanja u slučaju kataklizme

## Uvod

Agent bazirano modeliranje opstanka znanja u slučaju kataklizme.

**Pitanja** na koja ćemo dobiti odgovor nakon simulacije:

 - Da li će znanje **preživjeti**  kataklizmu?
 - Ako će se znanje **oporaviti** u kojem će to trenutku biti?
 - U kojem odnosu će biti **nivo znanja** kada populacija dosegne broj onom u trenutku **kataklizme**?

## Agenti

Pokretni agenti: **Osoba**
Nepokretni agenti: **Edukacijski centar** 

### Osoba

Agent predstavlja osobu koja je nasumično kreirana i koja shodno vrijednostima atributa teži ili ne teži ka edukacionim centrima i unaprijeđenju znanja.

**Funkcije** koje se vežu za osobe su:

- Kreiranje novih generacija
- Kretanje - nasumično ili usmjereno edukacionom centru
- Umiranje
- Starenje

#### Atributi

| **Naziv atributa**                     | Vrijednost    |
| -------------------------------------- | ------------- |
| Starost                                | od 18 do 73   |
| Sposobnost učenja                      | od 40 do 100  |
| Želja za učenjem                       | od 40 do 100  |
| Nivo trenutnog znanja                  | od 40 do 100  |
| Broj provedenih godina u centru znanja | 3 ili 5 ili 8 |

### Edukacijski centar

Nepokretni agent, edukacijski centar, je mjesto gdje agenti uvećavaju svoje znanje u zavisnosti od njihovih sposobnosti i nivoa znanja koji centar pruža na osnovu **formule** za rast znanja.

#### Atributi

| Naziv atributa | Vrijednost   |
| ------------------ | ------------ |
| Nivo znanja        | od 40 do 100 |
| Radijus            | 2            |

## Edukacija osoba

Osobe se kreću prema edukacijskom centru u odnosu na promjenjivi parametar **minimalne želje** za učenjem koja služi kao prag da li će osoba biti u potrazi za edukacijskim centrom ili ne.

Osobe provode određeni period u centru gdje **jedan tik** predstavlja **jedan mjesec.** U odnosu na slučajnu vrijednost u centru će ostati **tri**, **pet** ili **osam** godina.

<img src="./images/LegendaOsoba.png" alt="LegendaOsoba" style="zoom:50%;" />

### Rast znanja osobe

Rast znanja u slučaju da se osoba nalazi u edukacionom centru izračunava se na osnovu empirijski dobijene formule.

#### Varijable

- $K_F$ – Faktor sticanja znanja
  - $P_{LA}$ – Sposobnost učenja osobe
  - $P_{LW}$ – Volja za učenjem osobe
- $E_K$ – Nivo znanja edukacionog centra
- $E_{Ky}$ – Dostupno znanje u centru po godini
- $P_{Ky}$ – Stečeno znanje osobe po godini

#### Formule

<img src="./images/Formule.png" alt="Formule" style="zoom:50%;" />

<img src="./images/FormulaGraf.png" alt="FormulaGraf" style="zoom:50%;" />

## Kataklizma

Kataklizma predstavlja:

- **Uništenje određenog broja populacije** (edukovanih ili needukovanih)
- **Unišenje** **određenog broja edukacionih centara**
- **Smanjenje nivoa znanja centrima koji su** **opstali**

<img src="./images/PrijePoslijeKataklizme.png" alt="PrijePoslijeKataklizme" style="zoom:50%;" />

## Program

NetLogo je softver korišten za izradu agent baziranog modela.

Dijelovi programa:

- Glavni panel
- Slider-i
- Dugmad za pokretanje akcija
- Izvještaji

<img src="./images/Program.png" alt="Program" style="zoom:50%;" />

## Rezultati

Tri slučaja – **najgori, najbolji i prosječni**

Promjenjivi parametar je **smanjenja nivoa znanja edukacionog centra** (%) nakon kataklizme

### Globalne **postavke**

Parametri **populacije**:

| **Parametar**                          | Vrijednost | Opis                                                         |
| -------------------------------------- | ---------- | ------------------------------------------------------------ |
| Inicijalna populacija                  | 850        | :heavy_minus_sign:                                           |
| Inicijalni broj edukacionih centara    | 20         | :heavy_minus_sign:                                           |
| Minimalna volja za priključenje centru | 25         | Obično ljudi i sa manjom voljom žele da steknu određeni nivo akademskog znanja |

----

Parametri za **kataklizmu**:

| **Parametar**                 | **Vrijednost** | Opis                                            |
| ----------------------------- | -------------- | ----------------------------------------------- |
| Uništenje neobrazovanih ljudi | 50%            | Lakše se snalaze u situacijama preživljavanja   |
| Uništenje obrazovanih ljudi   | 90%            | Teže se snalaze u situacijama preživljavanja    |
| Uništenje edukacionih centara | 70%            | Djelomično proporcionalno broju uništenih ljudi |

### Najlošiji slučaj - Znanje nije preživjelo

**SMANJENJE ZNANJA OPSTALIH EDUKACIJSKIH CENTARA – 70%**

| **Vrijednost**                                     | U trenutku kataklizme | **Poslije** 180 godina |
| -------------------------------------------------- | --------------------- | ---------------------- |
| Populacija                                         | 1525                  | 1534                   |
| Osobe sa nivoom znanja preko 55                    | 46                    | 5                      |
| Nivo prosječnog znanja osoba starijih od 30 godina | 30.7                  | 24.1                   |

<img src="./images/NajlosijiSlucaj.png" alt="NajlosijiSlucaj" style="zoom:50%;" />

### Najbolji slučaj - Znanje je preživjelo

**SMANJENJE ZNANJA OPSTALIH EDUKACIJSKIH CENTARA – 45%**

| **Vrijednost**                                     | U trenutku kataklizme | **Poslije** 180 godina |
| -------------------------------------------------- | --------------------- | ---------------------- |
| Populacija                                         | 1510                  | 1500                   |
| Osobe sa nivoom znanja preko 55                    | 80                    | 208                    |
| Nivo prosječnog znanja osoba starijih id 30 godina | 34.6                  | 35.2                   |

<img src="./images/NajboljiSlucaj.png" alt="NajboljiSlucaj" style="zoom:50%;" />

### Prosječni slučaj  - Znanje je obnovljeno

**SMANJENJE ZNANJA OPSTALIH EDUKACIJSKIH CENTARA – 60%**

| **Vrijednost**                                     | U trenutku kataklizme | **Poslije** 180 godina |
| -------------------------------------------------- | --------------------- | ---------------------- |
| Populacija                                         | 1530                  | 3220                   |
| Osobe sa nivoom znanja preko 55                    | 123                   | 128                    |
| Nivo prosječnog znanja osoba starijih od 30 godina | 32                    | 29.45                  |

<img src="./images/ProsjecniSlucaj.png" alt="ProsjecniSlucaj" style="zoom:50%;" />

