<script>
	import CreciFrame from "./components/CreciFrame.svelte";
	import { onMount } from "svelte";
	import Cabecalho from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import UsuarioConectado from "./components/UsuarioConectado.svelte";
	import { Router, Route, Link } from "svelte-navigator";
	import Armario from "./components/Armario.svelte";
	export let url = "";



</script>

<Router>
	<main>

		<Route path="index">
			<Cabecalho></Cabecalho>
			<UsuarioConectado></UsuarioConectado>
			<CreciFrame></CreciFrame>
			<Footer text="©2022 CRECI-SE | Todos os direitos reservados." class="mb-5"></Footer>
		</Route>

		<Route path="armarios">
			<Cabecalho></Cabecalho>
			<Armario />
			<Footer text="©2022 CRECI-SE | Todos os direitos reservados." class="my-2"></Footer>
		</Route>
	</main>
</Router>


<style>
	main {
		height:100%;
		overflow:auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
			overflow:auto;
		}
	}
</style>