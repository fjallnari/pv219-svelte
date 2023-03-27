<script lang="ts">
    import Icon from '@iconify/svelte';
    import { createEventDispatcher } from 'svelte';
    import type ChipInterface from '../interfaces/ChipInterface';
    import InPlaceEdit from './InPlaceEdit.svelte';

    export let chip: ChipInterface;
    export let color: string = 'var(--clr-box-bg-light)';

    const dispatch = createEventDispatcher();

    function deleteChip() {
        dispatch('delete', {
            chip
        });
    }

</script>

<box class='chip' style="background-color: {color};">
    <sendable class="delete-chip" on:click={() => deleteChip()} on:keyup={() => {}}>
        <Icon class="big-icon" icon="mdi:close" />
    </sendable>
    <InPlaceEdit bind:value={chip.label} editWidth='6rem' editHeight='1.5rem' on:submit={() => {}}/>
</box>

<style>
    .chip {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
        gap: 0.2em;
        font-size: 1em;
        padding: 0.4em;
        flex-wrap: wrap;
        max-width: 90%;
    }

    .delete-chip {
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
</style>