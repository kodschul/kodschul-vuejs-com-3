
# Vue.js Schulung - Komponenten

## Komponenten: Die Bausteine deiner Anwendung

Vue.js Komponenten sind wiederverwendbare Instanzen mit einem Namen und enthalten alles, was nötig ist, um ein Stück der Benutzeroberfläche darzustellen.

## Erstellung und Nutzung von Vue-Komponenten

Komponenten in Vue.js werden typischerweise in einzelne Dateien (.vue) definiert, die drei Sektionen enthalten: Template, Script und Style. Hier ein einfaches Beispiel einer Komponente:

```html
<!-- MyComponent.vue -->
<template>
  <div>
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Hello Vue!'
    };
  }
}
</script>

<style scoped>
h1 {
  color: blue;
}
</style>
```

## Datenübergabe zwischen Komponenten

Daten werden in Vue.js oft von einer Elternkomponente zu einer Kindkomponente übergeben. Dies geschieht über Props.

```html
<!-- ParentComponent.vue -->
<template>
  <div>
    <child-component :user="user"/>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      user: {
        name: 'John Doe',
        age: 30
      }
    };
  }
}
</script>
```

## Templates und erste Logik

Das Template einer Vue-Komponente definiert das HTML-Markup, das gerendert werden soll, und kann Vue-spezifische Direktiven wie `v-if`, `v-for` und `v-model` verwenden, um Logik direkt im Markup zu integrieren.

```html
<template>
  <div>
    <p v-if="user.age > 18">{{ user.name }} is an adult.</p>
    <p v-else>{{ user.name }} is not an adult.</p>
  </div>
</template>
```

## Fazit

Vue-Komponenten sind leistungsstarke Werkzeuge zur Erstellung modularer und wartbarer Webanwendungen. Durch das Verständnis der Grundlagen der Komponentenerstellung und -nutzung, Datenübergabe und Templating-Logik können Entwickler effizient interaktive Anwendungen entwickeln.
