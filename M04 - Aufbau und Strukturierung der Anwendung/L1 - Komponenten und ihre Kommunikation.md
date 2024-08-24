
# Vue.js Schulung

## Komponenten und ihre Kommunikation

### Unterschiedliche Arten von Komponenten

Vue.js verwendet eine komponentenbasierte Architektur, die zwischen funktionalen und klassenbasierten Komponenten unterscheidet.

- **Funktionale Komponenten:** Leichtgewichtig und zustandslos, hauptsächlich für die Darstellung von UI-Elementen verwendet.
- **Klassenbasierte Komponenten:** Können Zustände halten und bieten mehr Funktionalitäten durch die Nutzung von Lebenszyklusmethoden.

### Props und Events zur Datenübergabe

In Vue.js werden Daten von einer Elternkomponente zu einer Kindkomponente mittels `props` übergeben, während `events` verwendet werden, um Informationen von Kind- zu Elternkomponenten zu senden.

```javascript
// Parent.vue
<template>
  <Child :user="user" @onUpdate="handleUpdate" />
</template>

<script>
import Child from './Child.vue';

export default {
  components: { Child },
  data() {
    return {
      user: { name: 'Vue Dev' },
    };
  },
  methods: {
    handleUpdate(updatedUser) {
      this.user = updatedUser;
    }
  }
};
</script>

// Child.vue
<template>
  <button @click="updateUser">Update User</button>
</template>

<script>
export default {
  props: ['user'],
  methods: {
    updateUser() {
      this.$emit('onUpdate', { name: 'Updated Vue Dev' });
    }
  }
};
</script>
```

### Zusammenspiel mehrerer Komponenten

Das Zusammenspiel mehrerer Komponenten in Vue.js wird durch die Verwendung von Ereignisbussen oder Zustandsmanagement-Lösungen wie Vuex erleichtert, um Zustände app-weit zu teilen.

## Beispielprojekt: Nachrichtenforum

- UI-Komponenten: Erstellung verschiedener Ansichten für Nachrichten und Kommentare.
- Datenübergabe: Nutzung von Props und Events für die Interaktion zwischen Komponenten.
- Zusammenspiel: Verwendung eines zentralen Zustandsmanagements für Benutzereinstellungen und Nachrichtendaten.

## Fazit

Vue.js ermöglicht eine effiziente und flexible Entwicklung moderner Webanwendungen durch die geschickte Nutzung von Komponenten und deren Kommunikationsmechanismen.
