# Vue cli

Membuat sebuah project menggunakan vuejs dengan setup yang lebih cepat adalah hal yang sangat penting untuk memulai membuat sebuah project dengan waktu yang singkat, hal tersebut bisa kita atasi karena vuejs sudah menyediakan tools generate template basic untuk develop app menggunakan vuejs namanya Vue CLI (Command Line Interface).

namun apa perbedaan vuejs dengan Vue CLI, hal tersebut jelas ber-beda, vue cli adalah tool untuk menggenerate setup pada paket Vue (Vuex, Vue Router, Path folder dll) yang bisa kita pilih dan install ketika memulai membuat a app sedangkan vue itu framework Javascript.

langsung saja kita memulai tutorial menggunakan Vue CLI.

installasi

`$ npm install -g @vue/cli @vue/cli-service-global`
<br>
or
<br>
`$ yarn global add @vue/cli @vue/cli-service-global`

<p> Kenapa kita harus menginstall lewat global, karena <b> Vue CLI adalah tool untuk generate project / Command Line Interface </b>. </p>

membuat project

`$ vue create yourname-app`

lalu akan muncul seperti gambar dibawah ini, kita pilih saja manually karena kita akan memilih webpack yang kita butuhkan saja.
<img src="https://cli.vuejs.org/cli-new-project.png">

setelah itu kita pilih webpack yang dibutuhkan dengan (Space keyboard).
<img src="https://cli.vuejs.org/cli-select-features.png">

<p>
kemudian kita bisa memilih es-lint yang kalian suka.
</p>

<p> lalu running project </p>

`$ yarn serve`

setelah selesai membuat project, coba kita buka project menggunakan text editor dan akan terlihat path public, src dll yang telah disediakan oleh vue.

kita buka file `main.js` di folder `./src` terlihat code es6 js dan initial vuejs.

```
import Vue from 'vue'; //es6
import App from './App.vue'; //es6

Vue.config.productionTip = false;

new Vue({
    render: (h) => h(App),
}).$mount('#app');
```

code diatas sama code dibawah ini perbedaanya apa?

```
new Vue({
el: '#app',
    components: {
        App
    }
})
```

code diatas sedikit ada perbedaannya pada rendering #app

`$mount allows you to explicitly mount the Vue instance when you need to. This means that you can delay the mounting of your vue instance until a particular element exists in your page or some async process has finished, which can be particularly useful when adding vue to legacy apps which inject elements into the DOM, I've also used this frequently in testing.`

link: https://stackoverflow.com/questions/46831452/difference-between-mount-and-el-vue-js

watch bisa ngelisten props juga
<br/>
name components itu penting
