# PIFU 
Personrelatert informasjonsflyt i utdanning (PIFU) er en norsk standard for utveksling av personrelatert informasjon mellom IKT-systemer i utdanningssammenheng. Standarden skal gjøre det enklere for skoleeiere og leverandører av tjenester til utdanningssektoren å motta og avgi informasjon.

<https://standard.iktsenteret.no/pifu>

## PIFU-IMS
PIFU-IMS er en profil av spesifikasjonen [IMS Enterprise 1.1](http://imsglobal.org/enterprise/) tilpasset PIFU og grunnopplæringen, og benyttes til å overføre informasjon mellom IKT-systemer i grunnopplæringen

XSD-skjema for profilen, XML-eksempler og spesifikasjon finnes i mappen *pifu-ims*.

## Hvilken gren av prosjektet skal jeg bruke?
Git opererer med greiner (branches) for forskjellige stadier og oppdelinger av et prosjekt. For de aller fleste av dere, som bare skal bruke skjemaene og eksemplene, er det grenen 'master' dere skal hente filer fra. Der ligger siste gjeldende versjon, for tiden PIFU-IMS 1.1.

For utviklere som skal endre skjemaene eller eksempelfilene er det grenen 'develop-latest' som skal brukes. Fork denne grenen, gjør endringene og kjør en pull-request mot 'develop-latest' her.

I tillegg til disse to hoved-grenene finnes det versjonerings-grener, men de kan de fleste bare se bort i fra.
