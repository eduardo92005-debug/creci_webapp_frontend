<script lang="ts">
    import { Pagination, PaginationItem, PaginationLink } from 'sveltestrap';
    export let number_pages;
    export let current_page;

    function handlePaginate(){
        let how_many_to_end = number_pages - current_page;
        let enumeration = [...Array(current_page+3).keys()].slice(1);
        const size_enum = enumeration.length;
        if(current_page < (number_pages - 4) && current_page > 4){
            enumeration = [...Array(current_page+6).keys()].slice(current_page - 4);
            return enumeration;
        }  

        if(current_page >= (number_pages - 4) ) {
            enumeration = [...Array(current_page+(how_many_to_end+1)).keys()].slice(current_page - 4);
            return enumeration;
        }
        return enumeration;
    }

    function enumerate(start,end){
        let enumeration = new Array();
        for(let i = start; i < end; i++){
            enumeration.push(i);
        }
        return enumeration;
    }

    const enumeration = handlePaginate();
        
</script>
  
<Pagination class="mt-3 d-flex justify-content-center justify-content-lg-start justify-content-xl-start">
    <PaginationItem>
        <PaginationLink first href="http://localhost:8080/armarios?page=1" />
    </PaginationItem>
    {#if (current_page - 1) <= 0}
        <PaginationItem disabled>
            <PaginationLink previous href="http://localhost:8080/armarios?page={current_page - 1}" />
        </PaginationItem>
    {:else}
        <PaginationItem>
            <PaginationLink previous href="http://localhost:8080/armarios?page={current_page - 1}" />
        </PaginationItem>
    {/if}
    {#each enumeration as pages}
        {#if pages == current_page}
        <PaginationItem active>
            <PaginationLink href="http://localhost:8080/armarios?page={pages}">{pages}</PaginationLink>
        </PaginationItem>
        {:else}
        <PaginationItem>
            <PaginationLink href="http://localhost:8080/armarios?page={pages}">{pages}</PaginationLink>
        </PaginationItem>
        {/if}
    {/each}
    <PaginationItem>
        <PaginationLink next href="http://localhost:8080/armarios?page={current_page + 1}" />
    </PaginationItem>
    <PaginationItem>
        <PaginationLink last href="http://localhost:8080/armarios?page={number_pages}" />
    </PaginationItem>
</Pagination>
<style>

</style>