<script lang="ts">
  import { fly } from "svelte/transition";

  let selectedIndex = 0;

  const changeTab = (index: number) => {
    selectedIndex = index;
  };
</script>

<div class="vertical-tab-container">
  <ul class="vertical-tab">
    <li class:selected={selectedIndex == 0} on:click={() => changeTab(0)}>
      First Tab
    </li>

    <li class:selected={selectedIndex == 1} on:click={() => changeTab(1)}>
      Second Tab
    </li>

    <li class:selected={selectedIndex == 2} on:click={() => changeTab(2)}>
      Third Tab
    </li>
  </ul>

  <div class="vertical-tab-content">
    {#if selectedIndex == 0}
      <div transition:fly>
        <h2>First Tab Heading</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus
          doloremque, velit delectus omnis iste quibusdam, minus iure facere
          harum illum consequuntur quia est laborum, ad vel veniam ullam eos
          nulla?
        </p>
      </div>
    {:else if selectedIndex == 1}
      <div transition:fly>
        <h2>Second Tab Heading</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint
          laudantium reiciendis doloribus nesciunt sit architecto voluptatem,
          maxime alias sunt commodi!
        </p>
      </div>
    {:else}
      <div transition:fly>
        <h2>Third Tab Heading</h2>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Explicabo,
          officiis.
        </p>
      </div>
    {/if}
  </div>
</div>

<style>
  .vertical-tab-container {
    width: 680px;
    display: flex;
    flex-direction: row;
    align-items: center;
    border: 1px solid #85ffbd;
    border-radius: 1rem;
    background-color: #fbab7e;
    background-image: linear-gradient(62deg, #fbab7e 0%, #f7ce68 100%);
    overflow: hidden;
  }

  .vertical-tab {
    margin: 0;
    font-size: 1.25rem;
    text-align: start;
    padding: 3rem;
    list-style: none;
    border-right: 1px solid gray;
    background-color: #0093e9;
    background-color: #85ffbd;
    background-image: linear-gradient(45deg, #85ffbd 0%, #fffb7d 100%);
    border-radius: 1rem;
  }

  .vertical-tab li {
    margin: 2rem 0;
    cursor: pointer;
  }

  .vertical-tab-content {
    flex: 1;
  }
  .selected {
    color: #fbab7e;
  }
</style>
