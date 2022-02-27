<template>
	<img alt="Vue logo" src="./assets/logo.png" />
	<TituloVue text="Mi Banco Dinámico v2.0" />
	<Cuenta />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TituloVue from "./components/Titulo.vue";
import Cuenta from "./components/Cuenta.vue";

export default defineComponent({
	name: "App",
	data() {
		return {

		};
	},
	components: {
    TituloVue,
    Cuenta,
},
});
</script>

<style lang="scss">
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>