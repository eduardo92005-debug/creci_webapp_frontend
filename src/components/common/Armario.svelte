<script>
    import { onMount } from "svelte";
    import VirtualList from "svelte-virtual-list-ce";
    import Carregando from "./Carregando.svelte";
    import { Container } from "sveltestrap";
    import FormularioPesquisa from "./FormularioPesquisa.svelte";
    import TabelaArmarios from "./TabelaArmarios.svelte";
    import PaginacaoBotao from "./PaginacaoBotao.svelte";

    const urlParams = new URLSearchParams(window.location.search);
    const page_param = urlParams.get('page');
    let _page = page_param;
    const URL = `http://localhost:8000/api/armario/?page=` + _page;

    let armarios = [];
    let _size;
    let _total;
    let _total_pages;
    onMount(async () => {
        const response = await fetch(URL);
        const data = await response.json();
        var { items, size, page, total, total_pages } = data;
        _size = size + 1;
        _total = total;
        _page = page;
        _total_pages = total_pages;
        armarios = items;
    });

</script>

{#if armarios.length !== 0}
    <Container>
        <h1>Consulta de Armarios</h1>
        <h5>Mostrando {_size} resultados de um total de {_total}</h5>
        <FormularioPesquisa />
        <VirtualList items={[armarios]}>
            <TabelaArmarios obj={armarios} />
        </VirtualList>
        <PaginacaoBotao
            number_pages={_total_pages}
            current_page={_page}
        />
    </Container>
{:else}
    <Carregando title="Carregando..." text="Por favor, aguarde." />
{/if}
