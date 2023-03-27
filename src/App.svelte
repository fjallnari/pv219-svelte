<script lang="ts">
    import type ChipInterface from "./interfaces/ChipInterface";
    import BoxWithChips from "./lib/BoxWithChips.svelte";
    import HelloWorld from "./lib/HelloWorld.svelte";

    let chipsArray: ChipInterface[] = [];
</script>

<main>
  <HelloWorld/>
  <BoxWithChips bind:chipsArray label="Generic chip array"></BoxWithChips>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
</style>
