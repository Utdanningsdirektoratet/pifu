# Overordnet beskrivelse

PIFU-IMS inneholder informasjon om:

* Personer
	* Elever
	* Lærere
	* Andre ansatte
	* Foresatte og kontaktpersoner
* Grupperinger
	* Skoleeier
	* Skoler
	* Basisgruppe
	* Undervisningsgruppe
	* Kontaktlærergruppe
	* Trinn
	* Undervisningsprogram
	* Programområde
	* Fag
* Personers medlemskap i grupperinger

## 1. Informasjon om personer

### 1.1. Informasjon om elever

**Identifikatorer**|**Navn og basisinfo**|**Kontaktinformasjon**|**Annen informasjon**
:------------------|:--------------------|:---------------------|:--------------------
Fødselsnummer|Fullt navn|E-postadresse (hovedadresse)|Aktivstatus på personen (aktiv/inaktiv)
Fødselsnummer i toveis-kryptert format|Fornavn|E-postadresse privat|Elevstatus (heltid/deltid/privatist/voksen/utveksl. i utlandet/utveksl. i Norge)
Identifikator i SAS|Etternavn|E-postadresse ved organisasjon|Foretrukket språkform
Studentnummer|Kjønn|Telefonnummer (hovednummer)|Morsmål
Brukernavn/passord om dette genereres i SAS|Fødselsdato (ikke utledet fra fødselsnummer)|Telefonnummer privat taletelefon|Peker til foresatte
|||Telefonnummer privat mobil/sms|Peker til bilde
|||Postadresse (hovedadresse)
|||Postadresse folkeregistrert
|||Postadresse Bosted
|||Postadresse Ferie/midlertidig
|||Tidsbegrensning på adresser

### 1.2. Informasjon om lærere

**Identifikatorer**|**Navn og basisinfo**|**Kontaktinformasjon**|**Annen informasjon**|
:------------------|:--------------------|:---------------------|:--------------------|
Fødselsnummer|Fullt navn|E-postadresse (hovedadresse)|Aktivstatus på personen (aktiv/inaktiv)|
Fødselsnummer i toveis-kryptert format|Fornavn|E-postadresse privat|Foretrukket språkform|
Identifikator i SAS|Etternavn|E-postadresse ved organisasjon|Morsmål|
Ansattnummer|Kjønn|Webside (hovedadresse)|Peker til kontaktpersoner/pårørende|
Brukernavn/passord om dette genereres i SAS|Fødselsdato (ikke utledet fra fødselsnummer)|Webside privat|Peker til bilde|
|||Webside ved organisasjon|
|||Telefonnummer (hovednummer)|
|||Faksnummer (hovednummer)|
|||Mobil/SMS (hovednummer)|
|||Telefonnummer privat Taletelefon|
|||Telefonnummer privat Mobil/sms|
|||Telefonnummer ved org Taletelefon|
|||Telefonnummer ved org Mobil/sms|
|||Telefonnummer ved org Faks|
|||Telefonnummer ved org Sentralbord|
|||Postadresse (hovedadresse)|
|||Postadresse folkeregistrert|
|||Postadresse Bostedsadresse|
|||Postadresse Ferie/midlertidig|
|||Besøksadresse ved organisasjon|
|||Tidsbegrensning på adresser|

### 1.3. Informasjon om andre ansatte

**Identifikatorer**|**Navn og basisinfo**|**Kontaktinformasjon**|**Annen informasjon**|
:------------------|:--------------------|:---------------------|:--------------------|
Fødselsnummer|Fullt navn|E-postadresse (hovedadresse)|Aktivstatus på personen (aktiv/inaktiv)|
Fødselsnummer i toveis-kryptert format|Fornavn|E-postadresse privat|Foretrukket språkform|
Identifikator i SAS|Etternavn|E-postadresse ved organisasjon|Morsmål|
Ansattnummer|Kjønn|Webside (hovedadresse)|Peker til kontaktpersoner/pårørende|
Brukernavn/passord om dette genereres i SAS|Fødselsdato (ikke utledet fra fødselsnummer)|Webside privat|Peker til bilde|
|||Webside ved organisasjon|
|||Telefonnummer (hovednummer)|
|||Faksnummer (hovednummer)|
|||Mobil/SMS (hovednummer)|
|||Telefonnummer privat Taletelefon|
|||Telefonnummer privat Mobil/sms|
|||Telefonnummer ved org Taletelefon|
|||Telefonnummer ved org Mobil/sms|
|||Telefonnummer ved org Faks|
|||Telefonnummer ved org Sentralbord|
|||Postadresse (hovedadresse)|
|||Postadresse folkeregistrert|
|||Postadresse Bostedsadresse|
|||Postadresse Ferie/midlertidig|
|||Besøksadresse ved organisasjon|
|||Tidsbegrensning på adresser|

