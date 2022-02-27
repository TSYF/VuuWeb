<template>
    <div>
        <h1> {{text}} </h1>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'TituloVue',
    props: {
        text: String,
    },
})
</script>

<style scoped>

</style>