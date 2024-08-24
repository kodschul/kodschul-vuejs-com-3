
# Vue.js Schulung: REST API & Promises

## Externe Daten integrieren

Die Integration von externen Daten in Vue.js-Anwendungen erfolgt häufig über REST APIs. Dies ermöglicht es den Anwendungen, dynamische Daten von einem Server abzurufen und zu verarbeiten.

## Grundlagen der REST-API-Integration

### Was ist eine REST API?

Eine REST API ist eine Programmierschnittstelle, die die Prinzipien des Representational State Transfer (REST) verwendet. Sie ermöglicht die Kommunikation zwischen der Vue.js-Anwendung und einem Server über HTTP-Anfragen, um Daten abzurufen, zu erstellen, zu ändern oder zu löschen.

### Beispiele für REST API Aufrufe in Vue.js

```javascript
new Vue({
  el: '#app',
  data: {
    items: null
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      fetch('https://api.example.com/data')
        .then(response => response.json())
        .then(data => {
          this.items = data;
        });
    }
  }
});
```

## Arbeiten mit Promises in Vue.js

Promises sind ein wichtiger Bestandteil der asynchronen Programmierung in JavaScript und somit auch in Vue.js. Sie repräsentieren das potenzielle Ergebnis einer asynchronen Operation.

### Beispiel für die Verwendung von Promises

```javascript
methods: {
  fetchData() {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => {
        this.items = data;
      })
      .catch(error => console.error('Error:', error));
  }
}
```

## Axios richtig verwenden: Konfiguration und Best Practices

Axios ist eine populäre Bibliothek, die für HTTP-Anfragen in Vue.js verwendet wird. Sie bietet mehr Funktionen als die `fetch` API und erleichtert das Arbeiten mit Promises.

### Einrichten von Axios in einem Vue.js-Projekt

```javascript
import axios from 'axios';

new Vue({
  el: '#app',
  data: {
    items: null
  },
  created() {
    axios.get('https://api.example.com/data')
      .then(response => {
        this.items = response.data;
      })
      .catch(error => console.error('Error:', error));
  }
});
```

### Best Practices

- Verwenden Sie Interceptors, um Anfragen und Antworten global zu bearbeiten.
- Verwalten Sie die API-Schlüssel und Basis-URLs zentral über die Konfiguration von Axios.
- Behandeln Sie Fehler konsequent und informieren Sie den Benutzer über Netzwerkprobleme.

## Fazit

Die Integration von externen Daten über REST APIs und das Management von asynchronen Anfragen über Promises sind wesentliche Fähigkeiten für moderne Webentwickler, die Vue.js verwenden.
