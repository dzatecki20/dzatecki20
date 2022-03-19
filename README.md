# Specifikacija sofverskih zahtjeva za "Happy Camper" <br/>
**Kolegij:** Programsko inženjerstvo <br/>
**Akademska godina:** 2021/2022 <br/>
**Autor:** Dominik Žatečki <br/>
**Datum:** 19.3.2022. <br/>

## 1. Uvod
#### 1.1 Svrha
U ovom dokumentu biti će specificirani softverski zahtjevi za softer koji će se koristiti za rezervaciju smještajnih jedinica u kampu. Softer su naručili vlasnici obiteljskog kampa, koji bi htjeli tablični kalkulator zamijeniti prikladnim softverom. Ovaj dokument je namijenjen projekt menadžerima, koji će voditi projekt, programerma i dizajnerima, koji će osmisliti i kreirati softver, te testeri, koji će ispitati funkcionalnost sotvera i ukazati na moguće mane istog. <br/>
Struktura dokumenta je utemeljena na predlošku definiranom u dokumentu IEEE 830-1998 Recommended Practice for Software Requirements Specifications.

#### 1.2 Opseg
S obzirom da svaka rezervacija ima mnogo varijabli korištenje prikladnog softvera će naručiteljima uvelike olakšati posao. U cjeniku (tablica 1.) se mogu vidjeti cijene boravka. 
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

Kamp nudi tri vrste smještaja: mobilnu kućicu, kamp kućicu i šator. Cijena za svaku vrstu smještaja se različito obračunava. Za kamp prikolicu
