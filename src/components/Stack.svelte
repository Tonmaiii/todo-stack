<script lang="ts">
    import Task from './Task.svelte'
    export let stack: string[]
</script>

<div class="stack">
    {#each stack as task}
        <Task {task} />
    {/each}
</div>

<style>
    .stack {
        display: flex;
        flex-direction: column-reverse;
        width: 100%;
        margin: 0.5rem;
        margin-top: auto;
    }
</style>
