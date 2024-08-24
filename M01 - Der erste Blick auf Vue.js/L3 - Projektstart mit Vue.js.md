
# Vue.js Schulung: Projektstart mit Vue.js

## Dein erster Schritt: Einführung in Vue.js

Vue.js ist ein progressives JavaScript-Framework, das verwendet wird, um Benutzeroberflächen zu erstellen. Im Gegensatz zu anderen monolithischen Frameworks ist Vue von Grund auf darauf ausgelegt, schrittweise adoptierbar zu sein.

## Die Vue.js CLI (create-vue) im Einsatz

Die Command Line Interface (CLI) von Vue.js, `create-vue`, ist ein leistungsstarkes Tool, das es Entwicklern ermöglicht, schnell neue Projekte zu starten.

### Installation der CLI
```bash
npm install -g @vue/cli
# oder
yarn global add @vue/cli
```

### Erstellen eines neuen Projekts
```bash
vue create mein-projekt
```
Dieser Befehl führt Sie durch die Erstellung eines neuen Vue.js-Projekts mit einer Reihe von Optionen zur Konfiguration.

## Node Paketmanager (yarn vs. npm) – Was nutzen und warum?

### npm
- **npm** ist der Standard-Paketmanager für JavaScript und kommt mit Node.js.
- Bietet eine große Sammlung von Paketen.
- Verwendet `package-lock.json` zur Sicherung der Versionen.

### yarn
- **yarn** bietet schnelle Installationen durch Caching und parallele Ausführungen.
- Verwendet `yarn.lock` zur präzisen Versionssicherung.
- Einfachere Syntax für einige Befehle.

Je nach Projektanforderungen und persönlichen Präferenzen können Entwickler zwischen npm und yarn wählen.

## Erstellung eines ersten Vue.js Projekts

Nach der Einrichtung Ihrer Entwicklungsumgebung können Sie ein erstes einfaches Projekt starten.

### Projektstruktur
Ein typisches Vue.js-Projekt könnte folgendermaßen aussehen:
```
mein-projekt/
|-- public/
|-- src/
|   |-- assets/
|   |-- components/
|   |-- App.vue
|   |-- main.js
|-- package.json
```

### Hauptkomponenten
- `main.js`: Der Einstiegspunkt, der das Vue-Instance erstellt.
- `App.vue`: Eine einzelne Datei-Komponente, die die Haupt-App-Komponente darstellt.

```javascript
// main.js
import Vue from 'vue';
import App from './App.vue';

new Vue({
  render: h => h(App),
}).$mount('#app');
```

## Fazit

Vue.js bietet eine flexible Architektur, die es ideal für Projekte jeder Größe macht. Durch das Erlernen dieser Tools und Techniken sind Sie gut gerüstet, um effektive und reaktionsfähige Webanwendungen zu entwickeln.
