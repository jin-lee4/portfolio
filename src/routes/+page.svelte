<script>
  import Tab1 from "./tab1.svelte";
  import Tab2 from "./tab2.svelte";
  import Tab3 from "./tab3.svelte";
  import Tabs from "./tabs.svelte";
  import { fade } from "svelte/transition";

  let hidden = true;

  setTimeout(() => {
		hidden = false;
	}, 200);

  // List of tab items with labels, values and assigned components
  let items = [
    { label: "Work Experience", value: 1, component: Tab1 },
    { label: "School", value: 2, component: Tab2 },
    { label: "Personal Projects", value: 3, component: Tab3 },
  ];
</script>

{#if !hidden}
  <div class="container" transition:fade={{ duration: 300 }}>
    <div id="header">
      <h1>Jin Lee</h1>
      <p>Welcome to my portfolio! Thanks for dropping by.</p>
    <div id="nav">
      <a href="mailto:leejinbc@gmail.com" target="_blank">Email</a>
      <a href="https://www.linkedin.com/in/jin-leebc/" target="_blank"
        >LinkedIn</a>
      <a href="https://drive.google.com/file/d/1M3lBSjlZ77Y6hsEtyu89jPA6vIR-KxVR/view?usp=sharing"
        target="_blank">Resume</a>
      <a href="https://www.jinlee.info" target="_blank">Blog</a>
    </div>
  </div>
    <div>
      <Tabs {items} />
    </div>
  </div>
{/if}

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

:global(:root) {
		--dark: #3f3f54;
		--light: #fbf9ec;
    --light-mid: #E9E5CB;
		--dark-mid: #4d8475;
		--accent: #235854;
    --accent-light: #b49fc2;
	}

  :global(*) {
		font-family: 'Inter', sans-serif;
	}

	:global(body) {
		background-color: var(--light);
    font-size: 0.8em;
    margin: 0;
    padding: 0;
	}

  :global(h1) {
    color: var(--accent);
  }

  :global(h3) {
    color: var(--dark-mid);
  }

  :global(p) {
    color:var(--dark);
  }
  
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 16px;
    margin-top: 48px;
    margin-bottom: 20px;
  }

  #header {
    padding-bottom: 15px;
    width: 100%;
    max-width: 600px;
  }

  #nav a {
    padding-right: 2em;
    color: var(--dark-mid);
  }

</style>
