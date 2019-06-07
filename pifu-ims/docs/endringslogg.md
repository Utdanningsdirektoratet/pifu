# Endringslogg

**2019-06-07:**

* Oppdatert til versjon 1.2.
* La inn foresattegruppe og språkopplæring som nye gruppetyper i skjema pifu-ims-go-grp. 
* La inn GSI som ny identifikatortype for organisasjon og organisasjonsenhet. 
* La inn personLIN og personFIN som nye identifikatortyper for personer for henholdsvis lokalt gitte ID-nummer og VIGO-nr.

**2016-04-29:**

* Følgende er kun endringer i dokumentasjonen.
* La til undervisningsgruppe i utvidelser for trinn, utdanningsprogram, programområde og fag. Det er behov for å knytte undervisningsgruppe til et fag (grep-kode), jmf. Feide 1.6. 

**2014-07-04:**  

* Oppdatert til versjon 1.1.
* La inn ny type t_decimal8p4_wn og utvidet pifu_absence_value fra t_decimal8p4 til t_decimal8p4_wn på grunn av problemer knyttet til validering av fravær, da det her registreres negativt fravær, av forskriftsmessige årsaker.

**2014-01-23:**  

* La inn countyNumber og municipalityNumber som mulige verdier i pifu_id.

**2013-09-18:**  

* Oppdatert til versjon 1.0, og renset litt opp i kommentarer i dokumentet.

**2013-09-16:**  

* La inn pifu_absence_classification for å kunne si om det er gyldig eller ugyldig fravær.

**2013-08-22:**  

* La inn userID-type personNINencrypted for å muliggjøre overføring av NIN i toveis-kryptert format. Dette er en mulig ekstra sikring av fødselsnummer i tillegg til at selve overføringen bør gjøres kryptert.

**2013-03-11:**  

* La inn beskrivelse av resultater/karakterer (interimresult og finalresult). Ganske åpen beskrivelse og verdirom som burde strammes opp i samarbeid med sektoren.

**2013-01-31:**  

* 3.11.3 label (i relationship) er utvidet fra t_string32 til t_string128 på grunn av behov for større plass og bryter derfor med ren IMS Enterprise 1.1.
