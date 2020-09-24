# PIFU-IMS

## Spesifikasjon
**Versjon:** 1.3

## Innhold
1. [Innledning](#innledning)
2. [Informasjonsmodell](#informasjonsmodell)
  * 2.1. [Enterpriseobjektet](#enterpriseobjektet)
  * 2.2. [Personobjekter](#personobjekter)
    * 2.2.1. [Utvidelser for personobjekter](#poutvidelser)
      * 2.2.1.1. [Vokabular for utvidelser på personobjekt](#poutvidelservokab)
  * 2.3. [Gruppeobjekter - organisasjoner, organisasjonsenheter og grupper](#gruppeobjekter)
    * 2.3.1. [Utvidelser på organisasjon og organisasjonsenhet](#goutvidelser1)
      * 2.3.1.1. [Vokabular for utvidelser på organisasjon og organisasjonsenhet](#goutvidelser1vokab)
    * 2.3.2. [Utvidelser på basisgruppe og kontaktlærergruppe](#goutvidelser2)
    * 2.3.3. [Utvidelser på trinn, utdanningsprogram, programområde, fag og undervisningsgruppe](#goutvidelser3)
	    * 2.3.3.1. [Vokabularer for utvidelser på trinn, utdanningsprogram, programområde, fag og undervisningsgruppe](#goutvidelser3vokab)
  * 2.4. [Medlemskapsobjekter](#medlemskapsobjekter)
    * 2.4.1. [Utvidelser på rolleobjektet](#moutvidelser)
  * 2.5. [Felles informasjonselementer](#finformasjonselementer)

<a name="innledning"/>

## 1. Innledning

Dette dokumentet beskriver uttrekket til/fra det skoleadministrative systemet til/fra andre systemer som IdM-systemer, LMSer og andre. Uttrekket bygger på NS 4170:2008 Personrelatert informasjonsflyt i utdanning (PIFU) og IMS Enterprise 1.1.

<a name="informasjonsmodell"/>

## 2. Informasjonsmodell

Som grunnlag for denne informasjonsmodellen benyttes: 

*	NS 4170:2008 Personrelatert informasjonsflyt i utdanning (PIFU) <https://standard.iktsenteret.no/pifu>
*	PIFU-FK Profil
*	IMS Enterprise 1.1 <http://www.imsglobal.org/enterprise/>

PIFU-standarden benyttes som referansemodell for å avbilde informasjonsmengden beskrevet i PIFU-FK, mens IMS Enterprise 1.1 benyttes som det grunnleggende overføringsformatet.

I PIFU-standarden er det beskrevet en eksempelavbilding av PIFU i IMS Enterprise som strukturelt dekker behovet i denne spesifikasjonen og benyttes som mal. Vokabularer og verdier blir ikke dekt av eksemplet i PIFU-standarden så dette hentes fra PIFU-FK med noen få tillegg og endringer.

IMS Enterprise Information Model 1.1 gjelder generelt og kalles fra nå av IMS-E. I kapitlene under beskrives denne strukturen overordnet, men forklaring og typer er nærmere beskrevet i grunnlagsdokumentet. Fokuset i dette dokumentet er hva som skal være med i dette uttrekket, utvidelsene som er gjort og utdypninger i forhold til den generelle informasjonsmodellen.

**Tabellforklaring**

**Nr:** Nummeret til dataelementet. Et element kan ha underelementer som reflekteres i nummereringen vha punktum. Nummereringen av elementer i tabellene er de samme som i IMS-E bortsett fra nummer som starter med P. Dette er utvidelser som ikke er beskrevet i IMS-E.

**Navn:** Beskrivende navn på dataelementet.

**Forklaring:** En kort forklaring av innholdet i elementet.

**Obl:** Om elementet er obligatorisk (O) eller valgfritt (V). Obligatorisk betyr at feltet må være fylt ut for å ha et gyldig objekt. Valgfritt betyr at feltet skal være utfylt om informasjonen finnes i systemet. Alle elementer som er obligatoriske i IMS-E er obligatoriske her, men noen av elementene som er valgfrie i IMS-E er gjort obligatoriske i dette uttrekket. (-) benyttes i beskrivelsen for felleselementer der O/V er beskrevet andre steder. 

I tillegg benyttes en C, conditional,  for et felt er obligatorisk avhengig av hvilken verdi som er satt i et annet felt.

**Mult:** Multiplisiteten til elementet. Blank = en enkelt instans, n = mange instanser uten begrensning, et nummer = maksimalt antall instanser. -= benyttes i beskrivelsen for felleselementer der multiplisiteten er beskrevet andre steder.

**Utdyping:** Utdypende tekst, inkludert eksempler på verdier og syntaks.

**Verdi:** For vokabulartabellene viser denne konkrete verdier et dataelement kan ha.

<a name="enterpriseobjektet"/>

### 2.1. Enterpriseobjektet

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
1.1|comments|Kommentar|V
1.2|properties|Egenskaper med fila|O
1.2.1|lang|Default språk for innhold|O||Obligatorisk her, valgfri i IMS-E
1.2.2|comments|Kommentar for propertydel|V
1.2.3|datasource|Identifikator for datakilden|O||Se struktur 5.3
1.2.4|target|Identifikator for datamottaker|V|n|Skal være unik på global basis. Bygges opp som datasource. Eksempel: *buddy@måne.kommune.no*
1.2.5|type|Beskriver type for dette datauttrekket|O||Obligatorisk her, valgfri i IMS-E. For denne bestillingen benyttes bare *full*, men flere kan komme senere. Tilgjengelige verdier: *full*, *delta*, *melding*. *full* - hele datasettet, *delta* - endring siden siste uttrekk, *melding* - en endringsmelding.
1.2.6|datetime|Tidspunkt datauttrekket ble laget|O
1.2.7|extension|Utvidelse av propertydel
1.3|person|Personobjekter|V	|n|Valgfri, men som regel fylt ut
1.4|group|Gruppeobjekter og deres relasjoner til andre gruppeobjekter|V|n|Valgfri, men som regel fylt ut. Inneholder både organisasjonsinformasjon, grepkodegrupper, undervisningsgrupper og lignende.
1.5|membership|Personers og gruppers medlemskap i grupper|V|n|Valgfri, men som regel fylt ut. 

Datauttrekket skal struktureres etter rekkefølgen i tabellen over. 

<a name="personobjekter"/>

### 2.2. Personobjekter

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
2.1|recstatus|Type operasjon for denne personen|V||Benyttes ikke når datauttrekkstypen (1.2.5) er *full*. Ved andre typer skal denne være fylt ut etter IMS-E.
2.2|comments|Kommentar til denne personen|V||Beskrivende tekst om personen. 
2.3|sourcedid|Identifikator på personobjektet (kilde-id i kilde)|O|n|Se struktur og innhold i 5.6. Merk multiplisitet og mulighet for å endre sourcedid. 
2.4|userid|Forskjellige brukerIDer|V|n|Se struktur og innhold i 5.9.
2.5|name|Navnestruktur|O||SATS og Extens oppga at de bare hadde felt for fornavn og etternavn, så navnestrukturen er kuttet ned i forhold til vanlig IMS-E.
2.5.1|fn|Formatted name	|O||Formatert navn. Fullt juridisk navn. 
2.5.4|n|Navnet delt opp i deler	|O||Obligatorisk her, valgfri i IMS-E.
2.5.4.1|family|Familienavn, ikke nødvendigvis siste navn|O||Som regel etternavn etter reglene for navn i Norge, men kan variere.
2.5.4.2|given|Gitt navn, ikke nødvendigvis første navn|O||Som regel fornavn etter reglene for navn i Norge, men kan variere.
2.6|demographics|Demografisk informasjon|V		
2.6.1|gender|Personens kjønn|V||IMS-E begrenset til verdiene *0*, *1* og *2*. *0* - Ukjent, *1* - Kvinne, *2* - Mann.
2.6.2|bday|Fødselsdato|V||Ikke utledet fra fødselsnummer eller lignende
2.7|email|E-postadresse med høyest prioritet|V	
2.8|url|Webadresse med høyest prioritet|V		
2.9|tel|Telefon med av en type med høyest prioritet|V|n|Internasjonalt format skal benyttes, for eksempel *+47-99900099*.
2.9.1|teltype|Forskjellige telefontyper|O||Om tel (2.9) er utfylt skal type defineres. Gyldige verdier for dette uttrekket er *Voice*, *Fax* eller *Mobile*. *Voice* - taletelefon, *Fax* - faks, *Mobile* - telefon som har mulighet for mottak av SMS/MMS.
2.10|adr|Adresse for å levere fysiske objekter, med høyest prioritet|V||IMS-E støtter bare en adresse. Flere adresser blir lagt inn i utvidelser under.
2.10.1|pobox|Postboks|V		
2.10.2|extadd|Tilleggsinfo til adresse|V||For eksempel oppgang, suite eller lignende.
2.10.3|street|Gateadresse|V	|3|Maksimalt tre linjer i den rekkefølgen det skal skrives ut.
2.10.4|locality|Poststed|V		
2.10.5|region|Region|V||Benyttes ikke i norske adresser.
2.10.6|pcode|Postnummer	|V		
2.10.7|country|Land|V||Fylles alltid ut, selv for norske adresser. Følger ISO3166, fortrinnsvis alpha2 der det eksisterer. 
2.11|photo|Referanse til et eksternt fotografi|V||Bildet blir referert til, ikke inkludert i overføringen.
2.11.1|imgtype|Typen bilde|V||MIME-format benyttes, for eksempel *image/jpg*.
2.11.2|extref|Bildereferansen|V	||En URL der bildet kan hentes fra. Eksempler kan være *http://måne.kommune.no/bilder/124.jpg* og *smb://filserver/bilder/124.jpg*.
2.15|extension|Utvidelser for personobjektet|V	||Utvidelser på personer er beskrevet i tabellen under.

<a name="poutvidelser"/>

#### 2.2.1. Utvidelser for personobjekter

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
P2.15.1|pifu_email|Flere e-postadresser knyttet til person|V|n
P2.15.1.1|type|E-posttype|V||Skal være fylt ut om pifu_email benyttes. Se verdier i tabellen under.
P2.15.1.2|priority|Prioritet på denne e-postadressen|V||Et heltall der 1 har høyest prioritet. 0 er ukjent/ingen verdi.
P2.15.2|pifu_url|Flere URLer knyttet til personen|V|n
P2.15.2.1|type|URL-type|V||Skal være fylt ut om pifu_url benyttes. Se verdier i tabellen under.
P2.15.2.2|priority|Prioritet på denne webadressen|V||Et heltall der 1 har høyest prioritet. 0 er ukjent/ingen verdi.
P2.15.3|pifu_tel|Flere telefonnummer knyttet til personen|V|n
P2.15.3.1|type|telefontype|V||Skal være fylt ut om pifu_tel benyttes. Se verdier i tabellen under.
P2.15.3.2|priority|Prioritet på denne telefonen|V||Et heltall der 1 har høyest prioritet. 0 er ukjent/ingen verdi.
P2.15.4|pifu_adr|Flere adresser knyttet til personen|V|n
P2.15.4.1|type|adressetype|V||Skal være fylt ut om pifu_adr benyttes. Se verdier i tabellen under.
P2.15.4.2|priority|Prioritet på denne adressen|V||Et heltall der 1 har høyest prioritet. 0 er ukjent/ingen verdi.
P2.15.4.3|adr|Adressen|V||Strukturen er den samme som 2.10.
P2.15.4.4|timeframe|Tidsbegrensning av adressen|V||Strukturen er den samme som for 5.10.
P2.15.5|pifu_status|Statuser på personen|V|n|Hovedstatus på personen. For typen activeInactive er gyldige verdier *aktiv* eller *inaktiv*. For typen pupilStatus er gyldige verdier *heltid*, *deltid*, *voksen*, *privatist*, *norsk-utv-i-utlandet* eller *utenlandsk-utv-i-norge*.
P2.15.5.1|type|type status|V||Må fylles ut om status er definert. Gyldige verdier er *activeInactive* eller *pupilStatus*.
P2.15.6|pifu_preferredLanguage|Foretrukket språkform|V||Helst to-bokstavers kode, men tre-bokstaver for de som ikke har to i standardene under.
P2.15.6.1|source|Språkstandard brukt|V||Må fylles ut om foretrukket språk er definert. Verdier er *ISO 639-1*, *ISO 639-2* eller *ISO 639-3* avhengig av hvor P2.15.6 er definert.
P2.15.7|pifu_nativeTongue|Morsmål|V|n|Helst to-bokstavers kode, men tre-bokstaver for de som ikke har to i standardene under.
P2.15.7.1|source|Språkstandard brukt|V||Må fylles ut om morsmål er definert. Verdier er *ISO 639-1*, *ISO 639-2* eller *ISO 639-3* avhengig av hvor P2.15.7 er definert.
P2.15.8|pifu_hasContactPerson|Kontaktperson|V|n|Peker på en sourcedid til kontaktpersoner av forskjellige typer.
P2.15.8.1|type|Type kontaktperson|V||Må fylles ut om kontaktperson er definert. Verdier er *nextOfKin* – pårørende, *guardian* – foresatt, *fosterParent* - fosterforelder og *closeRelative* - nær familie som tante, onkel, besteforelder og steforelder. 
P2.15.8.2|sourcedid|Peker til kontaktperson|V||Må fylles ut om kontaktperson er definert. Samme struktur som 5.6.

<a name="poutvidelservokab"/>

##### 2.2.1.1. Vokabular for utvidelser på personobjekt

**Nr**|**Navn**|**Verdi**|**Obl**|**Utdypning**|
:-----|:-------|:--------|:------|:------------|
P2.15.1.1|pifu_email - type	|*personEmailPrivate*|V|Privat e-postadresse.
|||*personEmailAtOrg*|V|E-postadresse ved organisasjonen.
P2.15.2.1|pifu_url - type|*personURLPrivate*|V|Privat webside.
|||*personURLAtOrg*|V|Webside ved organisasjonen.
P2.15.3.1|pifu_tel - type|*personTelephonePrivate*|V|Privat talenummer.
|||*personMobilePrivate*|V|Privat nummer som kan motta SMS/MMS.
|||*personTelephoneAtOrg*|V|Talenummer ved org.
|||*personMobileAtOrg*|V|Nummer ved org som kan motta SMS/MMS.
|||*personFaxAtOrg*|V|Nummer ved org som kan motta fax.
|||*personSwitchboard*|V|Personens sentralbordnummer.
P2.15.4.1|pifu_adr - type|*personRegisteredAddressPrivate*|V|Folkeregistrert adresse.
|||*personPostalAddressPrivate*|V|Privat bosted/postadresse.
|||*personVisitorAddressAtOrg*|V|Besøksadresse ved org.
|||*personPostalAddressAtOrg*|V|Postadresse ved org.
|||*personPostalAddressHoliday*|V|Postadresse i ferie.

<a name="gruppeobjekter"/>

### 2.3. Gruppeobjekter - organisasjoner, organisasjonsenheter og grupper

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
3.1|recstatus|Type operasjon for denne gruppen|V||Benyttes ikke når datauttrekkstypen (1.2.5) er *full*. Ved andre typer skal denne være fylt ut etter IMS-E.
3.2|comments|Kommentar til denne gruppen|V||Beskrivende tekst om gruppen. 
3.3|sourcedid|Identifikator på gruppeobjektet (kilde-id i kilde)|O|n|Se struktur og innhold i 5.6. Merk multiplisitet og mulighet for å endre sourcedid. 
3.4|grouptype|Struktur for gruppetype|O|n|Struktur som viser hvilken type gruppe det er.
3.4.1|scheme|Skjemaet som definerer gruppetyper|O||Settes til *pifu-ims-go-org* for grupper som er skoleeier eller skole, *pifu-ims-go-grp* for alle andre.
3.4.2|typevalue|Typen gruppe|O||Tillatte verdier. For scheme *pifu-ims-go-org*: *skoleeier* – skoleeieren, *skole* – skoler. For scheme *pifu-ims-go-grp*: *basisgruppe* – basisgruppe/klasse, *undervisningsgruppe* – undervisningsgruppe i et fag, *kontaktlærergruppe* – gruppe med elever med en kontaktlærer, *trinn* – klassetrinn, *utdanningsprogram* – utdanningsprogram i videregående, *programområde* – progområde i videregående, *fag* – fag i læreplanen, *foresattegruppe* - foresatte til barn som er elever med samme basisgruppetilhørighet, *språkopplæring* - gruppe med elever som mottar særskilt språkopplæring (§2.8/§3.12) med lærer, *sammensattgruppe* - sammensatt gruppe på tvers av klasser, trinn og fag, *elevråd* - skolens elevråd, *fau* - foreldrerådets arbeidsutvalg, *skoleutvalg* - skoleutvalget/samarbeidsutvalget/driftsstyre ved skolen, *skolemiljøutvalg* - skolens skolemiljøutvalg, *sfo* - skolefritidsordning, *eksamensgruppe* - gruppe for elever som skal ta samme eksamen. 
3.4.2.1|level|Gruppetypens tilhørende kode|O||Gjenspeiler en kodeverdi for verdiene i 3.4.2. For schema *pifu-ims-go-org*: *1* – skoleeier, *2* – skole. For schema *pifu-ims-go-grp*: *1* – basisgruppe, *2* – undervisningsgruppe, *3* – kontaktlærergruppe, *4* – trinn, *5* – utdanningsprogram, *6* – programområde, *7* – fag, *8* - foresattegruppe, *9* - språkopplæring, *10* - sammensattgruppe, *11* - elevråd, *12* - fau, *13* - skoleutvalg, *14* - skolemiljøutvalg, *15* - sfo, *16* - eksamensgruppe.
3.5|description|Beskrivelse av gruppen|O		
3.5.1|short|Kort navn på gruppen|O		
3.5.2|long|Beskrivelse av gruppen|V||Begrenset til String256, så kan jo ikke bli så lang.
3.5.3|full|Lengre beskrivelse av gruppen|V	||String2048 så her er det plass til mer tekst.
3.7|timeframe|Tidsbegrensning for gruppen|V||Skal være fylt for grupper som har tidsbegrensning. Se struktur 5.10.
3.9|email|E-post til gruppen med høyest prioritet|V
3.10|url|Webadresse til gruppen med høyest prioritet|V
3.11|relationship|Relasjon til andre grupper|O|n|Her knyttes grupper sammen i et hierarki. 
3.11.1|relation|Type relasjon|O	||For dette datautrekket brukes bare *parent*. Topporganisasjon peker på seg selv, org.enheter pekter på org eller org.enhet over seg. Alle andre gruppetyper peker på org.enhet de tilhører.
3.11.2|sourcedid|ID til parent|O||Den gruppen som er parent til denne gruppen. Struktur 5.6.
3.11.3|label|Tekstlig merknad som beskriver relasjonen|O||IMS-E har denne som obligatorisk. **I IMS-E er dette en String32, utvidet til String128 for norske behov**.
3.13|extension|Utvidelser for gruppeobjektet|V	||Utvidelser på gruppetyper er beskrevet i tabellene under

<a name="goutvidelser1"/>

#### 2.3.1. Utvidelser på organisasjon og organisasjonsenhet

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
P3.13.1|pifu_id|Forskjellige identifikatorer|O|n|Struktur for en id.
P3.13.1.1|type|Typen identifikator|O||Se vokabular i tabellen under.
P3.13.1.2|pifu_value|Verdien i IDen|O||Selve verdien på IDen.
P3.13.1.3|pifu_scope|Gyldighetsområdet for verdien|O||Et skop/sett der verdien er medlem. Se vokabular i tabellen under.
P3.13.1.4|pifu_unique|Om verdien er unik|O	||Settes til *1* om dette objektet er det eneste som har denne verdien i pifu_scope. *0* om det er flere objekter som kan ha samme ID.
P3.13.2|pifu_name|Forskjellige navneformer på org/ou|O|n|Struktur for et navn.
P3.13.2.1|type|Typen navn|O	||Se vokabular i tabellen under.
P3.13.2.2|pifu_value|Verdien i navnet|O||Selve navnet.
P3.13.2.3|pifu_language|Språket navnet er skrevet i|V||Helst to-bokstavers kode, men tre-bokstaver for de som ikke har to i standardene under.
P3.13.2.3.1|source|Standarden for språkkoden brukt over|V||Må fylles ut om språk er definert. Verdier er *ISO 639-1*, *ISO 639-2* eller *ISO 639-3* avhengig av hvor P3.13.2.3 er definert.
P3.13.3|pifu_email|E-post til org/ou|V||Kontaktadresse til enheten.
P3.13.3.1|type|typen e-postadresse|V||For org/ou er denne alltid *orgEmail*.
P3.13.4|pifu_url|Websted knyttet til org/ou|V|n
P3.13.4.1|type|Typen websted|V||For org/ou brukes *orgURL* – åpen webside, *orgIntranet* – enhetens intranett.
P3.13.5|pifu_tel|Telefonnummer til enheten|V|n	
P3.13.5.1|type|Typen telefonnummer|V||For org/ou brukes *orgTelephone* – enhetens telefonmottak, *orgFax* – enhetens faks.
P3.13.6|pifu_adr|Adresser til enheten|V|n|Adressestrukturen følger 2.10 adr.
P3.13.6.1|type|Typen adresse|V||Se vokabular i tabellen under.
P3.13.7|pifu_schoolType|Typen skole|V||Tillate verdier: *barneskole* (1.-7. trinn), *ungdomsskole* (8.-10. trinn), *barneOgUngdomsskole* (1.-10. trinn), *videregående* (vg1, vg2, vg3 og påbygg), *barnehage* (barnehage) og *sfo* (skolefritidsordning).

<a name="goutvidelser1vokab"/>

##### 2.3.1.1. Vokabular for utvidelser på organisasjon og organisasjonsenhet

**Nr**|**Navn**|**Verdi**|**Obl**|**Utdypning**|
:-----|:-------|:--------|:------|:------------|
P3.13.1.1|pifu_id - type|*organizationNumber*|O|Organisasjonsnummer registrert i enhetsregisteret skal være med i eksport. eks ’NO999000999’.
|||*vigoNumber*|V|Vigonummeret om enheten har det.
|||*domainName*|V|Domenenavn om det er tilgjengelig.
|||*municipalityNumber*|V|Kommunenummeret til skoleeieren.
|||*countyNumber*|V|Fylkesnummeret til skoleeieren, eller fylket der kommunen ligger.
|||*gsiNumber*|V|Nummer fra Grunnskolens Informasjonssystem (GSI).
P3.13.1.3|pifu_scope|*enhetsregistere*t|O|Settes når type er organizationNumber. Sannsynligvis skal da også pifu_unique settes til *1*.
|||*vigo*|V|Settes når type er vigoNumber. Sannsynligvis skal da også pifu_unique settes til *1* om ikke en vigo-enhet er modellert som flere organisasjonsenheter.
|||*gsi*|V|Settes når type er gsiNumber. Sannsynligvis skal da også pifu_unique settes til *1*.
|||*.no*|V|Settes når type er domainname. Pifu_unique avhenger av om flere enheter har samme domainname knyttet til seg.
|||*http://hotell.difi.no/?dataset=difi/geo/kommune*|V|Settes når type er municipalityNumber. Pifu_unique må som oftest settes til *0*, det avhenger av om flere enheter har samme municipalityNumber knyttet til seg, som er sannsynlig i de fleste use cases.
|||*http://hotell.difi.no/?dataset=difi/geo/fylke*|V|Settes når type er countyNumber. Pifu_unique må som oftest settes til *0*, det avhenger av om flere enheter har samme countyNumber knyttet til seg, som er sannsynlig i de fleste use cases.
P3.13.2.1|pifu_name - type|*legalName*|O|Enhetens juridiske navn.
|||*name*|V|Enhetens vanlige navn.
|||*fullName*|V|Enhetens fulle navn.
|||*shortName*|V|Enhetens kortnavn.
P3.13.6.1|pifu_adr - type|*orgPostalAddress*|V|Enhetens postadresse.
|||*orgVisitorAddress*|V|Enhetens besøksadresse.
|||*orgDeliveryAddress*|V|Enhetens leveringsadresse.
|||*orgBillingAddress*|V|Enhetens fakturaadresse.

<a name="goutvidelser2"/>

#### 2.3.2. Utvidelser på basisgruppe og kontaktlærergruppe

<a name="goutvidelser3"/>

#### 2.3.3. Utvidelser på trinn, utdanningsprogram, programområde, fag, undervisningsgruppe, sammensattgruppe og eksamensgruppe

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
P3.13.1|pifu_id|Forskjellige identifikatorer|O|n|Struktur for en id.
P3.13.1.1|type|Typen identifikator|O||Se vokabular i tabellen under.
P3.13.1.2|pifu_value|Verdien i IDen|O||Selve verdien på IDen.
P3.13.1.3|pifu_scope|Gyldighetsområdet for verdien|O||Et skop/sett der verdien er medlem. Se vokabular i tabellen under.
P3.13.1.4|pifu_unique|Om verdien er unik|O||Settes til *1* om dette objektet er det eneste som har denne verdien i pifu_scope. *0* om det er flere objekter som kan ha samme ID.

<a name="goutvidelser3vokab"/>

##### 2.3.3.1. Vokabularer for utvidelser på trinn, utdanningsprogram, programområde, fag,  undervisningsgruppe, sammensattgruppe og eksamensgruppe

**Nr**|**Navn**|**Verdi**|**Obl**|**Utdypning**|
:-----|:-------|:--------|:------|:------------|
P3.13.1.1|pifu_id - type|*grepCode*|O|PSI eller uuid til gruppen fra grep.
|||*grepCodeShortForm*|V|Kortform eller NVB-kode til gruppen fra grep.
P3.13.1.3|pifu_scope|*grep - levende læreplaner*|O|Settes når type er grepCode og grepCodeShortForm. 

<a name="medlemskapsobjekter"/>

### 2.4. Medlemskapsobjekter

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
4.1|comments|Kommentar på medlemskapsobjektet|V||**Skal vi gjøre denne obligatorisk? Skal vi fjerne her?**
4.2|sourcedid|IDen på gruppen medlemskapene peker på|O||Her peker en på IDen til gruppen (org/ou/fag/basisgruppe osv).
4.3|member|Medlemmene i gruppen	|O|n|Struktur for medlemmer i gruppen.
4.3.1|comments|Kommentar for dette medlemmet|V	
4.3.2|sourcedid|IDen på medlemmet|O||Peker til brukeren eller gruppen som er medlem av gruppen pekt på i 4.2.
4.3.3|idtype|Viser om dette er en person eller gruppe|O||I dette uttrekket er det bare personer som er medlemmer i grupper, så denne settes til *1*.
4.3.4|role|Rolle medlemmet har i gruppen|O|n|Struktur for å beskrive et medlems rolle i gruppen.
4.3.4.1|recstatus|Type operasjon for denne personen|V||Benyttes ikke når datauttrekkstypen (1.2.5) er *full*. Ved andre typer skal denne være fylt ut etter IMS-E.
4.3.4.2|roletype|Medlemmets rolle|O||Obligatorisk her, valgfritt i IMS-E. Vokabular definert i IMS-E med følgende oversettelse: *01* – elev, *02* – lærer/pedansatt, *03* - content developer, *04* – andre, *05* - skoleledelse, *06* - kontaktlærer, *07* - administrator, *08* - assistent.
4.3.4.3|subrole|Utdypende rolle	|V||**Denne bryter med IMS Enterprise 1.1. Det er et behov å ha definerte verdier å velge mellom.** Underroller for roletype 4.3.4.2. Tillatte verdier: for roletype *02* - *faglærer*, *lærerstudent*, *vikar*. For roletype *04* - *rådgiver*, *kontormedarbeider*, *skolehelsetjeneste*, *skolebibliotekansvarlig*, *vaktmester*, *renholdsarbeider*, *sosiallærer*, *sensor*, *pptansatt*. For roletype *05* - *rektor*, *inspektør*. For roletype *07* - *iktansvarlig*.<br /> **Fortsatt støtte for verdier fra Vigo brukerhåndbok for Sats/Extens** <br /> **1.** Dersom rolletypen er *elev* og gruppetypen er *fag* kan rollen (fagstatus) eleven har i faget utdypes med følgende verdier (hentet fra Vigo brukerhåndbok for Sats/Extens): *E* (elev), *A* (spesialundervisning), *F* (fritatt), *M* (fagopplæring i skole), *N* (nettundervisning), *U* (utenlandsk utvekslingselev i Norge), *P* (privatist), *R* (realkompetansevurdert), *V* (voksen), *O* (oppdragsundervisning), *S* (Avbrutt opplæring i faget). **2.** Dersom rolletypen er *elev* og gruppetypen er *programområde* kan rollen (elevstatus) eleven har i programområdet utdypes med følgende verdier (hentet fra Vigo brukerhåndbok for Sats/Extens): *E* (elev), *A* (spesialundervisning), *D* (deltidselev), *U* (utenlandsk utvekslingselev i Norge), *I* (norsk utvekslingselev i utlandet), *M* (fagopplæring i skole), *P* (privatist), *V* (voksen), *O* (oppdragsundervisning), *S* (avbrutt hele programområdet), *L* (lærling i programområdet (opplæring i bedrift)), *K* (lærekandidat i programområdet (opplæring i bedrift)).
4.3.4.4|status|Status på medlemskap|O||Sier om relasjonen skal være aktiv eller ikke. Settes som regel til *1*, kan settes til *0* om relasjonen skal deaktiveres.
4.3.4.6|comments|Kommentar på rolle 			
4.3.4.7|datetime|Tidspunkt der gjeldende medlemskapstatus ble oppdatert|V
4.3.4.8|timeframe|Gyldighetstid for medlemskapet|V||Brukes for å sette tidsbegrensinger på medlemskap, for eksempel for et semester, skoleår eller lignende.
4.3.4.9|Interimresult|Resultater og karakterer gjennom året|V|n|Kan benyttes for å overføre karakterer og andre resultater gjennom året, for eksempel terminkarakterer og lignende.
4.3.4.9.1|resulttype|Hvilken type resultat det er|V||Her settes hva det er resultat for, for eksempel termin 1.
4.3.4.9.2|mode|Type resultatskala|V||Hvilken skala som benyttes: *Letter grade* – bokstavkarakterer, *Number grade* – tallkarakterer, *Pass/Fail* – Bestått/Ikke-bestått, *Percentage* - prosentpoeng.
4.3.4.9.3|values|Gyldige verdier for resultatet|V||Struktur for å beskrive gyldige verdier innenfor de forskjellige resultatskalaene.
4.3.4.9.3.1|valuetype|Type verdirom for resultatskala|O||Om det er gitte verdier, eller en kontinuerlig skala: *0* – liste med verdier, *1* – kontinuerlig tallskala, f.eks 0-100.
4.3.4.9.3.2|list|resultatverdi for gitte verdier|C|n|Om valuetype er *0* må list fylles ut med tillatte verdier, som for eksempel A, B, C, D, E, F, 1, 2, 3, 4, 5, 6, Bestått osv.
4.3.4.9.3.3|min|minimum resultatverdi|C||Om valuetype er *1* skal minimumsverdi fylles ut, for eksempel 0.
4.3.4.9.3.4|max|maksimum resultatverdi|C||Om valuetype er *1* skal maksimumsverdi fylles ut, for eksempel 100
4.3.4.9.4|result|resultatet/karakteren|V||Selve karakteren/resultatet eleven har fått. 
4.3.4.9.5|comments|kommentar|V||Kommentar om interimresultatet.
4.3.4.10|finalresult|Sluttresultat/karakter|V|n|Kan benyttes for å overføre endelige karakterer og andre resultater på slutten av fag.
4.3.4.10.1|mode|Type resultatskala|V||Hvilken skala som benyttes: *Letter grade* – bokstavkarakterer, *Number grade* – tallkarakterer, *Pass/Fail* – Bestått/Ikke-bestått, *Percentage* - prosentpoeng
4.3.4.10.2|values|Gyldige verdier for resultatet|V||Struktur for å beskrive gyldige verdier innenfor de forskjellige resultatskalaene.
4.3.4.10.2.1|valuetype|Type verdirom for resultatskala|O||Om det er gitte verdier, eller en kontinuerlig skala: *0* – liste med verdier, *1* – kontinuerlig tallskala, f.eks 0-100.
4.3.4.10.2.2|list|resultatverdi for gitte verdier|C|n|Om valuetype er *0* må list fylles ut med tillatte verdier, som for eksempel A, B, C, D, E, F, 1, 2, 3, 4, 5, 6, Bestått osv.
4.3.4.10.2.3|min|minimum resultatverdi|C||Om valuetype er *1* skal minimumsverdi fylles ut, for eksempel 0.
4.3.4.10.2.4|max|maksimum resultatverdi|C||Om valuetype er *1* skal maksimumsverdi fylles ut, for eksempel 100.
4.3.4.10.3|result|resultatet/karakteren|V||Selve karakteren/resultatet eleven har fått. 
4.3.4.10.4|comments|kommentar|V	||Kommentar om det endelige resultatet. 
4.3.4.10.5|resulttype|Hvilken type resultat det er|V||Her settes hva det er resultat for, for eksempel  standpunkt. **Denne bryter med IMS Enterprise 1.1. Finalresult mangler muligheten til å si hvilken type resultat det er, for eksempel standpunkt, skriftlig eksamen eller muntlig eksamen. For å kunne ha flere finalresults på samme fag/gruppe og kunne skille mellom dem må vi legge til dette feltet**. 
4.3.4.13|extension|Utvidelse for dette rolleobjektet.

<a name="moutvidelser"/>			

#### 2.4.1. Utvidelser på rolleobjektet

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
P4.3.4.13.1|pifu_primaryRelation|Om dette er primærrollen|V||Settes til *1* om dette er primærrollen mellom medlem og gruppe, *0* om det ikke er det. Brukes for eksempel om en person både er elev og ansatt ved samme skole/skoleeier.
P4.3.3.13.2|pifu_absence|Fraværsinformasjon|V||Fraværsstruktur som kobles til et gruppemedlemskap. Gruppen er typisk et fag for fravær knyttet til akkurat dette faget eller skolen for fravær oppsummert over alle fag.
P4.3.3.13.2.1|pifu_absence_mode	|Fraværskategori|O||Hvilken kategori fraværet er: *occurence* – innslag for et enkelt fraværstilfelle, *aggregate* – sum av flere fraværstilfeller.
P4.3.3.13.2.2|sourcedid|Identifikator for fraværet|V||ID som identifiserer dette fraværet i avsendersystemet.
P4.3.3.13.2.3|pifu_absence_type|Fraværstype|O||Hvilken type fravær det er: *hours* – timefravær i klokketimer, *days* - dagsfravær.
P4.3.3.13.2.4|pifu_absence_classification|Klassifisering av fravær|V||Attributt som klassifiserer om det er gyldig fravær eller ikke: *valid* – gyldig fravær, *invalid* – ugyldig fravær
P4.3.3.13.2.5|timeframe|Tidsperiode for fraværet|O||Tidsperioden fraværet oppstod/gjelder for. For kategorien occurence vil det typisk være datoen fraværet var. For aggregate vil det være perioden fraværet er summert opp over, for eksempel en termin eller hele skoleåret.
P4.3.3.13.2.6|pifu_absence_value|Fraværsverdi|O||Tallverdien for fraværet. For eksempel 3 (dager), 0.75 (timer).
P4.3.3.13.2.7|comments|Kommentarer|V||Kommentar for fraværet.

<a name="finformasjonselementer"/>

### 2.5. Felles informasjonselementer

**Nr**|**Navn**|**Forklaring**|**Obl**|**Mult**|**Utdypning**|
:-----|:-------|:-------------|:------|:-------|:------------|
5.1|comments|Kommentar for objekt|-|-	
5.1.1|lang|Språket kommentaren er skrevet i|V||Struktur 5.2.
5.2|lang|Språket teksten er skrevet i|-|-|Helst to-bokstavers kode, men tre-bokstaver for de som ikke har to i standardene ISO 639-1, ISO 639-2 eller ISO 639-3.
5.3|datasource|Identifikator for datakilden|||Skal være unik på global basis. Bygges opp som fagsystemid@enhet. Enhet er som regel en skoleeier eller eventuelt en skole om de kjører sitt eget fagsystem. Eksempel: *sats@måne.kommune.no*.
5.4|datetime|Tidspunktet objektet ble generert|-|-|ISO8601. Eksempler *1970-01-30*, *2011-10-07T10:31:03*.
5.5|recstatus|Transaksjonstype på objektet|-|-|Brukes for å kunne gjøre oppdateringer av deler av datasettet. Om verdien ikke er der skal det tolkes som en add eller update.
5.6|sourcedid|Identifikator på objektet i kilden|-|-
5.6.1|sourcedidtype|Typen for sourcedid|V||Benyttes når en endrer id og har duplikater. Tillatte verdier: *New*, *Old*, *Duplicate*.
5.6.2|source|Identifikator på kilden som tildelte objektiden under|O||Begrenset til string32, men bør være det samme som 1.2.3.
5.6.3|id|Permanent unik id for objektet slik det er definert i kilden|O||Datakildens unike id for dette objektet.
5.7|email|E-mail adresse med høyest prioritet/hovedadresse|-|-
5.8|url|Webside med høyest prioritet/hovedadresse|V||Ikke bruk relative adresser, bare fulle adresser.
5.9|userid|Personens identifikator|-|-|Selve verdien på identifikatoren, for eksempel brukernavn.
5.9.1|useridtype|Type identifikator|O||Oblikatorisk her, valgfri i IMS. Identifikatorer som skal fylles ut i dette uttrekket om informasjonen finnes er: *personNIN* – fødselsnummer/d-nummer eller lignende, *personNINencrypted* – personNIN kryptert slik at avsender kan dekryptere innholdet til en personNIN (Kryperingsmetode avtales mellom avsender og mottaker utenfor overføringen), *personLIN* - lokalt gitt ID-nummer, *personFIN* - VIGO-nr, *studentID* – Elevnummer, *workforceID* – ansattnummer, *username* – brukernavn, *sisID* – systemidentifikator i SAS/SIS(IPOS/OID), *feideID* - Feidebruker identifikator. Tilsvarer verdien eduPersonPrincipalName i [feidedokumentasjonen](https://docs.feide.no/reference/schema/info_uh/uh_attributter_ch02.html#edupersonprincipalname), *dufNumber* - DUF-nummer, *dNumber* - D-nummer, *microsoftUPN* - Brukernavn i office 365/Azure AD.
5.9.2|password|Passord|V||For userid av typen username kan passord settes.
5.9.3|pw.encryptiontype	||V||Om passord er satt skal krypterinsmetoden angis her: *passwordMD5* – MD5-hash er benyttet, *passwordPlain* – passordet er i klartekst.
5.10|timeframe|Gyldighetsområde i tid for et objekt|-|-|Brukes for å avgrense et objekt i tid, for eksempel et semester
5.10.1|begin|Starttidspunkt|V||ISO8601, begrenset til dato ser det ut til.
5.10.1.1|restrict|Bestemmer om elev kan delta i objektet før denne datoen|V||Om en ønsker å si at elever ikke skal være medlem av en gruppe før datoen kan en sette denne til *1* ellers *0*.
5.10.2|end|Sluttidspunkt|V||ISO8601, begrenset til dato ser det ut til.
5.10.2.1|restrict|Bestemmer om elev kan delta i objektet etter denne datoen|V||Om en ønsker å si at elever ikke skal være medlem av en gruppe etter datoen kan en sette denne til *1* ellers *0*.
5.10.3|adminperiod|Kort beskrivelse av en periode|V||Kan for eksempel brukes til å sette lesbare navn på semesteravgrensninger og lignende. *2010* – kalenderår, *2010/2011* – skoleår, *H2010* – høstsemesteret, *V2011* – vårsemesteret.
