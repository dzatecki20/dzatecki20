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

|Identifikator|Feature/login|
| :---: |:--- |
|Zahtjev| Sustav koji omogućava pristup samo osobama s ispravnim korisničkim podatcima|
|Obrazloženje|U aplikaciji se nalaze povjerljivi osobni podatci gostiju, te podatci o kampu i cijenama. Pristup takvim podatcima trebaju imati samo ovlaštene osobe. |
|Način provjere|Pokušaj pristupa aplikaciji s ispravnim korisničkim podatcima rezultira ulaskom u aplikaciju, dok s neispravnim rezultira zabranom ulaska.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene|<br/><br/>

|Identifikator|Feature/unit_data_import|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručni unos podataka o kampu|
|Obrazloženje|Naručitelji podatke o rezervacijama zapisuju u aplikaciju u svrhu praćenja račuanja cijena i praćenja popunjenosti kampa.|
|Način provjere|Uneseni podatci moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/unit_data_update|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručne izmjene unešenih podataka o kampu|
|Obrazloženje|Naručitelji žele moći po želji izmjenjivati podatke o kampu.|
|Način provjere|Unesene promjene podataka moraju biti vidljive u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/prices_import|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručni unos cjenika|
|Obrazloženje|Naručitelji žele moći unositi podatke o cijenama usluga.|
|Način provjere|Uneseni podatci moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/prices_update|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti ručne izmjene cjenika|
|Obrazloženje|Naručitelji žele moći po želji izmjenjivati cjenik.|
|Način provjere|Unesene promjene podataka moraju biti vidljive u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/raservation_data_import|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti unos rezervacije u bazu podataka.|
|Obrazloženje|naručitelji žele moći pratiti podatke o rezervacijama.|
|Način provjere|Uneseni podatci o rezervaciji moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/raservation_data_update|
| :---: |:--- |
|Zahtjev| Sustav će omogućiti unos izmjene podataka o rezervacijama.|
|Obrazloženje|naručitelji žele moći po potrebi mijenjati podatke o rezervacijama.|
|Način provjere|Unesene promjene u podatcima o rezervaciji moraju biti vidljivi u sustavu.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/return_discount|
| :---: |:--- |
|Zahtjev| Sustav će automatkski na cijenu ostanka u kampu gostiju koji ponovno ostaju u kampu obračunavati pet posto popusta.|
|Obrazloženje|Naručiitelji gostima koji ponovno ostaju u kmapu daju dodatni popust.|
|Način provjere|Gost koji nije prvi put u kampu, to jest već ima zapis o prijašnjim rezevacijama u bazi podataka, dobiva popust. Gost koji se prvi put upisuje u bazu podataka, to jest prvi put ostaje u kampu, ne dobiva takav popust.|
|Prioritet (1-5)|3|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/price_calculation|
| :---: |:--- |
|Zahtjev| Sustav će automatkski račuanti cijenu ostanka u kampu.|
|Obrazloženje|Naručitelji žele da sustav automatski računa cijenu ostanka u kampu.|
|Način provjere|Gost koji nije prvi put u kampu, to jest već ima zapis o prijašnjim rezevacijama u bazi podataka, dobiva popust. Gost koji se prvi put upisuje u bazu podataka, to jest prvi put ostaje u kampu, ne dobiva takav popust.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/reservation_calendar|
| :---: |:--- |
|Zahtjev| Sustav će u kalendaru prikazivati unešene rezervacije, svaka jedinica ima svoj kalendar.|
|Obrazloženje|Kalendar će korisnicima omogućiti lakše snalaženje u rezervacijama.|
|Način provjere|Nakon uspješnog unosa rezervacije provjerava se prikazuje li se termin ispravno u kalendaru.|
|Prioritet (1-5)|3|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/free_unit_search|
| :---: |:--- |
|Zahtjev| Sustav će omogučiti pretraživanje slobodnih jedinica s obzirom na odbrani termin.|
|Obrazloženje|Naručitelji žele moći vidjeti koje su jedinice slobodne u odabranom terminu. Termin se bira odabirom početnog i završnog datuma. Da bi jedinica bila slobodna mora biti nerezervirana svaki dan između zadanog početnog i završnog datuma termina.|
|Način provjere|Nakon unosa par rezervacija i željenog termina pretraživanja pokreće se pretraživanje i provjerava se navode li se zauzete jedince kao slobodne.|
|Prioritet (1-5)|4|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>


|Identifikator|Feature/current_free_unit_search|
| :---: |:--- |
|Zahtjev| Sustav će omogučiti pretraživanje slobodnih jedinica u trenutku pretrage.|
|Obrazloženje|Naručitelji žele moći vidjeti koje su jedinice slobodne u ternutku pretrage, to jest koje jedinice su trenutno slobodne.|
|Način provjere|Nakon unosa par rezervacija pokreće se pretraživanje i provjerava se navode li se zauzete jedince kao slobodne.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/current_occupied_unit_search|
| :---: |:--- |
|Zahtjev| Sustav će omogučiti pretraživanje zauzetih jedinica u trenutku pretrage.|
|Obrazloženje|Naručitelji žele moći vidjeti koje su jedinice zauzete u ternutku pretrage, to jest koje jedinice su trenutno nisu slobodne.|
|Način provjere|Nakon unosa par rezervacija pokreće se pretraživanje i provjerava se navode li se slobodne jedince kao zauzete.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>


