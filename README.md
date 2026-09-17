# Windows DFIR Lab

### EVTX • Event ID • Timelines • Artefacts Windows • Investigation

Ce dépôt regroupe mes travaux de laboratoire autour du **DFIR Windows** : analyse de journaux, reconstruction chronologique, recherche d'artefacts, validation d'hypothèses et documentation d'une investigation.

Il complète directement mon travail SOC : lorsqu'une alerte ne peut plus être traitée uniquement par le triage, il faut revenir aux traces, reconstruire les faits et comprendre ce qui s'est réellement produit.

> **L'objectif d'une investigation n'est pas de confirmer une intuition, mais de reconstruire les faits à partir de traces vérifiables.**

---

## Objectif du dépôt

Ce laboratoire suit une démarche d'investigation progressive :

```text
Question / alerte initiale
        ↓
Préservation et collecte des éléments utiles
        ↓
Identification des sources de preuve
        ↓
Analyse des journaux et artefacts
        ↓
Construction d'une chronologie
        ↓
Corrélation des événements
        ↓
Validation ou rejet des hypothèses
        ↓
Conclusion documentée
```

L'objectif est de montrer **le raisonnement d'investigation**, pas uniquement le résultat d'un outil.

---

## Outils et axes de travail

| Domaine | Outils / éléments | Finalité |
|---|---|---|
| Journaux Windows | EVTX, Event Viewer | Examiner les événements système et sécurité |
| Event ID | Security, System, PowerShell, Sysmon | Identifier les événements significatifs |
| Analyse rapide | Hayabusa | Détection et timeline sur EVTX |
| Recherche ciblée | Chainsaw | Hunting et règles Sigma sur journaux |
| Analyse Windows | DeepBlueCLI | Repérer certains comportements suspects |
| Collecte / investigation | Velociraptor | Interroger et collecter des artefacts |
| Télémétrie | Sysmon | Obtenir davantage de contexte sur les activités |
| Chronologie | Timeline | Reconstituer l'ordre des événements |

---

## Structure

```text
windows-dfir-lab/
│
├── dfir-fundamentals/
├── windows-event-logs/
├── event-id/
├── sysmon/
├── hayabusa/
├── chainsaw/
├── deepbluecli/
├── velociraptor/
├── windows-artifacts/
├── timelines/
├── investigation-methodology/
└── labs/
```

Chaque rubrique accueillera progressivement des notes, procédures, exemples de commandes, cas de laboratoire et analyses documentées.

---

## Méthode d'investigation

Je souhaite conserver une méthode reproductible pour chaque exercice :

```text
1. Définir la question
2. Identifier les sources de données disponibles
3. Préserver les éléments utiles
4. Examiner les événements pertinents
5. Filtrer le bruit
6. Construire une timeline
7. Corréler plusieurs sources
8. Formuler des hypothèses
9. Chercher les éléments qui confirment OU contredisent ces hypothèses
10. Documenter les faits et les limites
```

Une conclusion DFIR doit distinguer :

- les **faits observés** ;
- les **interprétations** ;
- les **hypothèses encore ouvertes** ;
- les **données manquantes ou limites de l'analyse**.

---

## Ce que je veux démontrer

- comprendre la structure et l'intérêt des journaux Windows ;
- identifier les Event ID importants sans les apprendre hors contexte ;
- filtrer de grandes quantités d'événements ;
- utiliser plusieurs outils sur les mêmes données et comparer leurs résultats ;
- construire une chronologie exploitable ;
- corréler utilisateur, processus, machine, réseau et authentification ;
- éviter de conclure sur la base d'un seul indicateur ;
- documenter une investigation afin qu'une autre personne puisse la relire et la reproduire.

---

## Relation avec le SOC

Le SOC et le DFIR ne sont pas deux blocs isolés :

```text
Télémétrie
    ↓
Détection SOC
    ↓
Alerte
    ↓
Triage
    ↓
Suspicion suffisamment forte
    ↓
Investigation DFIR
    ↓
Reconstruction des faits
    ↓
Conclusion / remédiation / amélioration de la détection
```

Le dépôt SOC associé est disponible ici :

[Cybersecurity SOC Lab](https://github.com/bricehach/cybersecurity-soc-lab)

---

## Cadre d'utilisation

Ce dépôt est consacré à des **laboratoires défensifs, à l'analyse de traces et à l'apprentissage de méthodologies d'investigation**. Les exemples publiés seront issus d'environnements contrôlés, de données de formation ou de jeux de logs adaptés à l'analyse.

---

## Fil conducteur

**Collecter → préserver → analyser → corréler → reconstruire → vérifier → conclure → documenter**
