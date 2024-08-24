
# Vue.js Schulung

## Installation und Projektaufsetzung: Schritt für Schritt

### Installation von Vue.js und Einrichtung eines Projektes

#### Schritt 1: Node.js installieren
Bevor Sie Vue.js installieren, stellen Sie sicher, dass Node.js auf Ihrem System installiert ist. Besuchen Sie [Node.js](https://nodejs.org/) und laden Sie die neueste Version herunter.

#### Schritt 2: Vue CLI installieren
Vue CLI ist ein mächtiges Tool, das Ihnen hilft, Vue-Projekte schnell aufzusetzen. Installieren Sie es global über npm:

```bash
npm install -g @vue/cli
```

#### Schritt 3: Ein neues Projekt erstellen
Erstellen Sie ein neues Vue-Projekt mit dem folgenden Befehl:

```bash
vue create mein-vue-projekt
```

Folgen Sie den Anweisungen im CLI, um die gewünschten Features auszuwählen.

### Überblick über die Projektstruktur

Nach der Erstellung Ihres Projekts wird folgende Struktur generiert:

- **node_modules/**: Enthält alle Pakete und Abhängigkeiten.
- **public/**: Verzeichnis für statische Assets wie das Haupt-HTML.
- **src/**: Hauptverzeichnis für Vue-Komponenten.
  - **assets/**: Bilder und andere Ressourcen.
  - **components/**: Wiederverwendbare Vue-Komponenten.
  - **App.vue**: Haupt-Root-Komponente.
  - **main.js**: Einstiegspunkt der Anwendung.

### Einbinden von Abhängigkeiten und ersten Libraries

#### Schritt 1: Abhängigkeiten hinzufügen
Um eine Library wie Axios für HTTP-Anfragen zu installieren, verwenden Sie npm:

```bash
npm install axios
```

#### Schritt 2: Library in Ihrem Projekt verwenden
Binden Sie die installierte Library in Ihrer Komponente ein:

```javascript
<script>
import axios from 'axios';

export default {
  methods: {
    fetchData() {
      axios.get('https://api.example.com/data')
        .then(response => {
          this.data = response.data;
        })
        .catch(error => console.error('Error:', error));
    }
  }
}
</script>
```

## Fazit

Mit diesen Schritten haben Sie eine solide Grundlage für die Entwicklung von Vue.js-Anwendungen. Die effektive Nutzung der Vue CLI und das Verständnis der Projektstruktur sind entscheidend für den Erfolg Ihrer Projekte.
