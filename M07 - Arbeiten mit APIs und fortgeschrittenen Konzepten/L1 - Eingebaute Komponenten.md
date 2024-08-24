
# Vue.js Schulung: Eingebaute Komponenten

## Überblick über eingebaute Komponenten in Vue.js

Vue.js bietet eine Vielzahl von eingebauten Komponenten, die das Erstellen von interaktiven und reaktiven Webanwendungen vereinfachen. Diese Komponenten sind in der Grundbibliothek enthalten und können direkt in jedem Vue-Projekt verwendet werden.

## Nutzung und Anpassung dieser Komponenten

Die Nutzung dieser eingebauten Komponenten in Vue.js ist einfach und erfordert nur das Importieren und Registrieren in deiner Vue-Instanz oder in deinen Komponenten. Anpassungen können durch Props, Events und Slots erfolgen, um die Funktionalität und das Aussehen nach Bedarf zu ändern.

### Beispiel: <transition> Komponente

Die <transition> Komponente ermöglicht es, einfache Übergangsanimationen für jedes Element zu definieren:

```vue
<template>
  <div>
    <button @click="show = !show">Toggle</button>
    <transition name="fade">
      <p v-if="show">Hello Vue.js!</p>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false
    };
  }
};
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>
```

### Beispiel: <keep-alive> Komponente

Mit <keep-alive> können Komponenten im Speicher gehalten werden, um schnelleres Rendern und Zustandserhaltung bei erneutem Rendern zu ermöglichen:

```vue
<template>
  <keep-alive>
    <component :is="currentView">
      <!-- Komponenten, die gewechselt werden, hier einfügen -->
    </component>
  </keep-alive>
</template>

<script>
export default {
  data() {
    return {
      currentView: 'MyComponent'
    };
  }
};
</script>
```

## Praktische Anwendung

Die praktische Anwendung dieser Komponenten umfasst verschiedene Aspekte der Webentwicklung, einschließlich der Verbesserung der Benutzererfahrung durch Animationen, Zustandserhaltung und Optimierung der Leistung.

## Fazit

Eingebaute Komponenten in Vue.js bieten leistungsstarke Werkzeuge zur Verbesserung und Personalisierung von Webanwendungen. Durch die effektive Nutzung dieser Komponenten können Entwickler komplexe Features mit weniger Aufwand implementieren.
