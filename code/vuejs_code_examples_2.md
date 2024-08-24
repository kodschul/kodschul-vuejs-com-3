
# Vue.js Codebeispiele

## Beispiel 1: Bedingtes Rendern mit `v-if`, `v-else` und `v-else-if`

```html
<div id="app">
  <p v-if="isLoggedIn">Willkommen zurück!</p>
  <p v-else>Bitte melde dich an.</p>
  <p v-else-if="role === 'admin'">Willkommen Admin!</p>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      isLoggedIn: false,
      role: ''
    }
  });
</script>
```

## Beispiel 2: Schleifen und Iterationen mit `v-for`

```html
<div id="app">
  <ul>
    <li v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
  </ul>
  <button v-on:click="addFruit">Frucht hinzufügen</button>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      fruits: ['Apfel', 'Banane', 'Orange']
    },
    methods: {
      addFruit() {
        const newFruits = ['Kiwi', 'Mango', 'Traube'];
        const randomFruit = newFruits[Math.floor(Math.random() * newFruits.length)];
        this.fruits.push(randomFruit);
      }
    }
  });
</script>
```

## Beispiel 3: Computed Properties

```html
<div id="app">
  <input v-model="firstName" placeholder="Vorname">
  <input v-model="lastName" placeholder="Nachname">
  <h2>{{ fullName }}</h2>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      firstName: '',
      lastName: ''
    },
    computed: {
      fullName() {
        return this.firstName + ' ' + this.lastName;
      }
    }
  });
</script>
```

## Beispiel 4: Vuex Store Einrichtung

```javascript
// store.js
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export default new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment(state) {
      state.count++;
    },
    decrement(state) {
      state.count--;
    }
  },
  actions: {
    incrementAsync({ commit }) {
      setTimeout(() => {
        commit('increment');
      }, 1000);
    }
  },
  getters: {
    currentCount: state => state.count
  }
});
```

## Beispiel 5: Watcher zur Überwachung von Daten

```html
<div id="app">
  <input v-model="text" placeholder="Gib etwas ein">
  <p>{{ message }}</p>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      text: '',
      message: ''
    },
    watch: {
      text(newValue) {
        this.message = `Du hast ${newValue.length} Zeichen eingegeben.`;
      }
    }
  });
</script>
```

## Beispiel 6: Formularerstellung mit `v-model`

```html
<div id="app">
  <form @submit.prevent="submitForm">
    <input v-model="name" placeholder="Name">
    <p>Hallo, {{ name }}!</p>
    <button type="submit">Absenden</button>
  </form>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      name: ''
    },
    methods: {
      submitForm() {
        alert(`Formular gesendet von: ${this.name}`);
      }
    }
  });
</script>
```

## Beispiel 7: Formularvalidierung mit VeeValidate

```html
<template>
  <div id="app">
    <ValidationObserver v-slot="{ invalid }">
      <form @submit.prevent="submitForm">
        <ValidationProvider rules="required|email" v-slot="{ errors }">
          <input v-model="email" type="email" placeholder="E-Mail">
          <span>{{ errors[0] }}</span>
        </ValidationProvider>
        <button :disabled="invalid" type="submit">Absenden</button>
      </form>
    </ValidationObserver>
  </div>
</template>

<script>
import { ValidationObserver, ValidationProvider } from 'vee-validate';

export default {
  data() {
    return {
      email: ''
    };
  },
  methods: {
    submitForm() {
      alert(`E-Mail gesendet: ${this.email}`);
    }
  },
  components: {
    ValidationObserver,
    ValidationProvider
  }
};
</script>
```
