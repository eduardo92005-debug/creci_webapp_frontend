<script>
    import  { onMount }  from "svelte";
    import VirtualList from "svelte-virtual-list-ce";
    import  Carregando  from './Carregando.svelte';
    import { Container } from 'sveltestrap';
    import PesquisarBotao from './PesquisarBotao.svelte';
    import TabelaArmarios from './TabelaArmarios.svelte';
    import PaginacaoBotao from './PaginacaoBotao.svelte';
    import FiltroBotao from './FiltroBotao.svelte';

    const URL = `http://localhost:8000/api/armario/`;
    /*const data = {
    "items": [
        {
            "id": 1,
            "creci": 5188,
            "nome_corretor": "ADIELE SANTOS SILVA Silva",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 2,
            "creci": 4510,
            "nome_corretor": "ADRIANA APARECIDA RIBEIRO RODRIGUES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 2,
            "armario": 25,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 3,
            "creci": 5365,
            "nome_corretor": "ALEXSANDRA PEREIRA DE SOUZA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 4,
            "creci": 4684,
            "nome_corretor": "ALEXANDRE MAGNO MENEZES SANTANA",
            "tipo": "pessoa fisica",
            "situacao": "Ativo",
            "gaveta": 3,
            "armario": 25,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 5,
            "creci": 3162,
            "nome_corretor": "AIRTON MONTES DE VASCONCELOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 6,
            "creci": 4866,
            "nome_corretor": "ADELWSON CHAVES GOMES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 7,
            "creci": 4951,
            "nome_corretor": "ARAMARI BANDEIRA TUDE",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 8,
            "creci": 3355,
            "nome_corretor": "AILTON ALVES PEREIRA JUNIOR",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 9,
            "creci": 3267,
            "nome_corretor": "ADRIANA VASCONCELOS MACEDO",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 10,
            "creci": 2662,
            "nome_corretor": "ADRIANA FERREIRA SOARES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 11,
            "creci": 4004,
            "nome_corretor": "ADRIANA DE LIMA AGUIAR",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 12,
            "creci": 4272,
            "nome_corretor": "ALINE CRUZ SILVA",
            "tipo": "pessoa fisica",
            "situacao": "Ativo",
            "gaveta": 1,
            "armario": 25,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 13,
            "creci": 4623,
            "nome_corretor": "ALEXANDRE DE ANDRADE MORAIS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 14,
            "creci": 4583,
            "nome_corretor": "ANA CAROLINA PEREIRA ALVES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 15,
            "creci": 4601,
            "nome_corretor": "ALVARO GABRIEL SAMPAIO ALMEIDA MENEZES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 16,
            "creci": 4822,
            "nome_corretor": "ALAINE DO NASCIMENTO LIMA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 17,
            "creci": 4551,
            "nome_corretor": "ANGELA TAISA DE OLIVEIRA SANTOS LIMA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 18,
            "creci": 2240,
            "nome_corretor": "ARISTOFONIS ARAGAO PASSOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 19,
            "creci": 3810,
            "nome_corretor": "ALEXANDRE OLIVEIRA DE ANDRADE",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 20,
            "creci": 4658,
            "nome_corretor": "ALISSON SILVA CORREA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 21,
            "creci": 3893,
            "nome_corretor": "ALISSON RODRIGO REZENDE DOS SANTOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 1,
            "armario": 1,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 22,
            "creci": 3775,
            "nome_corretor": "ALEXANDRE DE MENEZES OLIVEIRA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 23,
            "creci": 3329,
            "nome_corretor": "ANA ANDRADE CRUZ BATISTA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 24,
            "creci": 3202,
            "nome_corretor": "ADRIANA DOS SANTOS RODRIGUES",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 25,
            "creci": 4587,
            "nome_corretor": "ALLAN KARDEC BISPO SANTOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 26,
            "creci": 4595,
            "nome_corretor": "ARIV\u00c3 CONCEI\u00c7\u00c3O DOS SANTOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 27,
            "creci": 4108,
            "nome_corretor": "ANA LUIZA BORGES DE CARVALHO",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 28,
            "creci": 4727,
            "nome_corretor": "ALMANAJARA ALVES SAMPAIO CARNEIRO",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 29,
            "creci": 4581,
            "nome_corretor": "ALBERTO DE SOUZA OLIVEIRA",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 30,
            "creci": 4516,
            "nome_corretor": "ANGELA MARIA SANTANA ARAUJO SARMENTO",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        },
        {
            "id": 31,
            "creci": 2870,
            "nome_corretor": "ALISSON LUIZ VIEIRA SANTOS",
            "tipo": "estagi\u00e1rio",
            "situacao": "Cancelado a Pedido",
            "gaveta": 0,
            "armario": 0,
            "incluido_excluido": "Inclu\u00eddo"
        }
    ],
    "total": 10239,
    "page": 1,
    "size": 30,
    "total_pages": 331
    };*/
    //const { items, size, page, total, total_pages }  = data;
    //let armarios = items;
   let armarios = []
   onMount(async()=> {
        const response = await fetch(URL);
        const data = await response.json();
        const { items, size, page, total, total_pages }  = data;
        armarios = items;
    }
    );
    

</script>
{#if armarios.length !== 0}
<Container>
    <h1> Consulta de Armarios </h1>
    <h5> Mostrando resultados de um total de </h5>
    <PesquisarBotao/>
    <VirtualList items={[armarios]}>
        <TabelaArmarios obj={armarios}/>
    </VirtualList>
    <PaginacaoBotao/>
</Container>
{:else}
    <Carregando title="Carregando..." text="Por favor, aguarde."></Carregando>
{/if}
