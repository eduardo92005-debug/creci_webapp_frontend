<script>
    import { Table } from 'sveltestrap';
    export let obj;
</script>

<Table responsive striped size="sm">
    <thead>
        <tr>
        <th>ID</th>
        <th>CRECI</th>
        <th>Nome</th>
        <th>Tipo</th>
        <th>Situação</th>
        <th>Gaveta</th>
        <th>Armário</th>
        <th>Incluído ou excluído</th>
        </tr>
    </thead>
    <tbody>
    {#each obj as data (data)}
        <tr>
        <td>{data.id}</td>
        <td>{data.creci}</td>
        <td>{data.nome_corretor}</td>
        <td>{data.tipo}</td>
        <td>{data.situacao}</td>
        <td>{data.gaveta}</td>
        <td>{data.armario}</td>
        <td>{data.incluido_excluido}</td>
        </tr>
    {/each}
    </tbody>
</Table>