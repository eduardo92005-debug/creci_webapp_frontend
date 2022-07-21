<script lang="ts">
    import {
        Button,
        Modal,
        ModalBody,
        ModalFooter,
        ModalHeader,
    } from "sveltestrap";
    import FiltroModalInputs from "./FiltroModalInputs.svelte";
    export let open = false;
    export let toggle;
</script>

<div>
    <Modal isOpen={open} {toggle}>
        <ModalHeader {toggle}>Filtros</ModalHeader>
        <ModalBody>
            <FiltroModalInputs />
        </ModalBody>
        <ModalFooter>
            <Button color="primary" on:click={toggle}>Do Something</Button>
            <Button color="secondary" on:click={toggle}>Cancel</Button>
        </ModalFooter>
    </Modal>
</div>
