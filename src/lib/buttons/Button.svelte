<script lang="ts">
  export interface Props {
    className?: string;
    onClick?: () => void;
    title?: string;
    href?: string;
    children?: import("svelte").Snippet;
  }

  let { className = "", onClick = () => {}, title = "", href = "", children }: Props = $props();
</script>

{#if href}
  <a
    class={`text-center text-type-dimmed/90 border border-mono-divider py-1 px-2 hover:text-type-primary hover:bg-transparent hover:border-type-footer duration-200 ease-in-out ${className}`}
    {href}
    {title}>
    {@render children?.()}
  </a>
{:else}
  <button
    class={`text-center text-type-dimmed/90 border border-mono-divider py-1 px-2 hover:text-type-primary hover:border-type-footer duration-200 ease-in-out ${className}`}
    onclick={onClick}
    {title}>
    {@render children?.()}
  </button>
{/if}