|Identifikator|Feature/income_through_year|
| :---: |:--- |
|Zahtjev| Sustav će prikazivati prihod ostvaren u tekućoj godini.|
|Obrazloženje|Naručitelji žele moći vidjeti sumu prihoda ostvarenih u tekućoj godini, prihodu tekuće godine doprinose samo rezervacije čiji početak termina se nalazi u tekućoj godini.|
|Način provjere|Nakon unosa par rezervacija pokreće se funkcija i provjera se odgovaraju li prikazanano stanje previđenom stanju.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/current_guests_list|
| :---: |:--- |
|Zahtjev| Sustav će prikazivati listu trenutnih gostiju i u kojoj jedinici se nalaze.|
|Obrazloženje|Naručitelji žele moći vidjeti listu gostiju koji se trenutno nalaze u kampu i u kojoj jendici se nalaze.|
|Način provjere|Nakon unosa par rezervacija pokreće se funkcija i provjera se prikazuje li sustav ispravne podatke.|
|Prioritet (1-5)|1|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/occupancy_year|
| :---: |:--- |
|Zahtjev| Sustav će popunjenost u tekućoj godini.|
|Obrazloženje|Naručitelji žele moći vidjeti koliko je gostiju ostajalo u kojoj vrsti jedinica, te koliko dana u godini je određena vrsta jedinica bila zauzeta.|
|Način provjere|Nakon unosa par rezervacija pokreće se funkcija i provjera se odgovaraju li prikazanano stanje previđenom stanju.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

|Identifikator|Feature/occupancy_season|
| :---: |:--- |
|Zahtjev| Sustav će prikazivati prihod ostvaren u tekućoj godini.|
|Obrazloženje|Naručitelji žele moći vidjeti koliko je gostiju ostajalo u kojoj vrsti jedinica, te koliko dana u sezoni je određena vrsta jedinica bila zauzeta.|
|Način provjere|Nakon unosa par rezervacija pokreće se funkcija i provjera se odgovaraju li prikazanano stanje previđenom stanju.|
|Prioritet (1-5)|5|
|Izvor|Korisnički zahtjevi definirani u Dokumentu opisa problemske domene.|<br/><br/>

#### 3.1 Dinamika realizacije zahtjeva <br/><br/>

U početnoj verziji sofvera biti će implementirane samo najprioritetnije funkcije: <br/>

- Feature/login
- Feature/unit_data_import
- Feature/unit_data_update
- Feature/prices_data_import
- Feature/prices_data_update
- Feature/reservation_data_import
- Feature/reservation_data_update
- Feature/price_calculation
- Feature/current_guest_list  <br/>

U budućim verzijama je planirana implementacija slijedećih funckija: <br/>

- Feature/return_discount
- Feature/reservation_calendar
- Feature/free_unit_search
- Feature/current_free_unit_search
- Feature/current_occupied_unit_search
- Feature/income_through_year
- Feature/occupancy_year
- Feature/occupancy_season
<br/>

## 4 Nefunkcionalni zahtjevi <br/><br/>
#### 4.1 Izgled softvera <br/><br/>

Feature_01 - Sustav će imati grafičko sučelje za interakciju s korisnikom.<br/>
Feature_02 - Sustav će pratiti formalan/korporativni stil grafičkog sučelja.

#### 4.2 Upotrebljivost softvera <br/><br/>

Feature_03 - Sustav će imati mehanizme za smanjenje broju grešaka pri unosu zapisa.

#### 4.3 Preformanse softvera <br/><br/>

Feature_04 - Sustav će biti dostupan 24 sata na dan 365 dana u godini.<br/>
Feature_05 - Sustav će imati preciznost za decimalne brojeve od 2 decimalna mjesta.

#### 4.4 Izvođenje softvera i okruženje <br/><br/>

Feature_06 - Sustav će biti raditi na računalima s instaliranim Windows-om 10 ili novijom verzijom.

#### 4.5 Sigurnost i privatnost <br/><br/>

Feature_07 - Sustav će omogućiti pristup samo osobama s ispravnim korsničkim podatcima.<br/>
Feature_08 - Sustav će upotrebljavati podatke o gostima i kampu u skladu sa odredbama GDPR-a.

#### 4.6 Ostalo <br/><br/>

Nisu pronađeni dodatni nefunkcionalni zahtjevi.<br/>

## 5 Skice zaslona <br/><br/>
#### 5.1 Skica zaslona za Prijavu u sustav
![Login screen](https://user-images.githubusercontent.com/100710102/159169839-76f594df-c20c-4ea5-87a3-dee771746f24.png)

#### 5.2 Skica zaslona za Unos podataka o jedinici
![Unit_import](https://user-images.githubusercontent.com/100710102/159170601-13e9d78f-12eb-4714-934b-dd0670d9affb.png)

#### 5.3 Skica zaslona za Ispis trenutnih gostiju
![Current_guest_list](https://user-images.githubusercontent.com/100710102/159171101-f8712727-e237-4ee2-bda0-6cb8fa9a96d2.png)

