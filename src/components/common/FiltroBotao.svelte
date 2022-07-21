<script>
    import { Button, Icon, Styles } from 'sveltestrap';
    import FiltroModal from './FiltroModal.svelte';
    let open = false;
    const toggle = () => (open = !open);
</script>
<Styles />

<button on:click|preventDefault={toggle} outline class="mt-2 w-25 w-lg-14 w-xl-14 btn btn-outline-primary round ">
    <Icon name="bi bi-funnel" /> Filtro
</button>
<FiltroModal open={open} toggle={toggle} />
<style>
    .btn {
        margin-left:1rem;
    }
    @media (min-width: 992px) {  
        .w-lg-14{
            width: 14% !important;
        }
    
    }
    
    @media (min-width: 1200px) { 
        .w-xl-14{
            width: 14% !important;
        }
     }
</style>