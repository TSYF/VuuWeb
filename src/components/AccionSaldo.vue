<template>
        <button @click="mutarSaldo" :disabled="desactivar">{{mutacion}} Saldo</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    methods: {
        mutarSaldo() {
            this.$emit("mutar-saldo")
        },
    },
    props: {
        mutacion: {
            type: String,
            default: "Actualizar"
        },
        desactivar: {
            type: Boolean,
            default: false,
        }
    },
})
</script>

<style scoped>

</style>