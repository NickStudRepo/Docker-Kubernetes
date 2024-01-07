## Aufgabe "react-express-mongodb"

### Beschreibung

Der Ordner react-express-mongodb enthält ein fertiges Code-Projekt. Wie der Name schon sagt, besteht das Projekt aus drei Services: Einem Frontend mit React, einem Backend mit Express und einer MongoDB Datenbank. Ziel des Arbeitsblattes ist es, die Services zu containerisieren und die gesamte Anwendung mit dem Befehl "docker-compose up" zu starten.

### Aufgabe 1: Dockerfiles erstellen

#### Frontend (React-Service)

Erstelle ein Dockerfile für den React-Service. ([Frontend Dockerfile](./react-express-mongodb/frontend/Dockerfile))

#### Backend (Express-Service)

Erstelle ein Dockerfile für den Express-Service. ([Backend Dockerfile](./react-express-mongodb/backend/Dockerfile))

### Aufgabe 2: Docker Compose Datei erstellen

Erstelle eine Docker Compose Datei, um alle Services als Container zu starten. ([docker-compose.yaml](./react-express-mongodb/docker-compose.yaml) )

Hinweise:
- Dazu müssen 3 Services definiert werden.
- Die MongoDB-Datenbank ist standardmäßig über Port 27017 erreichbar (Expose Port).
- Die MongoDB benötigt ein Volume, um Daten persistent zu speichern. "./data:/data/db"
- Der Backend-Service ist auf Port 3000 erreichbar (Expose Port).
- Das Frontend mapped seinen Port 3000 nach außen, um außerhalb des Containers erreichbar zu sein.



TODOOOOO!!! wie viel Hilfe?
Wo sag frontend wie backend ansprechen??? wo im code?
Wo requirements für alle übungen.