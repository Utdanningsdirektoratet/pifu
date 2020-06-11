# PIFU-IMS
PIFU-IMS er en profil av [IMS Enterprise 1.1](http://www.imsglobal.org/enterprise/index.html) tilpasset PIFU og grunnopplæringen. På dette repositoriet forvaltes spesifikasjon og XSD-skjema for profilen samt XML-eksempler.

Gjeldende versjon av PIFU-IMS er 1.3.

[PIFU-IMS 1.3 spesifikasjon](pifu-ims/docs/spesifikasjon.md)

[Endringslogg](pifu-ims/docs/endringslogg.md)

## Hvilken gren av prosjektet skal jeg bruke?
Git opererer med greiner (branches) for forskjellige stadier og oppdelinger av et prosjekt. For de aller fleste av dere, 
som bare skal bruke skjemaene og eksemplene, er det grenen 'master' dere skal hente filer fra. Der ligger siste gjeldende versjon, for tiden PIFU-IMS 1.3.

# PIFU

**Personrelatert informasjonsflyt i utdanning (PIFU) er en norsk standard for utveksling av personrelatert informasjon mellom IKT-systemer i utdanningssammenheng. Standarden skal gjøre det enklere for skoleeiere og leverandører av tjenester til utdanningssektoren å motta og avgi informasjon.**

**For utveksling av personrelatert informasjon**

PIFU er en standard for utveksling av informasjon om personer i utdanningssektoren, og om deres organisasjons- og gruppetilhørighet.

**Mellom IKT-systemer i utdanning**

PIFU er laget for overføring av informasjon mellom IKT-systemer i utdanningssektoren knyttet til identitetsforvaltning.

Standarden er tenkt brukt mellom lokale informasjonskilder (skole- og studieadministrative systemer, lønns- og personalsystemer og lignende), sluttbrukertjenester (læringsplattformer, innholdstjenester, portaler og så videre) og støttetjenester (som brukeradministrative systemer, katalogtjenester og lignende).

Standarden kan også benyttes i forbindelse med nasjonale informasjonskilder og rapporteringssystemer i utdanningssektoren, som opptakssystemer, nasjonale registre med utdanningsrelatert informasjon og lignende.

**En abstrakt informasjonsmodell**

PIFU beskriver en abstrakt informasjonsmodell med ulike objekttyper og en del sentrale informasjonselementer knyttet til disse. 

Objektene som omfattes av standarden er personer, grupper, organisasjonsenheter og relasjoner. En person er assosiert med et sett av informasjon. Det samme gjelder for grupper og organisasjonsenheter. Det kan eksistere relasjoner mellom personer, grupper og organisasjonsenheter, og hver relasjon har en eller flere typer roller.

Kun sentrale informasjonselementer knyttet til objektene er tatt med i modellen. Den har strukturer for å beskrive blant annet navn, identifikatorer og kontaktinformasjon, samt for å utvide settet av tilgjengelige informasjonselementer, sette tidsbegrensning på informasjonsgyldighet og angi at informasjonen ikke skal vises eller spres.

**Med støtte for utvidelser**

Modellen dekker informasjon som antas å kunne være felles for alle brukere av standarden. Ulike skoleslag og andre aktører kan utover dette ha behov for å overføre annen informasjon. Slik informasjon kan gjøres tilgjengelig gjennom et generelt utvidelsesbegrep.

**Uavhengig av teknologi**

Utover at det er snakk om elektroniske systemer forutsetter ikke PIFU noen spesifikk teknologi. Det skal være mulig å utveksle informasjon uavhengig av hvilke produkter som benyttes.

**Ingen overføringsstandard**

Standarden sier ingenting om hvordan data bør overføres fra et system til et annet. Den omfatter ikke selve overføringsmetodene mellom systemer, men forutsetter gjenbruk av tidligere standardiserte overføringsmetoder.

**Standarden bør profileres**

Informasjonsmodellen bør profileres for bruk i ulike segmenter i utdanningssektoren, ved at en gruppe systemeiere går sammen og blir enige om hvilken informasjon de har behov for å overføre mellom sine systemer, hvilke utvidelser som trengs og hvilke vokabularer som skal brukes.

**Deretter avbildes i en overføringsstandard**

En profil kan avbildes i en eksisterende overføringsstandard eller -spesifikasjon. Avbildningen vil bestemme hva det er mulig å overføre mellom systemene, og hvordan slik overføring kan utføres. Flere typer overføringsmetoder bør støttes, for eksempel overføring av hele datamengden, endringer siden forrige oppdatering, og øyeblikkelige endringsmeldinger.

**Før den implementeres i systemene**

Når en profil av PIFU er avbildet i en overføringsstandard kan PIFU implementeres i systemene profilen er tenkt brukt for. PIFU kan implementeres i eksisterende og kommende overføringsstandarder eller -spesifikasjoner.

**Forvaltes av Standard Norge**

Standarden er utarbeidet av en komité opprettet av Standard Norge, og forvaltes av Standard Norge.

**Målet er færre formater**

PIFU er et verktøy skoleeiere og leverandører av tjenester til utdanningssektoren kan velge å bruke. Når skoleeiere og tjenesteleverandører blir enige om hvordan de ønsker å bruke PIFU kan de slippe unna med færre formater i bruk og mindre grad av skreddersøm i grensesnitt mellom systemer.

**Informasjonsmodell og eksempelavbilding**

Informasjonsmodellen illustrerer hvilke generelle objekttyper, informasjonselementer og relasjoner som kan forekomme i PIFU. Modellen fremstilles ved hjelp av et UML-klassediagram.

I et vedlegg til standarden gjengis et sett med eksempeldata, som i det påfølgende vedlegget avbildes i IMS Enterprise. IMS Enterprise er en av flere spesifikasjoner PIFU kan avbildes i, og standarden er ikke begrenset til denne avbildningen. IMS Enterprise er relativt begrenset i forhold til en del informasjon, men har mekanismer for utvidelse slik at hele eksempelsettet med data lar seg avbilde.

**Overføringsspesifikasjonen PIFU-IMS**

Det er laget en overføringsspesifikasjon som avbilder PIFU i IMS Enterprise og som benyttes for å overføre informasjon mellom systemer i grunnopplæringen.
