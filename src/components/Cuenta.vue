<template>
	<div>
		<h2>Tipo de cuenta: {{ cuenta }}</h2>
		<h2>Saldo: {{ saldo }}</h2>
		<h2>Cuenta: {{ estado }}</h2>
		<ul>
			<h2>Servicios</h2>
			<li v-for="(servicio, i) in servicios" :key="servicio + i">
				{{ servicio }}
			</li>
		</ul>
		<AccionSaldo mutacion="Aumentar" @mutar-saldo="aumentarSaldo(100)" />
		<AccionSaldo
			mutacion="Disminuir"
			@mutar-saldo="disminuirSaldo(100)"
			:desactivar="saldoBool"
		/>
	</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AccionSaldo from "./AccionSaldo.vue";

export default defineComponent({
	data() {
		return {
			saldo: 1000,
			cuenta: "Visa",
			servicios: [
				`Giro`,
				`Abono`,
				`Transferencia`,
				`Consulta`,
			] as string[],
		};
	},
	methods: {
		aumentarSaldo(val: number) {
			this.saldo += val;
		},
		disminuirSaldo(val: number) {
            this.saldo -= val;
            if (this.saldoBool) {
                console.error("Saldo Agotado")
                alert("Saldo Agotado")
                return
            }
		},
	},
	computed: {
		estado(): string {
			return this.saldoBool ? "Activa" : "Inactiva";
		},
		saldoBool(): boolean {
			return this.saldo > 0 ? false : true;
		},
	},
	components: { AccionSaldo },
});
</script>

<style scoped></style>
