<script>
    import {
    Button,
    Form, 
    FormGroup, 
    Input, 
    Label 
    } from 'sveltestrap';
    import PesquisaBotao from './PesquisaBotao.svelte';
    import FiltroBotao from './FiltroBotao.svelte';
</script>

<Form>
    <FormGroup>
        <Label for="searchField"> Digite um termo para pesquisa:</Label>
        <Input type="search" id="searchField" placeholder="Exemplo: Armario 27"/>
        <div class='d-inline-flex w-100 justify-content-between'>
            <PesquisaBotao />
            <FiltroBotao />
        </div>
    </FormGroup>
</Form>
