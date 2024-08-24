
# Vue.js Schulung: Formulare erstellen und handhaben

## Grundlagen der Formularerstellung in Vue.js

Vue.js erleichtert die Erstellung und Handhabung von Formularen durch sein reaktives Datenbindungsmodell. Ein einfaches Formular in Vue.js kann mit der Nutzung von `v-model` schnell aufgesetzt werden, um eine Zwei-Wege-Datenbindung zu erreichen.

## Nutzung von v-model für Formularelemente

`v-model` ist eine Direktive in Vue.js, die verwendet wird, um Formulardaten mit dem Datenmodell der Vue-Instanz zu binden. Es sorgt für eine automatische Synchronisierung der Formulareingaben mit den Daten.

### Beispiel: Einfaches Texteingabeformular

```html
<template>
  <div>
    <input v-model="message" placeholder="Geben Sie etwas ein">
    <p>Die Eingabe ist: {{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: ''
    }
  }
}
</script>
```

## Formular-Events und -Validierung

Formular-Events können genutzt werden, um spezifische Aktionen bei bestimmten Ereignissen wie `submit` oder `input` zu handhaben.

### Beispiel: Formular mit Validierung

```html
<template>
  <form @submit.prevent="validateForm">
    <input v-model="email" type="email" placeholder="E-Mail">
    <p v-if="errors.length">
      <b>Fehler:</b>
      <ul>
        <li v-for="error in errors" :key="error">{{ error }}</li>
      </ul>
    </p>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      errors: []
    };
  },
  methods: {
    validateForm() {
      this.errors = [];
      if (!this.email.includes('@')) {
        this.errors.push('Bitte geben Sie eine gültige E-Mail Adresse ein.');
      }
    }
  }
}
</script>
```

## Fazit

Das Verständnis der Formularerstellung und -handhabung in Vue.js ist wesentlich für das Entwickeln interaktiver Webanwendungen. Die Nutzung von `v-model` für eine effiziente Datenbindung und das Verständnis der Handhabung von Formularevents und -validierung sind entscheidend für robuste Anwendungen.
