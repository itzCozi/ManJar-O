<script lang="ts">
  interface TableProps {
    headers: string[];
    rows: { id: number; track: string; artist: string }[];
  }

  export let headers: TableProps["headers"];
  export let rows: TableProps["rows"];

  function formatId(id: number): string {
    return id < 10 ? `0${id}` : `${id}`;
  }
</script>

<table class="w-full border-collapse">
  <thead>
    <tr>
      {#each headers as header, index}
        {#if index < headers.length - 1}
          <th class="text-center border-r border-mono-divider">{header}</th>
        {:else}
          <th class="text-center">{header}</th>
        {/if}
      {/each}
    </tr>
    <tr>
      <td colspan={headers.length}><hr class="border-b border-mono-divider border-0" /></td>
    </tr>
  </thead>
  <tbody>
    {#each rows as row, index}
      <tr>
        <td class="border-r border-mono-divider p-2">{formatId(row.id)}</td>
        <td class="border-r border-mono-divider p-2">{row.track}</td>
        <td class="p-2">{row.artist}</td>
      </tr>
      {#if index < rows.length - 1}
        <tr>
          <td colspan={headers.length}>
            <hr class="border-b border-mono-divider border-0" />
          </td>
        </tr>
      {/if}
    {/each}
  </tbody>
</table>
