# Specifikacija sofverskih zahtjeva za Happy Camper <br/> <br/>


**Kolegij:** Programsko inženjerstvo <br/>
**Akademska godina:** 2021/2022 <br/>
**Autor:** Dominik Žatečki <br/>
**Datum:** 19.3.2022. <br/>


## 1 Uvod <br/><br/>
#### 1.1 Svrha
U ovom dokumentu biti će specificirani softverski zahtjevi za softer koji će se koristiti za rezervaciju smještajnih jedinica u kampu. Softer su naručili vlasnici obiteljskog kampa, koji bi htjeli tablični kalkulator zamijeniti prikladnim softverom. Ovaj dokument je namijenjen projekt menadžerima, koji će voditi projekt, programerma i dizajnerima, koji će osmisliti i kreirati softver, te testeri, koji će ispitati funkcionalnost sotvera i ukazati na moguće mane istog. <br/>
Struktura dokumenta je utemeljena na predlošku definiranom u dokumentu IEEE 830-1998 Recommended Practice for Software Requirements Specifications.<br/>

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
Vlasnici kampa su do sada koristili tablični kalkulator, što je sa sobom nosilo sljedeće poteškoće: zahtjevna procedura postavljanja tabličnog kalkulatora za različite vrste smještajnih jedinica ovisno o tipu, broju osoba i sezoni, nedostatak automatiziranih izvještaja, složena prilagodba u slučaju promjena.<br/><br/>
Uloga softvera Happy Camper bi bila olakšavanje procesa vođenja zapisa o rezervacijama. Softver bi osim računanja cijena, pamtio prošle rezervacije, prikazivao trenutnu zauzetost kampa, te računao prihod dobiven od noćenja. Softver ne bi računao troškove održavanja, niti potrošnju struje, vode i sličnih resursa na parcelama<br/><br/>

#### 1.3 Defincije, akronimi i skraćenice
**Sezona** - razdoblje od 1. lipnja do 30. kolovoza
**Jedinica** - jedan smještaj, može biti šator, kamp prikolica ili mobilna kućica<br/>

#### 1.4 Reference
1. 830-1998 - IEEE Recommended Practice for Software Requirements Specifications.” IEEE, 1998. [Online]. Dostupno na: http://ieeexplore.ieee.org/servlet/opac?punumber=5841
2. Dokument opisa problemske domene

#### 1.5 Struktura dokumenta

## 2 Općeniti opis <br/><br/>
#### 2.1 Perspektiva proizvoda <br/><br/>
Happy Camper će biti samostalno sofversko rješenje, koje zamjenjuje postojeći sustav s tabličnim kalkulatorom. Softversko rješnenje i baza podataka bi se nalazili na klijentovom računalu, pošto će samo oni moći pristupati podatcima. Happy Camper bi se koristio klijetovim hardverom za pohranu podataka, no ne bi se koristio komuikacijskim tehnologijama. Time bi se omogućilo da aplikacija funkcionira i bez interneta. Predviđeno je da bilo kakva uporaba takvih resursa bude odrađena od strane operacijskog sustava.

#### 2.2 Funkcije proizvoda <br/><br/>
Naručitelji softvera žele sljedeće funkcije:
- Ograničenje pristupa softveru
- Mogućnost samostalnog unosa podataka o smještaju: vrsta smještaja, broj jedinica, kapacitet
- Mogućnost samostalne izmjene podataka o smještaju: vrsta smještaja, broj jedinica, kapacitet
- Definiranje cijena unutar i izvan sezone
- Obračunavanje cijene s obzirom na vrstu jedinice, broj gostiju i termin
- Obračunavanje dodatog popusta na goste koji su koristili usluge kampa 
- Unos rezervacija
- Pretraživanje slobodnih jedinica po terminu i kapacitetu
- Popis svih jedinca koje su trenutno, u trenutku pretraživanja rezervirane
- Popis svih jedinca koje su trenutno, u trenutku pretraživanja slobodne
- Popis svih gostiju koji su trenutno u kampu
- Statitstike po vrsti jedinica:
  - prosječan broj gostiju tokom boravka
  - popunjenost tokom godine
  - popunjenost tokom sezone 
  - ostvareni prihod tokom godine

#### 2.3 Karakteristike korisnika <br/><br/>
Korisnici i naručitelji softvera je bračni par srednjih godina, s područja srednje Dalmacije. Postoji samo jedna korisnička uloga, _vlasnik kampa_. Svaki od vlasnika će imati svoje podatke za prijavu, kako bi se u slučaju promjene podataka u aplikaciji moglo vidjeti tko ih je napravio. Vlasnici su srednje informatički pismeni.

