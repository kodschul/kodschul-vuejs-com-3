
# Vue.js Schulung - Watcher

## Watcher: Reaktive Überwachung deiner Daten

Watcher in Vue.js sind eine Möglichkeit, auf Änderungen an den Daten einer Komponente zu reagieren. Sie erlauben es dir, eine Callback-Funktion auszuführen, wenn sich spezifische Daten ändern. Dies ist besonders nützlich in Situationen, in denen du auf Datenänderungen reagieren musst, die auf komplexe Weise oder durch externe Einflüsse erfolgen.

## Wann und warum Watcher nutzen?

Watcher sollten genutzt werden, wenn du eine spezifische Reaktion auf Datenänderungen benötigst, die nicht direkt durch Methoden oder berechnete Eigenschaften (computed properties) abgedeckt werden können. Sie sind ideal für:

- Durchführung von asynchronen Operationen als Reaktion auf Datenänderungen.
- Ausführliche Berechnungen oder Prozesse, die nicht in berechneten Eigenschaften sinnvoll sind.
- Überwachung von externen Datenquellen.

## Beispiele für den Einsatz von Watchern

### Beispiel 1: Formatierung einer Telefonnummer

```javascript
new Vue({
  el: '#app',
  data: {
    phoneNumber: ''
  },
  watch: {
    phoneNumber(newVal) {
      this.phoneNumber = newVal.replace(/\D/g, '').replace(/(\d{3})(\d{3})(\d{4})/, '$1-$2-$3');
    }
  }
});
```

### Beispiel 2: Laden von Daten basierend auf einer Nutzerauswahl

```javascript
new Vue({
  el: '#example',
  data: {
    userId: 1,
    user: null
  },
  watch: {
    userId(newVal, oldVal) {
      this.fetchUserData(newVal);
    }
  },
  methods: {
    fetchUserData(id) {
      axios.get(`https://api.example.com/users/${id}`)
           .then(response => this.user = response.data)
           .catch(error => console.error('Error fetching data', error));
    }
  }
});
```

## Fehlervermeidung und Best Practices

### 1. Vermeidung von übermäßigem Gebrauch

Watcher können leicht überbeansprucht werden. Oftmals können Methoden oder berechnete Eigenschaften das gleiche Ergebnis auf eine effizientere Weise erzielen.

### 2. Trennung von Anliegen

Halte die Logik innerhalb von Watchern so spezifisch und isoliert wie möglich. Dies erleichtert das Testen und die Wartung.

### 3. Sauberes Aufheben von Side-Effects

Stelle sicher, dass alle Side-Effects, die durch einen Watcher eingeführt werden (z.B. Event Listener oder Timers), ordnungsgemäß aufgehoben werden, wenn die Komponente zerstört wird.

## Fazit

Watcher sind ein leistungsstarkes Werkzeug in Vue.js, das es ermöglicht, auf Änderungen in den Applikationsdaten effektiv zu reagieren. Ihre richtige Nutzung kann die Anwendung effizienter und reaktiver machen.
