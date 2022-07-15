<script lang="ts">
    import { Pagination, PaginationItem, PaginationLink } from 'sveltestrap';
    import { Link } from 'svelte-navigator';
    export let number_pages;
</script>
  
<Pagination class="mt-3 d-flex justify-content-center justify-content-lg-start justify-content-xl-start">
    <PaginationItem disabled>
        <PaginationLink first href="#" />
    </PaginationItem>
    <PaginationItem disabled>
        <PaginationLink previous href="#" />
    </PaginationItem>
    <PaginationItem active>
        <PaginationLink href="#">1</PaginationLink>
    </PaginationItem>
    <PaginationItem>
        <PaginationLink href="#">2</PaginationLink>
    </PaginationItem>
    <PaginationItem>
        <PaginationLink href="#">3</PaginationLink>
    </PaginationItem>
    <PaginationItem>
        <PaginationLink href="#">4</PaginationLink>
    </PaginationItem>
    <PaginationItem>
        <PaginationLink href="#">5</PaginationLink>
    </PaginationItem>
    <PaginationItem>
        <PaginationLink next href="#" />
    </PaginationItem>
    <PaginationItem>
        <PaginationLink last href="#" />
    </PaginationItem>
</Pagination>
<style>

</style>