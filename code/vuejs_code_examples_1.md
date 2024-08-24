
# Vue.js Codebeispiele

## Beispiel 1: Datenbindung mit `v-bind`

```html
<div id="app">
  <img v-bind:src="imageSrc" alt="Beispielbild">
  <p v-bind:title="title">{{ message }}</p>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      imageSrc: 'path/to/image.jpg',
      title: 'Beispieltitel',
      message: 'Hallo Vue!'
    }
  });
</script>
```

## Beispiel 2: Event-Handling mit `v-on`

```html
<div id="app">
  <button v-on:click="incrementCounter">Klicke mich</button>
  <p>Zähler: {{ counter }}</p>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      counter: 0
    },
    methods: {
      incrementCounter() {
        this.counter++;
      }
    }
  });
</script>
```

## Beispiel 3: Zweirichtungsbindung mit `v-model`

```html
<div id="app">
  <input v-model="inputValue" placeholder="Gib etwas ein">
  <p>Du hast eingegeben: {{ inputValue }}</p>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      inputValue: ''
    }
  });
</script>
```

## Beispiel 4: Projektaufsetzung mit Webpack und Vue.js

```bash
# Installiere Vue CLI
npm install -g @vue/cli

# Erstelle ein neues Projekt
vue create mein-projekt

# Wechsel in das Projektverzeichnis
cd mein-projekt

# Starte den Entwicklungsserver
npm run serve
```

## Beispiel 5: Verwendung von ESLint und Prettier

```bash
# Installiere ESLint
npm install eslint --save-dev

# Führe ESLint aus
npx eslint --init

# Installiere Prettier
npm install prettier --save-dev

# Formatieren des Codes mit Prettier
npx prettier --write .
```

## Beispiel 6: TypeScript in Vue.js verwenden

```typescript
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      message: 'Hallo TypeScript mit Vue!'
    };
  },
  methods: {
    logMessage(): void {
      console.log(this.message);
    }
  }
});
</script>
```

## Beispiel 7: Migration von Vue.js 2 zu Vue.js 3

```bash
# Installiere das @vue/compat Paket
npm install @vue/compat --save

# Füge die Kompatibilitätsversion in der main.js hinzu
import { createApp } from '@vue/compat';
import App from './App.vue';

createApp(App).mount('#app');
```
