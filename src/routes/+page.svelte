<script>
  import Tab1 from "./tab1.svelte";
  import Tab2 from "./tab2.svelte";
  import Tab3 from "./tab3.svelte";
  import Tabs from "./tabs.svelte";

  // List of tab items with labels, values and assigned components
  let items = [
    { label: "Work Experience", value: 1, component: Tab1 },
    { label: "School", value: 2, component: Tab2 },
    { label: "Personal Projects", value: 3, component: Tab3 },
  ];
</script>

<body>
  <div class="container">
    <h1>Jin Lee</h1>
    <p>Welcome to my portfolio! Thanks for dropping by.</p>
    <div class="nav">
      <a href="mailto:leejinbc@gmail.com" target="_blank">Email</a>
      <a href="https://www.linkedin.com/in/jin-leebc/" target="_blank">LinkedIn</a>
      <a href="https://www.jinlee.info" target="_blank">Blog</a>
    </div>
    <div>
      <Tabs {items} />
    </div>
  </div>
</body>

<style>
  body {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.9em;
  }

  p {
    color: #3f3f54;
  }

  .container {
    padding: calc(8px + 1.5625vw);
  }

  @media (min-width: 600px) {
    .container {
      padding: calc(8px + 1.5625vw);
    }
  }

  @media (min-width: 900px) {
    .container {
      padding: calc(8px + 1.5625vw);
    }
  }

.nav a {
  padding-right: 2em;
}

</style>
