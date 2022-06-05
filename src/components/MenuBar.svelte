<script lang="ts">
    import { createEventDispatcher } from 'svelte'

    const dispatch = createEventDispatcher()

    const push = (name: string) => dispatch('push', { name })
    const pop = () => dispatch('pop')
    const swap = () => dispatch('swap')
    const reverse = () => dispatch('reverse')
    const up = () => dispatch('up')
    const down = () => dispatch('down')
</script>

<div class="menu-bar">
    <div
        class="menu-bar-button push-button"
        on:click={() => push(prompt('Task Name') || 'New Task')}
    >
        Push
    </div>
    <div class="menu-bar-button pop-button" on:click={pop}>Pop</div>
    <div class="menu-bar-button swap-button" on:click={swap}>Swap</div>
    <div class="menu-bar-button reverse-button" on:click={reverse}>Reverse</div>
    <div class="menu-bar-button cycle-up-button" on:click={up}>Cycle Up</div>
    <div class="menu-bar-button cycle-down-button" on:click={down}>
        Cycle Down
    </div>
</div>
<div class="padder-menu-bar">
    <div class="menu-bar-button push-button">Push</div>
    <div class="menu-bar-button pop-button">Pop</div>
    <div class="menu-bar-button swap-button">Swap</div>
    <div class="menu-bar-button reverse-button">Reverse</div>
    <div class="menu-bar-button cycle-up-button">Cycle Up</div>
    <div class="menu-bar-button cycle-down-button">Cycle Down</div>
</div>

<style>
    .padder-menu-bar,
    .menu-bar {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        top: auto;
        bottom: 0;
        padding: 0;
        background-color: #2d2d31;
    }

    .padder-menu-bar {
        visibility: hidden;
    }

    .menu-bar {
        position: fixed;
    }

    .menu-bar-button {
        margin: 0.5rem;
        padding: 0.5rem;
        border-radius: 0.5rem;
        background-color: #f0f0f0;
        color: black;
        flex-grow: 1;
        text-align: center;
    }

    .menu-bar-button:hover {
        background-color: #e0e0e0;
    }

    .menu-bar-button:active {
        background-color: #c0c0c0;
    }
</style>
