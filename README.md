# Lead Check Page

#### Repository klonen
```bash
git clone https://github.com/FarbKlexx/landing-page-template.git
```

## Installation & Setup (Vue/Vuetify Frontend)

Das Frontend basiert auf **Vue 3**, **Vuetify 3** und **Vite**.  
Alle benötigten Abhängigkeiten werden automatisch anhand der [`package.json`](./package.json) installiert.

### Voraussetzungen
- **[Node.js 18+](https://nodejs.org/en/download)**

---

### Projekt starten

#### 1. In den Frontend-Ordner wechseln
```bash
cd frontend
```

#### 2. Alle npm-Dependencies installieren
```bash
npm install
```

#### 3. Entwicklungsserver starten
```bash
npm run dev
```


## Installation & Setup (Maven/Spring Boot Backend)

Dieses Projekt verwendet **Maven** als Build- und Dependency-Management-Tool.  
Alle benötigten Abhängigkeiten werden automatisch anhand der [`pom.xml`](./pom.xml) installiert.

### Voraussetzungen
- **[Java 21+](https://www.oracle.com/de/java/technologies/downloads/)**
- **[Maven 3.9+](https://maven.apache.org/install.html)**
- Internetzugang (für den ersten Download der Dependencies)

---

### Projekt bauen & starten

#### 1. In den Backend-Ordner wechseln
```bash
cd backend
```

#### 2. Alle Dependencies aus der pom.xml herunterladen und Projekt bauen
```bash
mvn clean install
```

#### 3. Anwendung starten
```bash
mvn spring-boot:run
```

#### 4. H2 Entwicklungs-Datenbank aufrufen
http://localhost:8080/h2-console/login.do

#### 5. SwaggerUI API Dokumentation aufrufen
http://localhost:8080/swagger-ui/index.html
