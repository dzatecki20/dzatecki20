# Specifikacija sofverskih zahtjeva za *Happy Camper* <br/> <br/>


**Kolegij:** Programsko inženjerstvo <br/>
**Akademska godina:** 2021/2022 <br/>
**Autor:** Dominik Žatečki <br/>
**Datum:** 19.3.2022. <br/>


## 1 Uvod <br/><br/>
#### 1.1 Svrha
U ovom dokumentu biti će specificirani softverski zahtjevi za softer koji će se koristiti za rezervaciju smještajnih jedinica u kampu. Softer su naručili vlasnici obiteljskog kampa, koji bi htjeli tablični kalkulator zamijeniti prikladnim softverom. Ovaj dokument je namijenjen projekt menadžerima, koji će voditi projekt, programerma i dizajnerima, koji će osmisliti i kreirati softver, te testeri, koji će ispitati funkcionalnost sotvera i ukazati na moguće mane istog. <br/>
Struktura dokumenta je utemeljena na predlošku definiranom u dokumentu IEEE 830-1998 Recommended Practice for Software Requirements Specifications.

#### 1.2 Opseg
S obzirom da svaka rezervacija ima mnogo varijabli korištenje prikladnog softvera će naručiteljima uvelike olakšati posao. U cjeniku (tablica 1.) se mogu vidjeti cijene boravka. <br/> <br/>
Tablica 1. - sve cijene su izražene u kunama po danu, kn/dan
|  |Sezona|Izvan sezone|
| :---: | :---: | :---: |
|Vrsta smještaja|  | |
|Kamp prikolica|150|80|
|Šator|50|35|
|Mobilna kućica|900|500|
|Gost|  |  |
|Odrasli|60|40|
|Djeca 5-12|30|20|
|Djeca 0-4|0|50|
<br/>
Kamp nudi tri vrste smještaja: mobilnu kućicu, kamp kućicu i šator. Cijena za svaku vrstu smještaja se različito obračunava. Za kamp prikolicu i šator gost plaća cijenu po danu za odabranu vrstu smještaja + cijenu gosta po danu ovisno o dobi. U slučaju da se gost odluči za mobilnu kučicu plaćati će samo punu cijenu kućice, bez obzira na broj gostiju. Kapacitet kućice je šest osoba, dok šator i kamp prikolica imaju noegraničen kapacitet. S obzirom na datum smještaja softver će se prebacivati između račuanja cijena u sezoni i računanja cijena izvan sezona. Također treba naglasiti da gosti koji su prije ostajali u kampu dobivaju pet posto popusta na cijenu smještaja. Prikazano na konkternom primjeru: Odrasla osoba koja sa osmogodišnjim djetetom u sezoni rezervira šator, te prvi put ostaje u kampu, će plaćati 140kn/dan, to jest 50kn/dan+60kn/dan+30kn/dan.<br/><br/>
Vlasnici kampa su do sada koristili tablični kalkulator, što je sa sobom nosilo sljedeće poteškoće: ahtjevna procedura postavljanja tabličnog kalkulatora za različite vrste smještajnih jedinica ovisno o tipu, broju osoba i sezoni, nedostatak automatiziranih izvještaja, složena prilagodba u slučaju promjena i sl.<br/><br/>
Uloga softvera *Happy Camper* bi bila olakšavanje procesa vođenja zapisa o rezervacijama. Softver bi osim računanja cijena, pamtio prošle rezervacije, prikazivao trenutnu zauzetost kampa, te računao prihod dobiven od noćenja. Softver ne bi računao troškove održavanja, niti potrošnju struje, vode i sličnih resursa na parcelama<br/><br/>

#### 1.3 Defincije, akronimi i skraćenice
**Sezona** - razdoblje od 1. lipnja do 30. kolovoza

#### 1.4 Reference
1. 830-1998 - IEEE Recommended Practice for Software Requirements Specifications.” IEEE, 1998. [Online]. Dostupno na: http://ieeexplore.ieee.org/servlet/opac?punumber=5841
2. Dokument opisa problemske domene

#### 1.5 Struktura dokumenta

## 2 Općeniti opis <br/><br/>
#### 2.1 Perspektiva proizvoda <br/><br/>
#### 2.2 Funkcije proizvoda <br/><br/>
#### 2.3 Karakteristike korisnika <br/><br/>
#### 2.4 Ograničenja <br/><br/>
#### 2.5 Pretpostavke i ovisnosti <br/><br/>
#### 2.1 Ostalo <br/><br/>
## 3 Specifični funkcionalni zahtjevi <br/><br/>
#### 3.1 Dinamika realizacije zahtjeva <br/><br/>
## 4 Nefunkcionalni zahtjevi <br/><br/>
#### 4.1 Izgled softvera <br/><br/>
#### 4.2 Upotrebljivost softvera <br/><br/>
#### 4.3 Preformanse softvera <br/><br/>
#### 4.4 Izvođenje softvera i okruženje <br/><br/>
#### 4.5 Sigurnost i privatnost <br/><br/>
#### 4.6 Ostalo <br/><br/>
## 5 Skice zaslona <br/><br/>

