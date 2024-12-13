# min-side-brukervarsel-topic

Repo med configurasjon for hvem som kan produsere og konsumere fra åpent brukervarsel-topic

Mer info i [dokumentasjonen](https://navikt.github.io/tms-dokumentasjon/varsler/).

## Topics og hensikt

- `aapen-brukervarsel-v1` er ment for å produsere/inaktivere eller på andre vis endre varsler.
- `aapen-varsel-hendelse-v1` kan brukes av produsenter for å lytte på f. eks. når bruker inaktiverer en beskjed, eller status på ekstern varsling.

## Hvordan få tilgang til topic?

**For skrivetilgang**

```
        - team: myTeam
          application: myApplication
          access: write 
```
**For lesetilgang**

```
        - team: myTeam
          application: myApplication
          access: read 
```

## Hvordan bumper jeg topic-en?

1. Opprett en ny `.yaml` fil i ønsket miljø (`dev-gcp/prod-gcp`). Bump versjonsnummer i filnavnet og topic-navnet inne i filen.
2. Oppdater workflow til å peke på de nye `.yaml` filene du akkurat opprettet.  

 ## Sletting av topic?
1. Ved å sette `removeDataWhenResourceIsDeleted` til `true` kan vi slette topic og all data som ligger på den.  

    ```
      annotations:
            kafka.nais.io/removeDataWhenResourceIsDeleted: "true"
    ```
2. Deploy topic
3. Slett filen 

# Henvendelser

Spørsmål knyttet til koden eller prosjektet kan rettes mot https://github.com/orgs/navikt/teams/min-side


## For NAV-ansatte

Interne henvendelser kan sendes via Slack i kanalen #brukernotifikasjoner.
