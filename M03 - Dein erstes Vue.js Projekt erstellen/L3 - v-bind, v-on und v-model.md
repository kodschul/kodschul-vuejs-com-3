
# Vue.js Schulung

## Erste Interaktionen in Vue.js: v-bind, v-on und v-model

Vue.js ist ein progressives JavaScript-Framework zur Erstellung von Benutzeroberflächen. In dieser Schulung konzentrieren wir uns auf drei wichtige Direktiven: `v-bind`, `v-on`, und `v-model`, die essentiell für die Interaktionen in Vue.js-Anwendungen sind.

### Datenbindung mit v-bind

Die `v-bind` Direktive ermöglicht es uns, die Attribute von HTML-Elementen dynamisch an Daten aus unseren Vue-Instanzen zu binden.

Beispiel:
```html
<div id="app">
  <img v-bind:src="imageUrl" alt="Vue.js Logo">
</div>

<script>
new Vue({
  el: '#app',
  data: {
    imageUrl: 'https://vuejs.org/images/logo.png'
  }
});
</script>
```

### Event-Handling mit v-on

Mit der `v-on` Direktive können wir Vue.js anweisen, auf DOM-Ereignisse zu reagieren, wie z.B. Klicks oder Eingaben.

Beispiel:
```html
<div id="app">
  <button v-on:click="count++">Click me</button>
  <p>{{ count }}</p>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    count: 0
  }
});
</script>
```

### Zweirichtungsbindung mit v-model

Die `v-model` Direktive schafft eine Zweirichtungsbindung auf Formulareingaben, sodass sowohl die Benutzeroberfläche als auch die Daten in Echtzeit aktualisiert werden.

Beispiel:
```html
<div id="app">
  <input v-model="message" placeholder="Enter your message">
  <p>The message is: {{ message }}</p>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    message: ''
  }
});
</script>
```

## Zusammenfassung

Diese Direktiven sind die Grundbausteine für die Interaktion innerhalb von Vue.js-Anwendungen. Indem wir `v-bind` für Datenbindung, `v-on` für Event-Handling und `v-model` für Zweirichtungsbindungen nutzen, können wir reaktive und dynamische Webanwendungen effizient entwickeln.
