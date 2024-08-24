
# Vue.js Schulung: Computed Properties

## Computed Properties: Reaktiv und Effizient

Computed Properties in Vue.js sind eine Art von reaktiven Abhängigkeiten, die es ermöglichen, Datenberechnungen effizient durchzuführen. Sie sind besonders nützlich, wenn eine Eigenschaft von anderen Daten abhängt und nur neu berechnet werden muss, wenn sich diese Daten ändern.

## Grundlagen und Einsatz von Computed Properties

Computed Properties basieren auf einer Funktion, die eine berechnete Eigenschaft zurückgibt. Diese Eigenschaft wird gecacht und nur dann neu berechnet, wenn eine ihrer Abhängigkeiten sich ändert.

```javascript
new Vue({
  el: '#app',
  data: {
    a: 2
  },
  computed: {
    b: function () {
      return this.a + 1;
    }
  }
});
```

## Performance-Optimierung mit Computed Properties

Durch die Verwendung von Computed Properties wird die Performance verbessert, da unnötige Berechnungen vermieden werden. Sie eignen sich hervorragend für komplexe Logik, die mehrfach im Template verwendet wird, ohne dass jedes Mal eine Neuberechnung notwendig ist.

## Unterschied zwischen Computed Properties und Methoden

- **Computed Properties**: Werden nur neu berechnet, wenn ihre Abhängigkeiten sich ändern. Sie sind gecacht und effizienter, wenn die gleichen Ergebnisse oft benötigt werden.
- **Methoden**: Werden immer ausgeführt, wenn sie aufgerufen werden, unabhängig von Änderungen in den Daten.

```javascript
new Vue({
  el: '#app',
  data: {
    a: 5
  },
  computed: {
    b: function () {
      return this.a * 2;
    }
  },
  methods: {
    calculateB: function () {
      return this.a * 2;
    }
  }
});
```

## Fazit

Computed Properties bieten eine leistungsstarke Möglichkeit, die Performance in Vue.js-Anwendungen zu optimieren, indem Berechnungen effizient und nur bei Bedarf durchgeführt werden.
