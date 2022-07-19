
<script>
    export let title;
    export let text;
    import { Spinner } from 'sveltestrap';
</script>
<main>
        <div class="d-flex flex-column align-items-center justify-content-center min-vh-100">
                <Spinner/>
                <h1>
                    {title} 
                </h1>
                <p>{text}</p>
        </div>
</main>
