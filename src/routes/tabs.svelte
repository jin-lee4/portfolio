<script>
  export let items = [];
  export let activeTabValue = 1;

  const handleClick = (tabValue) => () => (activeTabValue = tabValue);
</script>

<ul>
  {#each items as item}
    <li class={activeTabValue === item.value ? "active" : ""}>
      <button on:click={handleClick(item.value)}>{item.label} </button>
    </li>
  {/each}
</ul>
{#each items as item}
  {#if activeTabValue == item.value}
    <div class="box">
      <svelte:component this={item.component} />
    </div>
  {/if}
{/each}

<style>

  .box {
    margin-bottom: 10px;
    padding: 40px;
    border: 1px solid var(--accent-light);
    border-radius: 0 0.5rem 0.5rem 0.5rem;  
    max-width: 600px;  
  }

  ul {
    display: flex;
    flex-wrap: wrap;
    padding-left: 0;
    margin-bottom: 0;
    list-style: none;
    /* border-bottom: 1px solid var(--accent-light); */
  }
  li {
    margin-bottom: -1px;
    border: 1px solid var(--accent-light);
    border-top-left-radius: 0.25rem;
    border-top-right-radius: 0.25rem;
  }

  button {
    border: 1px solid transparent;
    border-top-left-radius: 0.25rem;
    border-top-right-radius: 0.25rem;
    display: block;
    padding: 0.5rem 1rem;
    cursor: pointer;
    border: 1px var(--accent-light);
    background-color: var(--light);
    color: var(--accent);
  }

  button:hover {
    border-color: var(--accent-light);
    background-color: var(--light-mid);
  }

  li.active > button {
    color: var(--light);
    background-color: var(--accent-light);
    border-color: var(--accent-light)
  }
</style>
