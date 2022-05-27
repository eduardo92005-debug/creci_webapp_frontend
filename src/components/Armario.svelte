<script>
    import  { onMount }  from "svelte";
    import VirtualList from "svelte-virtual-list-ce";
    import  Carregando  from './Loading.svelte';
    import TextoBase from './TextoBase.svelte';
    import { Container, Row, Col } from 'sveltestrap';
    import {
    Button,
    Card,
    CardBody,
    CardHeader,
    CardSubtitle,
    CardText,
    Form, 
    FormGroup, 
    FormText, 
    Input, 
    Label 
    } from 'sveltestrap';

    const URL = `http://localhost:8000/api/armario/`;
    let armarios = [
    {
        "id": 1,
        "creci": 405,
        "nome_corretor": "teste 0",
        "tipo": "tipo 0",
        "situacao": "situacao 0",
        "gaveta": 1,
        "armario": 31,
        "incluido_excluido": "incluido 0"
    },
    {
        "id": 2,
        "creci": 115,
        "nome_corretor": "teste 1",
        "tipo": "tipo 1",
        "situacao": "situacao 1",
        "gaveta": 4,
        "armario": 37,
        "incluido_excluido": "incluido 1"
    },
    {
        "id": 3,
        "creci": 435,
        "nome_corretor": "teste 2",
        "tipo": "tipo 2",
        "situacao": "situacao 2",
        "gaveta": 3,
        "armario": 17,
        "incluido_excluido": "incluido 2"
    },
    {
        "id": 4,
        "creci": 9,
        "nome_corretor": "teste 3",
        "tipo": "tipo 3",
        "situacao": "situacao 3",
        "gaveta": 5,
        "armario": 12,
        "incluido_excluido": "incluido 3"
    },
    {
        "id": 5,
        "creci": 209,
        "nome_corretor": "teste 4",
        "tipo": "tipo 4",
        "situacao": "situacao 4",
        "gaveta": 1,
        "armario": 41,
        "incluido_excluido": "incluido 4"
    },
    {
        "id": 6,
        "creci": 352,
        "nome_corretor": "teste 5",
        "tipo": "tipo 5",
        "situacao": "situacao 5",
        "gaveta": 5,
        "armario": 18,
        "incluido_excluido": "incluido 5"
    },
    {
        "id": 7,
        "creci": 41,
        "nome_corretor": "teste 6",
        "tipo": "tipo 6",
        "situacao": "situacao 6",
        "gaveta": 1,
        "armario": 35,
        "incluido_excluido": "incluido 6"
    },
    {
        "id": 8,
        "creci": 104,
        "nome_corretor": "teste 7",
        "tipo": "tipo 7",
        "situacao": "situacao 7",
        "gaveta": 3,
        "armario": 30,
        "incluido_excluido": "incluido 7"
    },
    {
        "id": 9,
        "creci": 455,
        "nome_corretor": "teste 8",
        "tipo": "tipo 8",
        "situacao": "situacao 8",
        "gaveta": 2,
        "armario": 5,
        "incluido_excluido": "incluido 8"
    },
    {
        "id": 10,
        "creci": 402,
        "nome_corretor": "teste 9",
        "tipo": "tipo 9",
        "situacao": "situacao 9",
        "gaveta": 5,
        "armario": 37,
        "incluido_excluido": "incluido 9"
    },
    {
        "id": 11,
        "creci": 42,
        "nome_corretor": "teste 10",
        "tipo": "tipo 10",
        "situacao": "situacao 10",
        "gaveta": 3,
        "armario": 6,
        "incluido_excluido": "incluido 10"
    },
    {
        "id": 12,
        "creci": 74,
        "nome_corretor": "teste 11",
        "tipo": "tipo 11",
        "situacao": "situacao 11",
        "gaveta": 5,
        "armario": 17,
        "incluido_excluido": "incluido 11"
    },
    {
        "id": 13,
        "creci": 370,
        "nome_corretor": "teste 12",
        "tipo": "tipo 12",
        "situacao": "situacao 12",
        "gaveta": 5,
        "armario": 17,
        "incluido_excluido": "incluido 12"
    },
    {
        "id": 14,
        "creci": 349,
        "nome_corretor": "teste 13",
        "tipo": "tipo 13",
        "situacao": "situacao 13",
        "gaveta": 4,
        "armario": 30,
        "incluido_excluido": "incluido 13"
    },
    {
        "id": 15,
        "creci": 298,
        "nome_corretor": "teste 14",
        "tipo": "tipo 14",
        "situacao": "situacao 14",
        "gaveta": 3,
        "armario": 30,
        "incluido_excluido": "incluido 14"
    },
    {
        "id": 16,
        "creci": 457,
        "nome_corretor": "teste 15",
        "tipo": "tipo 15",
        "situacao": "situacao 15",
        "gaveta": 1,
        "armario": 1,
        "incluido_excluido": "incluido 15"
    },
    {
        "id": 17,
        "creci": 381,
        "nome_corretor": "teste 16",
        "tipo": "tipo 16",
        "situacao": "situacao 16",
        "gaveta": 5,
        "armario": 29,
        "incluido_excluido": "incluido 16"
    },
    {
        "id": 18,
        "creci": 231,
        "nome_corretor": "teste 17",
        "tipo": "tipo 17",
        "situacao": "situacao 17",
        "gaveta": 1,
        "armario": 10,
        "incluido_excluido": "incluido 17"
    },
    {
        "id": 19,
        "creci": 190,
        "nome_corretor": "teste 18",
        "tipo": "tipo 18",
        "situacao": "situacao 18",
        "gaveta": 2,
        "armario": 11,
        "incluido_excluido": "incluido 18"
    },
    {
        "id": 20,
        "creci": 419,
        "nome_corretor": "teste 19",
        "tipo": "tipo 19",
        "situacao": "situacao 19",
        "gaveta": 3,
        "armario": 40,
        "incluido_excluido": "incluido 19"
    },
    {
        "id": 21,
        "creci": 666,
        "nome_corretor": "teste",
        "tipo": "teste",
        "situacao": "teste",
        "gaveta": 2,
        "armario": 1,
        "incluido_excluido": "teste"
    }
];

    /*onMount(async()=> {
        const response = await fetch(URL);
        const json = await response.json();
        armarios = json;
    }
    );*/
    let start;
    let end;

