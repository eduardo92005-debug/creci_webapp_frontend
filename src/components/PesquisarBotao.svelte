<script>
    import {
    Button,
    Form, 
    FormGroup, 
    Input, 
    Label 
    } from 'sveltestrap';
</script>

<Form>
    <FormGroup>
        <Label for="searchField"> Digite um termo para pesquisa:</Label>
        <Input type="search" id="searchField" placeholder="Exemplo: Armario 27"/>
        <button class="w-100 mt-2 btn btn-primary w-lg-27 w-xl-27"> Pesquisar </button>
    </FormGroup>
</Form>

<style>

@media (min-width: 992px) {  
    .w-lg-27{
        width: 27% !important;;
    }

}

@media (min-width: 1200px) { 
    .w-xl-27{
        width: 27% !important;
    }
 }
</style>
