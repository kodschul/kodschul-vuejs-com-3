
# Vue.js Codebeispiele

## Beispiel 1: Verwendung der Transition-Komponente

```html
<div id="app">
  <button @click="show = !show">Toggle Text</button>
  <transition name="fade">
    <p v-if="show">Dieser Text wird ein- und ausgeblendet</p>
  </transition>
</div>

<script>
  new Vue({
    el: '#app',
    data: {
      show: true
    }
  });
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>
```

## Beispiel 2: REST API Integration mit Axios

```javascript
<template>
  <div id="app">
    <ul>
      <li v-for="user in users" :key="user.id">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      users: []
    };
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        this.users = response.data;
      })
      .catch(error => {
        console.error(error);
      });
  }
};
</script>
```

## Beispiel 3: Verwendung des Vue Routers

```javascript
// router.js
import Vue from 'vue';
import Router from 'vue-router';
import Home from './components/Home.vue';
import About from './components/About.vue';
import Contact from './components/Contact.vue';

Vue.use(Router);

export default new Router({
  routes: [
    { path: '/', component: Home },
    { path: '/about', component: About },
    { path: '/contact', component: Contact }
  ]
});
```

## Beispiel 4: Verwendung von Router Guards

```javascript
// router.js
import Vue from 'vue';
import Router from 'vue-router';
import Login from './components/Login.vue';
import Secret from './components/Secret.vue';

Vue.use(Router);

const isAuthenticated = false; // Beispielwert, normalerweise aus einem Store oder Auth-Service

const router = new Router({
  routes: [
    { path: '/login', component: Login },
    { 
      path: '/secret', 
      component: Secret, 
      beforeEnter: (to, from, next) => {
        if (isAuthenticated) {
          next();
        } else {
          next('/login');
        }
      }
    }
  ]
});

export default router;
```

## Beispiel 5: Zustand zwischen Routenwechseln bewahren

```javascript
// In main.js
import Vue from 'vue';
import Vuex from 'vuex';
import App from './App.vue';

Vue.use(Vuex);

const store = new Vuex.Store({
  state: {
    scrollPosition: 0
  },
  mutations: {
    setScrollPosition(state, position) {
      state.scrollPosition = position;
    }
  }
});

new Vue({
  store,
  render: h => h(App),
  router: new Router({
    routes: [
      { 
        path: '/', 
        component: Home,
        beforeRouteLeave (to, from, next) {
          this.$store.commit('setScrollPosition', window.scrollY);
          next();
        },
        beforeRouteEnter (to, from, next) {
          next(vm => {
            window.scrollTo(0, vm.$store.state.scrollPosition);
          });
        }
      }
    ]
  })
}).$mount('#app');
```

## Beispiel 6: Arbeiten mit Promises und Axios

```javascript
<template>
  <div>
    <button @click="fetchFact">Hol einen Fakt!</button>
    <p>{{ fact }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      fact: ''
    };
  },
  methods: {
    fetchFact() {
      axios.get('http://numbersapi.com/random')
        .then(response => {
          this.fact = response.data;
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
};
</script>
```

## Beispiel 7: Teleport-Komponente verwenden

```html
<template>
  <div>
    <button @click="showModal = true">Zeige Modal</button>
    <teleport to="body">
      <div v-if="showModal" class="modal">
        <p>Dies ist ein modal</p>
        <button @click="showModal = false">Schließen</button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showModal: false
    };
  }
};
</script>

<style>
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 1em;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}
</style>
```