### 1.4. Informasjon om foresatte og kontaktpersoner/pårørende

**Navn og basisinfo**|**Kontaktinformasjon**|
:--------------------|:---------------------|
Fullt navn|E-postadresse privat|
Fornavn|Telefonnummer privat Taletelefon|
Etternavn|Telefonnummer privat Mobil/SMS|

## 2. Informasjon om grupperinger

### 2.1. Informasjon om skoleeier

**Identifikatorer**|**Navn og basisinfo**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:---------------------|:----------------------------------|
Organisasjonsnummer|Navn|E-postadresse|Peker til seg selv (toppnode)|
Domenenavn|Juridisk navn|Websted ekstern|
Kommunenummer (og/eller)|Fullt navn|Websted intern/Intranett|
Fylkesnummer|Kortnavn|Telefonnummer|
|||Faksnummer|
|||Postadresse|
|||Besøksadresse|
|||Leveringsadresse|
|||Fakturaadresse|

### 2.2. Informasjon om skoler

**Identifikatorer**|**Navn og basisinfo**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:---------------------|:----------------------------------|
Organisasjonsnummer/bedriftsnummer|Navn|E-postadresse|Peker til enheten over seg/skoleeier|
Domenenavn|Juridisk navn|Websted ekstern|
Vigonummer|Fullt navn|Websted intern/Intranett|
||Kortnavn|Telefonnummer|
|||Faksnummer|
|||Postadresse|
|||Besøksadresse|
|||Leveringsadresse|
|||Fakturaadresse|  

### 2.3. Informasjon om basisgrupper

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
||Beskrivelse kort|Starttidspunkt|E-postadresse|Peker til skole|
|||Sluttidspunkt|Websted|
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.4. Informasjon om undervisningsgrupper

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
Grepkode|Beskrivelse kort|Starttidspunkt|E-postadresse|Peker til skole|
Grepkode kortform||Sluttidspunkt|Websted|
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.5. Informasjon om kontaktlærergrupper

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
||Beskrivelse kort|Starttidspunkt|E-postadresse|Peker til skole|
|||Sluttidspunkt|Websted|
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.6. Informasjon om trinn

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
Grepkode|Beskrivelse kort|Starttidspunkt||Peker til skole|
Grepkode kortform||Sluttidspunkt||
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.7. Informasjon om utdanningsprogram

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
Grepkode|Beskrivelse kort|Starttidspunkt||Peker til skole|
Grepkode kortform||Sluttidspunkt||
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.8. Informasjon om programområde

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
Grepkode|Beskrivelse kort|Starttidspunkt||Peker til skole|
Grepkode kortform||Sluttidspunkt||
|||Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.9. Informasjon om fag

**Identifikatorer**|**Navn og basisinfo**|**Gyldighetsperiode**|**Kontaktinformasjon**|**Relasjon til andre grupperinger**|
:------------------|:--------------------|:--------------------|:---------------------|:----------------------------------|
Grepkode|Beskrivelse kort|Starttidspunkt||Peker til skole|
Grepkode kortform|Beskrivelse middels|Sluttidspunkt||
||Beskrivelse full|Tekstlig beskrivelse for eksempel ’2007/2008’, ’V2008’|

### 2.10. Informasjon om personers medlemskap i grupperinger

**Identifikatorer**|**Medlemsinformasjon for hvert medlem**|**Gyldighetsperiode for medlemskap for hvert medlem**|**Resultater, karakterer og fravær**|
:------------------|:--------------------------------------|:----------------------------------------------------|:-----------------------------------|
Peker til gruppeobjekt|Rolle i gruppa (elev, lærer, annet medlem)|Starttidspunkt|Resultater og karakterer for terminer, standpunkt og eksamen|
Peker til et antall medlemmer|Status (Aktiv/inaktiv)|Sluttidspunkt|Fraværsdager og timer knyttet til fag og samlet|
||Tidspunkt medlemskap/status ble sist ble endret|
||Om dette er primærrollen til medlemmet i gruppa|
