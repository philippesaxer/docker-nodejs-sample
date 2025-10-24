# Schritte zur Installation des Projekts

> [!IMPORTANT]
> ## Was muss man installiert haben:
> - Git bash
> - Docker-desktop

## Klonen des Repositories
- [x] Als erstes muss man einen Fork vom Repository machen
- [x] Dannach muss man mit **Git bash** es clonen:
* gehe zuerst mit cd _C:/(Ordnername)/docker-nodejs-sample_ in dein Speicherort rein
* dann mit git clone _repository-link_
  
## Installation der notwendigen Pakete
### dependencies
| Paket | Erklärung |
|--------|------------|
| **express** | Ein einfaches Web-Framework für Node.js. Damit kannst du Webseiten und APIs erstellen. |
| **pg** | Programm, mit dem Node.js mit einer PostgreSQL-Datenbank sprechen kann (zum Lesen und Speichern von Daten). |
| **sqlite3** | Ein Datenbankprogramm, das alles in einer Datei speichert. |
| **uuid** | Erstellt automatisch eindeutige IDs. |
| **wait-port** | Wartet, bis ein bestimmter Port bereit ist (nützlich wenn mehrere Programme gleichzeitig starten). |


### devDependencies
| Paket | Erklärung |
|--------|------------|
| **jest** | Ein Test-Tool für Node.js. Damit kannst du automatisch prüfen, ob dein Code richtig funktioniert. |
| **nodemon** | Startet deinen Server automatisch neu, wenn du am Code etwas änderst. Spart Zeit beim Entwickeln. |
| **prettier** | Ein Tool, das deinen Code automatisch schön und einheitlich formatiert. |


### Scripts
| Script | Funktion |
|---------|-----------|
| **prettify** | Formatiert automatisch alle javascript Dateien mit Prettier. |
| **test** | Führt alle Tests mit Jest aus. |
| **dev** | Startet das Projekt im Entwicklungsmodus mit nodemon und aktiviert den Debugger. |

## Docker-Konfiguration und Installation

- Als erstes Docker Desktop herunterladen 

  - Dazu ist das optionale Feature Windows-Subsystem für Linux durch Ausführung der folgenden Anweisung in der Powershell zu aktivieren: 
  _dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart_

  - Direkt danach aktiviert man für WSL2 die Virtual Machine Platform:
  _dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart_

  - Alternativ lassen sich beide Optionen auch in der Anwendung Windows Features auswählen (Windows-Subsystem für Linux und Plattform für virtuelle Computer).

  - Abschliessend ist ein Windows-Neustart erforderlich, WSL1 und das Update auf WSL2 werden dabei eingerichtet.

  - Mit dem Befehl wsl verwaltet man das Subsystem von der Kommandozeile aus. wsl --help listet die verfügbaren Optionen auf. Nach der Aktivierung ist noch WSL1 als Standard   eingestellt, das ändert man mit Hilfe der folgenden Eingabe:
  _wsl --set-default-version 2_

## Starten der Applikation in einem Docker-Container

- Zuerst muss man den Command _docker init_ im Git Bash eingeben
- Dannach stellt es dir fragen und du musst sie so antworten:

  - What application platform does your project use? Node
  - What version of Node do you want to use? 18.0.0
  - Which package manager do you want to use? npm
  - What command do you want to use to start the app: node src/index.js
  - What port does your server listen on? 3000

- Danach muss man _docker compose up --build -d_ eingeben
- Um es zu stoppen den Command _docker compose down_
