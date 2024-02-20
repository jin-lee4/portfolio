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
    border: 1px solid #b49fc2;
    border-radius: 0 0 0.5rem 0.5rem;
    border-top: 0;
    margin: auto;
    width: 45rem;    
  }

  ul {
    display: flex;
    flex-wrap: wrap;
    padding-left: 0;
    margin-bottom: 0;
    list-style: none;
    border-bottom: 1px solid #b49fc2;
  }
  li {
    margin-bottom: -1px;
    border: 1px solid #b49fc2;
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
    border: 1px #b49fc2;
    background-color: #fbf9ec;
    color: #235854;

  }

  button:hover {
    border-color: #b49fc2 #b49fc2 #b49fc2 #b49fc2;
    background-color: #E9E5CB;
  }

  li.active > button {
    color: #fff;
    background-color: #b49fc2;
    border-color: #b49fc2 #b49fc2 #b49fc2;
  }
</style>
