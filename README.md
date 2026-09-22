# Network Experience 2026–20278

In **Network Experience** bouwt en beheert elke studentengroep een echte dienst voor de opleiding. Jullie werken niet in een wegwerplabo: de VM's draaien op de gedeelde Proxmox-productieomgeving, op node **Smith**. Daarom tellen technische kwaliteit, veiligheid, communicatie en overdraagbaarheid even zwaar als een geslaagde demo.

Jullie krijgen een afgebakende Proxmox-pool, een resourcebudget en rechten om binnen die pool VM's aan te maken en te beheren. De host, storage, uplinks en globale Proxmox-configuratie blijven onder beheer van de opleiding.

## De opdracht

Elke groep krijgt één groot project uit de [projectcatalogus](projecten/README.md). Het resultaat moet bruikbaar zijn voor echte gebruikers en na de oplevering door een volgende groep of de opleiding beheerd kunnen worden.

Ongeacht het gekozen project levert elke groep:

- een gevalideerde behoefteanalyse en afgebakende scope;
- een architectuur-, netwerk- en resourceplan;
- een veilige, reproduceerbare implementatie op Smith;
- monitoring, logging, back-up en een geteste herstelprocedure;
- beheer- en gebruikersdocumentatie;
- een gebruikerstest of realistisch evenement;
- een overdraagbare einddemo en individueel technisch gesprek.

## Platformgrens

```text
Opleidingsnetwerk / internet
            │
            ▼
  gedeelde netwerkdiensten
            │
            ▼
     Proxmox-node Smith
       ├── pool groep-01 → VM's project A
       ├── pool groep-02 → VM's project B
       └── pool groep-…  → VM's project …
```

Studenten beheren uitsluitend hun toegewezen VM's, accounts en applicaties. Wijzigingen aan Smith zelf, gedeelde storage, switching, VLANs, DNS, reverse proxy, firewall of publieke bereikbaarheid verlopen via een change request en moeten vooraf goedgekeurd zijn.

## Starten

1. Lees [Start hier](docs/00-start-here.md), de [praktische afspraken](praktische-afspraken.md) en de [spelregels](spelregels.md).
2. Vul [groepsindeling.md](groepsindeling.md) in.
3. Verken de [projectcatalogus](projecten/README.md) en laat de projectfiche toewijzen of goedkeuren.
4. Werk het [projectcharter](docs/templates/projectcharter-template.md) en het [resourcebudget](docs/templates/resourcebudget-template.md) uit vóór de eerste VM wordt aangemaakt.
5. Maak issues aan voor analyse, ontwerp, realisatie, tests, documentatie en overdracht.

## Handboek

- [Platformarchitectuur](docs/01-labo-architectuur.md)
- [Toegang en accounts](docs/02-toegang-en-accounts.md)
- [Netwerk, firewall en publicatie](docs/03-netwerk-en-firewall.md)
- [Werken op Smith](docs/04-smith-proxmox.md)
- [Netwerk- en dataflowplan](docs/05-netwerkplan.md)
- [Services ontwerpen en beheren](docs/06-services.md)
- [Back-up en restore](docs/07-backup-en-restore.md)
- [Monitoring en logging](docs/08-monitoring-en-logging.md)
- [Security en hardening](docs/09-security-hardening.md)
- [Documentatiestandaard](docs/10-documentatie-template.md)

## Evaluatie in het kort

| Domein | Gewicht |
|---|---:|
| Dienst en technische realisatie | 25% |
| Architectuur, netwerk en security | 20% |
| Automatisering en reproduceerbaarheid | 15% |
| Operations, betrouwbaarheid en herstel | 20% |
| Projectwerking, documentatie en communicatie | 20% |

De volledige rubric staat in [evaluatie.md](evaluatie.md). Een oplossing die alleen tijdens de einddemo werkt, is geen beheerde productiedienst.

## Bewijs en secrets

Deze repo is het technische bewijsdossier van de groep. Gebruik issues, pull requests, diagrammen, testresultaten en beslissingsverslagen. Plaats nooit wachtwoorden, tokens, private keys, recovery codes of ongeschoonde configuratie-exports in Git. Gebruik bijvoorbeeld `<SECRET_IN_VAULT>`.
