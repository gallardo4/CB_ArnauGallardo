<script>

import { ref, computed } from 'vue'

const nom = ref('Arnau')

const nomMajus = computed(() => nombre.value.toUpperCase())

</script>

<template>

    <div>
        <h2>computed()</h2>
        <p>Nom: {{ nom }}</p>
        <p>Nom en majúscules: {{ nomMajus }}</p>
    </div>

</template>