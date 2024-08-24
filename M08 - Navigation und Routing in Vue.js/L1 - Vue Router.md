
# Vue.js Schulung - Vue Router

## Vue Router: Dein Navigator durch die Anwendung

Vue Router ist das offizielle Router-Modul für Vue.js. Es ermöglicht das Erstellen von Single Page Applications (SPAs) durch effizientes Routing und Ansichtsmanagement.

## Installation und Grundkonfiguration des Vue Routers

Um Vue Router zu verwenden, muss es zunächst installiert und in einem Vue-Projekt eingerichtet werden. Hier ist ein einfacher Leitfaden zur Installation und Konfiguration:

### Installation
```bash
npm install vue-router
```

### Grundkonfiguration
```javascript
import Vue from 'vue';
import VueRouter from 'vue-router';
import Home from './components/Home.vue';
import About from './components/About.vue';

Vue.use(VueRouter);

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About }
];

const router = new VueRouter({
  mode: 'history',
  routes
});

new Vue({
  router,
  render: h => h(App)
}).$mount('#app');
```

## Unterschiedliche Routing-Strategien und Einsatzbereiche

Vue Router unterstützt verschiedene Routing-Strategien wie die Hash-Modus und den History-Modus:

- **Hash-Modus**: verwendet URL-Hashes für das Routing (z.B. `#about`). Ideal für statische Websites oder wenn kein Server-Seitiges Routing erwünscht ist.
- **History-Modus**: verwendet die HTML5 History API für saubere URLs ohne Hashes. Erfordert Server-Konfiguration, um Seiten korrekt zu liefern.

### Einsatzbereiche
- **Single Page Applications (SPAs)**: für dynamische Seiten, die unter einer einzigen URL geladen werden.
- **Multiple Page Applications (MPAs)**: ermöglicht das Routing zwischen verschiedenen Ansichten einer größeren Webanwendung.

## Dynamische Routen und Nested Routing

Dynamische Routen erlauben es, Parameter innerhalb von URLs zu definieren, was sehr nützlich für das Anzeigen von spezifischen Inhalten ist.

### Dynamische Routen
```javascript
const routes = [
  { path: '/user/:id', component: User }
];
```

Nested Routing, oder verschachteltes Routing, ist nützlich für Anwendungen mit mehreren Ebenen von Komponenten.

### Nested Routing
```javascript
const routes = [
  { path: '/user/:id', component: User, children: [
    { path: 'profile', component: UserProfile },
    { path: 'posts', component: UserPosts }
  ]}
];
```

## Fazit

Vue Router ist ein kraftvolles Werkzeug für das Routing in Vue.js Anwendungen, das dynamische, verschachtelte Routen und verschiedene Routing-Strategien unterstützt. Die Beherrschung des Vue Routers ermöglicht die Erstellung komplexer und benutzerfreundlicher SPAs.
