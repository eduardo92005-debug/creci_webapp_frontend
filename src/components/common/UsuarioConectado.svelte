<script>
    import  { onMount }  from "svelte";


    const URL = `http://localhost:8000/api/usuario/`;
    let usuarios = [];

    onMount(async()=> {
        const response = await fetch(URL);
        const json = await response.json();
        usuarios = json;
    }
    );

</script>

<main>
        <p class="h4 m-1 ml-3">Último usuário conectado: daniel</p>
</main>

<style>

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>