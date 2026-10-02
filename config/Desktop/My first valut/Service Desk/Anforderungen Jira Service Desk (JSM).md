## Version
1.0

## Zweck

Definition der Anforderungen für den zukünftigen ATT Service Desk auf Basis von Jira Service Management.

Dieses Dokument ergänzt das Asset- und CMDB-Konzept und beschreibt die Serviceprozesse, den Servicekatalog sowie die Ticketarchitektur.

---

## Zielsetzung

Der Jira Service Desk soll als zentrale Plattform für die Bearbeitung sämtlicher Serviceanfragen, Störungen, Genehmigungen und Asset-Lifecycle-Prozesse dienen.

### Ziele

- Einheitliche Serviceplattform
- Standardisierte Prozesse
- Transparente Bearbeitung
- Nachvollziehbarkeit
- SLA-Steuerung
- Self Service
- Wissensmanagement
- Integration zur CMDB (Jira Assets)

---

## Zielarchitektur

```text
Benutzer
    |
    v

JSM Portal
    |
    +------------------+
    |                  |
    v                  v

Service Requests   Incidents

    |
    v

Jira Service Management

    |
    +--------------------+
    |                    |
    v                    v

Jira Assets         Confluence
(CMDB)             (Knowledge Base)

    |
    v

Power BI
```

---

# Tickettypen

## Incident

### Zweck

Wiederherstellung eines gestörten Services.

### Beispiele

- Notebook defekt
- Drucker funktioniert nicht
- Netzwerkproblem
- Smartphone beschädigt
- WLAN-Ausfall

### Workflow

```text
Neu
→ In Bearbeitung
→ Gelöst
→ Geschlossen
```

---

## Service Request

### Zweck

Anforderung eines Standardservices.

### Beispiele

- Neues Notebook
- Zusätzlicher Monitor
- Neues Headset
- Passwort Reset
- Software Installation
- VPN Zugang

### Workflow

```text
Neu
→ Genehmigt
→ In Umsetzung
→ Erledigt
```

---

## Asset Lifecycle

### Zweck

Verwaltung aller Asset-Prozesse.

### Beispiele

- Wareneingang
- Ausgabe
- Rückgabe
- Inventur
- Reparatur
- Austausch
- Aussonderung

### Workflow

```text
Beantragt
→ Freigegeben
→ Durchgeführt
→ Abgeschlossen
```

---

## Change

### Zweck

Kontrollierte Änderungen an Produktivsystemen.

### Beispiele

- Firewall Änderung
- Router Tausch
- Netzwerk Erweiterung
- Notebook Modellwechsel

### Typen

- Standard Change
- Normal Change
- Emergency Change

---

## Problem

### Zweck

Beseitigung der Ursache wiederkehrender Störungen.

### Beispiele

- Serienfehler bei Geräten
- Wiederkehrende WLAN-Probleme
- Wiederkehrende Druckerausfälle

---

## Task

### Zweck

Interne Arbeitsaufgaben.

### Beispiele

- Dokumentation aktualisieren
- Inventar bereinigen
- Asset prüfen

---

# Servicekatalog

## Arbeitsplatz Service

### Services

- Notebook
- Monitor
- Dock
- Headset
- Tastatur
- Maus

**Service Owner:** ATT Workplace Team

---

## Mobile Service

### Services

- Smartphone
- Tablet
- SIM-Karte
- Tarifwechsel

**Service Owner:** ATT Mobile Team

---

## Netzwerk Service

### Services

- Netzwerkanschluss
- WLAN
- VPN

**Service Owner:** ATT Netzwerk Team

---

## Druckservice

### Services

- Drucker
- Scanner
- Verbrauchsmaterial

---

## Software Service

### Services

- Office
- Visio
- Adobe
- Spezialsoftware

---

## Fahrzeug / AMOB Service

### Services

- Toughbook
- Fahrzeugdrucker
- Scanner
- Router
- Smartphone

---

# Reporting

## Benutzer Dashboard

### Zweck

Transparenz für den Anforderer.

### Inhalte

- Meine offenen Tickets
- Status meiner Tickets
- Meine Genehmigungen
- Meine Assets
- Fällige Rückgaben
- Letzte Aktivitäten

---

## Service Desk Dashboard

### Zweck

Operative Steuerung des Tagesgeschäfts.

### Inhalte

- Meine offenen Tickets
- Tickets nach Priorität
- Überfällige Tickets
- SLA-Verletzungen
- Tickets ohne Bearbeiter
- Heute fällige Aufgaben

---

## Team Dashboard (Daily / Weekly)

### Zweck

Überblick über die Gesamtauslastung des Teams.

### Inhalte

- Alle offenen Tickets
- Neue Tickets
- Tickets nach Status
- Tickets nach Priorität
- SLA-Verletzungen
- Tickets pro Team
- Ticketalter (Aging)
- Eskalationen

---

## Asset Dashboard

### Zweck

Transparenz über Bestand und Status aller Assets.

### Inhalte

- Assetbestand gesamt
- Bestand nach Standort
- Bestand nach Assettyp
- Geräte in Reparatur
- Geräte ohne Zuordnung
- Garantieabläufe
- Ausgesonderte Assets
- Inventurstatus

---

## Management Dashboard

### Zweck

Steuerung und KPI-Übersicht.

### Inhalte

- Ticketvolumen
- SLA-Erfüllung
- Backlog-Entwicklung
- Assetbestand
- Inventurfortschritt
- Geräte in Reparatur
- Top Ticketkategorien
- Risiken und Eskalationen

---

# Optionale Dashboards

## Inventur Dashboard

- Inventurquote pro Standort
- Nicht bestätigte Assets
- Inventurdifferenzen
- Letzte Inventur
- Fehlende Assets

---

## Beschaffungs Dashboard

- Offene Beschaffungen
- Genehmigungen ausstehend
- Offene Bestellungen
- Lieferstatus
- Beschaffungsvolumen

---

## Lifecycle Dashboard

- Neu beschaffte Assets
- Aktive Assets
- Reparaturen
- Austauschgeräte
- Aussonderungen
- Lifecycle-Kosten

---

## Lizenz Dashboard

- Lizenzbestand
- Lizenznutzung
- Freie Lizenzen
- Ablaufende Lizenzen
- Compliance-Status

---

## Discovery / CMDB Dashboard

- Durch checkmk erkannte Geräte
- Nicht zugeordnete Geräte
- CMDB-Abdeckung
- Discovery-Fehler
- Veraltete Konfigurationen