</script>
{#if armarios.length !== 0}
<Container>
    <h1> Consulta de Armarios </h1>
    <h5> Mostrando resultados de um total de {armarios.length}</h5>
    <Form>
        <FormGroup>
            <Label for="searchField"> Digite um termo para pesquisa:</Label>
            <Input type="search" id="searchField" placeholder="Exemplo: Armario 27"/>
            <Button class="mt-2 btn btn-primary"> Pesquisar </Button>
        </FormGroup>
    </Form>
</Container>
<VirtualList items={[armarios]} bind:start bind:end let:item>
    <Container>
        <Row>
            {#each item as armario}
            <Col md="4" class="pb-5">
                <Card>
                    <CardHeader>
                        {armario.id} ~ CRECI {armario.creci}
                    </CardHeader>
                    <CardBody>
                        <CardSubtitle><h3>{armario.nome_corretor}</h3></CardSubtitle>
                        <CardText style="text-align:left">
                            <TextoBase text = "Tipo: " from={armario.tipo}></TextoBase>
                            <TextoBase text = "Armario: " from={armario.armario}></TextoBase>
                            <TextoBase text = "Gaveta: " from={armario.gaveta}></TextoBase>
                            <TextoBase text = "Situação: " from={armario.situacao}></TextoBase>
                            <TextoBase text = "Incluido ou excluido: " from = {armario.incluido_excluido}></TextoBase>
                        </CardText>
                    </CardBody>
                </Card>
            </Col>
            {/each} 
        </Row>
    </Container>
 
</VirtualList>
{:else}
    <Carregando title="Carregando..." text="Por favor, aguarde."></Carregando>
{/if}


<style>
</style>