<script>
    import { Button, Icon, Styles } from 'sveltestrap';
</script>
<Styles />
<Button color="primary" class="w-100 mt-2 btn btn-primary w-lg-27 w-xl-27">
    <Icon name="bi bi-search" /> Pesquisar
</Button>
<style>
    @media (min-width: 992px) {  
        .w-lg-27{
            width: 27% !important;
        }
    
    }
    
    @media (min-width: 1200px) { 
        .w-xl-27{
            width: 27% !important;
        }
     }
</style>