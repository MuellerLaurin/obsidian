# PowerToys - Kurzanleitung

## 1. Arbeitsbereiche (Workspaces)

Mit Arbeitsbereichen können häufig benötigte Anwendungen und Fenster in einer definierten Anordnung gespeichert und später mit einem Klick wieder geöffnet werden. Das eignet sich ideal für standardisierte Arbeitsplätze oder wiederkehrende Tätigkeiten.

### Arbeitsbereich erstellen

1. Gewünschte Anwendungen und Fenster öffnen.
2. Tastenkombination drücken:

   ```text
   STRG + WIN + Ö
   ```

3. **Apps anordnen** auswählen.
4. Auf **Capture** klicken.
5. Arbeitsbereich benennen und speichern.

### Optionen

#### Desktop-Verknüpfung erstellen

Erstellt eine Verknüpfung auf dem Desktop, über die der Arbeitsbereich jederzeit gestartet werden kann. Alle im Arbeitsbereich gespeicherten Anwendungen werden automatisch geöffnet und angeordnet.

#### In Taskleiste anheften

Die erstellte Desktop-Verknüpfung kann per Drag & Drop in die Taskleiste gezogen werden. Dadurch lässt sich der komplette Arbeitsbereich mit einem Klick starten.

💡 Ideal für häufig genutzte Arbeitsplätze wie Service Desk, Monitoring, Administration oder Projektarbeit.

---

## 2. Always On Top

Mit "Always On Top" bleibt ein Fenster dauerhaft im Vordergrund, auch wenn andere Anwendungen geöffnet werden. Das ist praktisch für Notizen, Teams-Chats, Monitoring-Fenster oder Anleitungen.

### Aktivieren

1. Gewünschtes Fenster auswählen.
2. Tastenkombination drücken:

   ```text
   STRG + WIN + T
   ```

3. Das Fenster bleibt nun immer im Vordergrund.

Zum Deaktivieren dieselbe Tastenkombination erneut drücken.

💡 Nützlich, wenn Informationen aus einem Fenster laufend benötigt werden, während in anderen Anwendungen gearbeitet wird.

---

## 3. Vorhandene Fenster verschieben

Bereits geöffnete Fenster können jederzeit neu angeordnet oder in vorbereitete Layouts verschoben werden. Dadurch lassen sich Arbeitsplätze schnell an unterschiedliche Aufgaben anpassen.

### Fenster neu anordnen

1. Fenster per Drag & Drop verschieben.
2. Optional die Fenster in FancyZones-Bereiche ziehen, um sie automatisch einzurasten.
3. Die neue Anordnung kann bei Bedarf wieder als Arbeitsbereich gespeichert werden.

💡 Besonders hilfreich bei mehreren Explorer-, Edge-, Outlook- oder Teams-Fenstern.

### Fenster einem gespeicherten Arbeitsbereich zuordnen

Wird ein Arbeitsbereich gestartet und die Anwendung ist bereits geöffnet, kann das vorhandene Fenster automatisch an die gespeicherte Position verschoben werden. So bleibt die gewünschte Anordnung erhalten, ohne zusätzliche Fenster öffnen zu müssen.

# Weitere nützliche PowerToys-Funktionen

## FancyZones

Mit FancyZones können Bereiche am Bildschirm definiert werden, in die Fenster automatisch einrasten. Das funktioniert deutlich flexibler als die Standard-Snap-Funktion von Windows.

### Nutzung

1. PowerToys öffnen
2. FancyZones auswählen
3. Layout erstellen oder Vorlage verwenden
4. Fenster mit gedrückter SHIFT-Taste in die gewünschte Zone ziehen

💡 Ideal bei UltraWide-Monitoren wie dem Dell U3425WE.

---

## PowerToys Run

Eine schnelle Such- und Startleiste für Programme, Dateien, Ordner und Befehle.

### Tastenkombination

```text
ALT + LEERTASTE
```

### Beispiele

```text
notepad
control
services.msc
cmd
```

💡 Oft schneller als das Windows-Startmenü.

---

## Text Extractor

Texte direkt aus Bildern, PDFs oder Anwendungen auslesen.

### Tastenkombination

```text
WIN + SHIFT + T
```

Anschließend den Bereich markieren.

💡 Perfekt zum Kopieren von Fehlermeldungen, Seriennummern oder Texten aus Screenshots.

---

## Mouse Highlighter

Markiert Mausklicks optisch auf dem Bildschirm.

### Aktivieren

```text
WIN + SHIFT + H
```

💡 Sehr hilfreich bei Schulungen, Präsentationen oder Remote-Support.

---

## Color Picker

Farben von beliebigen Stellen am Bildschirm aufnehmen.

### Tastenkombination

```text
WIN + SHIFT + C
```

💡 Praktisch für SharePoint-, Power Apps- oder Webseiten-Designs.

---

## Bildschirm-Lineal (Screen Ruler)

Misst Größen und Abstände direkt auf dem Bildschirm.

### Tastenkombination

```text
WIN + SHIFT + M
```

💡 Hilfreich beim Erstellen von Grafiken, SharePoint-Seiten oder Power Apps.

---

## Datei-Vorschau im Explorer

Erweitert den Explorer um Vorschauen für zusätzliche Dateitypen.

### Beispiele

- SVG
- Markdown (.md)
- PDF
- Code-Dateien

Vorschaufenster aktivieren:

```text
ALT + P
```

💡 Besonders nützlich beim Arbeiten mit Obsidian-Markdown-Dateien.

---

## Hosts File Editor

Bearbeiten der lokalen Hosts-Datei ohne Notepad als Administrator starten zu müssen.

### Typische Verwendung

```text
10.16.51.75  testserver.oeamtc.at
```

💡 Praktisch für Tests, Migrationen und Troubleshooting.

---

## Quick Accent

Schnelles Einfügen von Sonderzeichen.

### Nutzung

Taste gedrückt halten:

```text
a
```

Dann erscheinen:

```text
ä à á â
```

💡 Nützlich für deutschsprachige Dokumentation und internationale Namen.

---

## Advanced Paste

Texte automatisch umwandeln.

### Tastenkombination

```text
WIN + SHIFT + V
```

Mögliche Formate:

- Plain Text
- JSON
- Markdown
- AI-gestützte Umwandlungen

💡 Super für Obsidian, OneNote und technische Dokumentationen.

---

## File Locksmith

Zeigt an, welcher Prozess eine Datei sperrt.

### Nutzung

Rechtsklick auf Datei:

```text
Mit File Locksmith entsperren
```

💡 Spart viel Zeit bei Fehlermeldungen wie:
"Datei wird von einem anderen Prozess verwendet."

---

## Command Not Found

Leitet unbekannte Befehle in PowerShell automatisch auf Winget-Vorschläge um.

### Beispiel

```powershell
terraform
```

PowerToys schlägt automatisch die Installation vor.

💡 Sehr praktisch auf Admin- und Entwickler-PCs.