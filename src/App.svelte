<script lang="ts">
    import type ChipInterface from "./interfaces/ChipInterface";
    import BoxWithChips from "./lib/BoxWithChips.svelte";
    import HelloWorld from "./lib/HelloWorld.svelte";

    let chipsArray: ChipInterface[] = [];

    $: firstLetters = chipsArray.map(chip => chip.label[0]);
</script>

<main>
  <HelloWorld/>
  <BoxWithChips bind:chipsArray label="Generic chip array"></BoxWithChips>
  <h4>First letters of chips are: {firstLetters.length ? firstLetters: 'None'}</h4>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
</style>
