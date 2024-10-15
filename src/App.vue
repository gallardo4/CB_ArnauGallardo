<script setup>
  import { ref, reactive } from 'vue'

  // v-on / @
  const num = ref(0)

  const incrementar = () => {
    num.value++
  }

  const usuari = reactive({
    nom: 'Arnau',
    edat: 19
  })

  const incrementarEdat = () => {
    usuari.edat++
  }

  // v-bind / :
  const titol = "Hola Alan"

  const imatgeURL = "https://okdiario.com/img/2019/11/16/-cual-es-el-mono-mas-inteligente_-1-655x368.jpg"

  // v-model
  const nomUsuari = ref('')

  // v-for
  const productes = [
    {id: 1, nom: "Colacao", preu: 31},
    {id: 2, nom: "Nesquik", preu: 32},
    {id: 3, nom: "Valor", preu: 29}
  ]

  // v-if v-else
  const logat = ref(false)

  // v-show
  const mostrar = ref(false)
</script>

<template>
  <body>
    <div>
      <h2>v-on / @</h2>
      <h3>Comptador: {{ num }}</h3>
      <button @click="incrementar">Incrementar</button>
    </div>

    <div>
      <h2>v-on / @</h2>
      <p>Nom: {{ usuari.nom }}</p>
      <p>Edat: {{ usuari.edat }}</p>
      <button @click="incrementarEdat">Incrementar</button>
    </div>

    <div>
      <h2>v-bind / :</h2>
      <h3 v-bind:title="titol">Passa el ratolí per sobre</h3>
      <img :src="imatgeURL" alt="Imatge">
    </div>

    <div>
      <h2>v-model</h2>
      <p>Nom d'usuari: {{ nomUsuari }}</p>
      <input v-model="nomUsuari" type="text" placeholder="Escriu el teu nom">
    </div>

    <div>
      <h2>v-for</h2>
      <ul>
        <li v-for="producte in productes" :key="producte.id">{{ producte.nom }} {{ producte.preu }}</li>
      </ul>
    </div>

    <div>
      <h2>v-if v-else</h2>
      <p v-if="logat">Benvingut, usuari!</p>
      <p v-else>Inicia sessió!</p>
    </div>

    <div>
      <h2>v-show</h2>
      <button @click="mostrar =! mostrar">Mostra el text</button>
      <p v-show="mostrar">Aquest és el text que es mostra o s'amaga</p>
    </div>
  </body>
</template>

<style scoped>
header {
  line-height: 1.5;
}

body {
  display: flex;
  flex-direction: column;
  margin: 100px;
}

div {
  margin-top: 20px;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
