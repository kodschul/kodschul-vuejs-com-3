
# Vue.js Schulung

## Conditional Rendering: Steuere dein UI

Vue.js bietet leistungsfähige Direktiven, um das Rendern von Komponenten im User Interface (UI) bedingt zu steuern. Diese Methoden ermöglichen eine dynamische und bedingte Darstellung von Inhalten basierend auf den Daten und Zuständen der Anwendung.

### Bedingtes Rendern mit v-if und v-else

Die `v-if` Direktive in Vue.js wird verwendet, um Teile des UI nur dann zu rendern, wenn eine bestimmte Bedingung wahr ist. Wenn die Bedingung falsch ist, kann alternativ `v-else` verwendet werden.

```html
<template>
  <div>
    <h1 v-if="loggedIn">Willkommen zurück!</h1>
    <h1 v-else>Bitte logge dich ein.</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loggedIn: false
    }
  }
}
</script>
```

### Schleifen und Iterationen mit v-for

Mit der `v-for` Direktive können Listen von Elementen gerendert werden. Es ist nützlich für das Erstellen von wiederholbaren Komponenten wie Listen, Tabellen oder jeder Gruppe von ähnlichen Objekten.

```html
<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      {{ item.text }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, text: 'Vue.js lernen' },
        { id: 2, text: 'Conditional Rendering verstehen' },
        { id: 3, text: 'v-for nutzen' }
      ]
    }
  }
}
</script>
```

### Dynamisches Rendering basierend auf Daten

Vue.js ermöglicht es, UI-Komponenten dynamisch zu rendern, basierend auf den aktuellen Daten und Zuständen der Anwendung. Dies kann durch eine Kombination von `v-if`, `v-for` und anderen reaktiven Datenbindungen erreicht werden.

```html
<template>
  <div>
    <input v-model="searchQuery" placeholder="Suche...">
    <div v-for="item in filteredItems" :key="item.id">
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: '',
      items: [
        { id: 1, name: 'Tomate' },
        { id: 2, name: 'Kartoffel' },
        { id: 3, name: 'Karotte' }
      ]
    }
  },
  computed: {
    filteredItems() {
      return this.items.filter(item => item.name.includes(this.searchQuery));
    }
  }
}
</script>
```

## Fazit

Vue.js bietet einfache und effiziente Werkzeuge für das bedingte und dynamische Rendering von UI-Komponenten, was die Erstellung von interaktiven und reaktiven Anwendungen vereinfacht.
