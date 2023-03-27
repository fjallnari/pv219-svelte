<script lang="ts">
    import { randomColor } from "../util/util";
    import Chip from "./Chip.svelte";
    import Icon from '@iconify/svelte';
    import { nanoid } from 'nanoid/non-secure'
    import type ChipInterface from "../interfaces/ChipInterface";

    export let chipsArray: ChipInterface[] = [];
    export let label: string;

    const addChip = () => {
        const chipId = nanoid(10);
        chipsArray = chipsArray.concat([{ id: chipId, label: chipId, icon: "" }]);
    }

    const deleteChip = (id: string) => {
        chipsArray = chipsArray.filter(chip => chip.id !== id);
    }

</script>

<box class="box-with-chips">
    <sendable class="add-chip" on:click={() => addChip()} on:keyup={() => {}}>
        <Icon class="big-icon" icon="mdi:add" />
    </sendable>
    <div class="chips-array box-main-text">
        {#if chipsArray.length === 0}
            <div>No chips in array.</div>
        {:else}
            {#each chipsArray as chip}
                <Chip bind:chip on:delete={() => deleteChip(chip.id)} />
            {/each}
        {/if}      
    </div>
    <div class="box-justify-filler"></div>
    <div class="box-label">
        {label}
    </div>
</box>

<style>
    .box-with-chips {
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        position: relative;
        padding: 0.5em;
        max-width: 40em;
    }

    .chips-array {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        gap: 0.5em;
        overflow-y: auto;
        scrollbar-width: thin;
        margin-bottom: 0.2em;
        padding: 0.2em;
    }
</style>