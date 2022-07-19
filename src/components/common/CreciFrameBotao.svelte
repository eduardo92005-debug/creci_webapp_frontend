
<script>
    import { useNavigate } from "svelte-navigator";


    export let href;
    export let text;
    const navigate = useNavigate();


</script>
<main>
        <a href={href} on:click={navigate(href)} class="btn rounded-0 btn-secondary btn-lg btn-outline-dark text-white text-decoration-none"> 
            {text}

        </a>
</main>
<style>
    
</style>
