<script lang="ts">
    export let task: string
</script>

<div class="task">
    <div class="task-name">{task}</div>
</div>

<style>
    .task {
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: #f0f0f0;
        padding: 0.5rem;
        margin: 0.5rem;
        border-radius: 0.5rem;
        color: black;
    }

    .task-name {
        font-size: 2em;
        font-weight: bold;
    }
</style>
