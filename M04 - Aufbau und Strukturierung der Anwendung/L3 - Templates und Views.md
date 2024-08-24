
# Vue.js Schulung: Templates und Views

## Deine Benutzeroberfläche gestalten

In Vue.js sind Templates und Views zentrale Elemente, um ansprechende und dynamische Benutzeroberflächen zu gestalten. Diese Komponenten ermöglichen es Entwicklern, HTML-basierte Templates zu definieren, die reaktive Datenbindung und interaktive Elemente integrieren.

## Grundlagen von Templates in Vue.js

Ein Template in Vue.js ist HTML-Code, der Vue-spezifische Direktiven und Ausdrücke enthält, um das DOM effizient zu aktualisieren. Diese Templates sind eng mit der Vue-Instanz verbunden und ermöglichen eine deklarative Beschreibung der Benutzeroberfläche.

```html
<template>
  <div>
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Hallo Vue!',
      message: 'Das ist ein einfaches Template.'
    }
  }
}
</script>
```

## Erstellung und Nutzung von Views

Views in Vue.js sind im Grunde genommen Komponenten, die für spezifische Teile der Anwendung verwendet werden. Eine View kann eine Seite oder einen Teil einer Seite darstellen und enthält oft Logik und Templates, die zusammenarbeiten, um Features zu realisieren.

### Beispiel View: Benutzerprofil

```html
<template>
  <div class="profile">
    <img :src="user.avatar" alt="User Avatar">
    <h2>{{ user.name }}</h2>
    <p>{{ user.bio }}</p>
  </div>
</template>

<script>
export default {
  props: {
    user: Object
  }
}
</script>
```

## Strukturierung von Views und Routing

Die Strukturierung von Views und das Routing sind wesentliche Aspekte bei der Entwicklung von Single-Page Applications (SPAs) in Vue.js. Vue Router wird verwendet, um verschiedene Komponenten als Views zu verschiedenen URLs zuzuordnen.

```javascript
import VueRouter from 'vue-router';
import UserProfile from './components/UserProfile.vue';
import UserSettings from './components/UserSettings.vue';

const router = new VueRouter({
  routes: [
    { path: '/profile', component: UserProfile },
    { path: '/settings', component: UserSettings }
  ]
})

export default router;
```

## Fazit

Das Verständnis von Templates und Views in Vue.js ist entscheidend für die Gestaltung interaktiver und benutzerfreundlicher Webanwendungen. Durch den Einsatz von Vue's reaktiver Engine und dem Router können Entwickler effiziente und navigierbare SPAs erstellen.
