<script lang="ts">
    // You can write TypeScript here.
    const world = 'World!';
</script>

<div>
    <!-- You can write HTML here. -->
    <h1>Hello <div class="accented">{world}</div></h1>
</div>

<style>
    /* You can write CSS here, it will be scoped to this component. */
    h1 {
        font-family: Montserrat;
        font-size: 2em;
        display: flex;
        gap: 0.2em;
    }
    .accented {
        color: var(--clr-accent);
    }
</style>