#### 2.4 Ograničenja <br/><br/>
Pošto se u aplikaciji nalaze privatni podatci gostiju, važno je da ti poadtci budu sigurni, što će biti postignuto GDPR odredbama. Radi sigurnosti svaki od vlasnika će imati svoje korisničke podatke. Pošto će se podatci spremati na klijentov hardver, implementirati će se mjere zaštite podataka. Naurčitelji se nisu izjasnili oko nikakvih posebnih zahtjeva oko alata, programskog jezika ili posebnih metoda za izradu softvera. Preptostavlja se da naurčitelji imaju standardno računalo na kojem će izvoditi aplikaciju.<br/><br/>

#### 2.5 Pretpostavke i ovisnosti <br/><br/>
Podatke o broju jedinica, vrsti jedinica, maksmialnom kapacitetu jedinica i cijenama vlasnici mogu mijenjati bilo kad tokom godine. Promjene podataka navedenih u prošloj ne bi trebale utjecati na goste koji se trenutno nalaze u kampu.<br/><br/>

#### 2.6 Ostalo <br/><br/>
Nema potrebe za elaboracijom dodatnih aspekata.<br/><br/>

## 3 Specifični funkcionalni zahtjevi <br/><br/>
#### 3.1 Dinamika realizacije zahtjeva <br/><br/>

|Identifikator|Feature/login|
| :---: |:--- |
|Zahtjev| Sustav koji omogućava pristup samo osobama s ispravnim korisničkim podatcima|
|Obrazloženje|U aplikaciji se nalaze povjerljivi osobni podatci gostiju, te podatci o kampu i cijenama. Pristup takvim podatcima trebaju imati samo ovlaštene osobe. |
|Način provjere|Pokušaj pristupa aplikaciji s ispravnim korisničkim podatcima rezultira ulaskom u aplikaciju, dok s neispravnim rezultira zabranom ulaska.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene|<br/><br/>

|Identifikator|Feature/manual_data_import|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručni unos podataka o kampu i cijena|
|Obrazloženje|Vlasnici podatke o rezervacijama zapisuju u aplikaciju u svrhu praćenja račuanja cijena i praćenja popunjenosti kampa.|
|Način provjere|Uneseni podatci moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/manual_data_update|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručne izmjene unešenih podataka|
|Obrazloženje|Vlasnici žele moći po želji izmjenjivati podatke o kampu i cijenama.|
|Način provjere|Uneseni promjene podataka moraju biti vidljive u sustavu.|
|Prioritet (1-5)|3|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/raservation_data_import|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti unos rezervacije u bazu podataka.|
|Obrazloženje|Vlasnici žele moći pratiti rezervacije.|
|Način provjere|Uneseni podatci o rezervaciji moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|2|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/return_discount|
| :---: |:--- |
|Zahtjev| Sustav će automatkski na cijenu gostiju koji ponovno ostaju u kampu obračunavati pet posto popusta.|
|Obrazloženje|Vlasnici gostima koji ponovno ostaju u kmapu daju dodatni popust.|
|Način provjere|Gost koji nije prvi put u kampu, to jest već ima zapis o prijašnjim rezevacijama u bazi podataka, dobiva popust. Gost koji se prvi put upisuje u bazu podataka, to jest prvi put ostaje u kampu, ne dobiva takav popust.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/return_discount|
| :---: |:--- |
|Zahtjev| Sustav će automatkski na cijenu gostiju koji ponovno ostaju u kampu obračunavati pet posto popusta.|
|Obrazloženje|Vlasnici gostima koji ponovno ostaju u kmapu daju dodatni popust.|
|Način provjere|Gost koji nije prvi put u kampu, to jest već ima zapis o prijašnjim rezevacijama u bazi podataka, dobiva popust. Gost koji se prvi put upisuje u bazu podataka, to jest prvi put ostaje u kampu, ne dobiva takav popust.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

## 4 Nefunkcionalni zahtjevi <br/><br/>
#### 4.1 Izgled softvera <br/><br/>

#### 4.2 Upotrebljivost softvera <br/><br/>

#### 4.3 Preformanse softvera <br/><br/>

#### 4.4 Izvođenje softvera i okruženje <br/><br/>

#### 4.5 Sigurnost i privatnost <br/><br/>

#### 4.6 Ostalo <br/><br/>

## 5 Skice zaslona <br/><br/>

