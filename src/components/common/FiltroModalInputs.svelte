<script lang="ts">
    import {
        InputGroup,
        InputGroupText,
        Input,
    } from "sveltestrap";
    let is_checked = false;
</script>

<InputGroup class="mb-2">
    <InputGroupText>
        <Input
            type="checkbox"
            aria-label="Checkbox for following text input"
            bind:checked={is_checked}
        />
    </InputGroupText>
    <Input disabled placeholder="Por número do CRECI" />
    {#if is_checked}
        <Input>DSASKFAKDFASD</Input>
    {/if}
</InputGroup>

<InputGroup class="mb-2">
    <InputGroupText>
        <Input
            type="checkbox"
            aria-label="Checkbox for following text input"
        />
    </InputGroupText>
    <Input disabled placeholder="Por nome do corretor" />
</InputGroup>

<InputGroup class="mb-2">
    <InputGroupText>
        <Input
            type="checkbox"
            aria-label="Checkbox for following text input"
        />
    </InputGroupText>
    <Input disabled placeholder="Por situação" />
</InputGroup>