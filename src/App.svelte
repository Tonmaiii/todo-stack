<script lang="ts">
    import MenuBar from './components/MenuBar.svelte'
    import Stack from './components/Stack.svelte'

    const store = () => localStorage.setItem('stack', JSON.stringify(stack))

    const push = (name: string) => {
        stack = [...stack, name]
        store()
    }

    const pop = () => {
        stack = stack.slice(0, -1)
        store()
    }

    const swap = () => {
        stack = [...stack.slice(0, -2), stack.at(-1), stack.at(-2)]
        store()
    }

    const reverse = () => {
        stack = stack.reverse()
    }

    const up = () => {
        stack = [stack.at(-1), ...stack.slice(0, -1)]
        store()
    }

    const down = () => {
        stack = [...stack.slice(1), stack[0]]
        store()
    }

    let stack: string[] = JSON.parse(localStorage.getItem('stack') || '[]')
</script>

<main>
    <h1>Todo Stack</h1>
    <Stack {stack} />
    <MenuBar
        on:push={e => push(e.detail.name)}
        on:pop={pop}
        on:swap={swap}
        on:reverse={reverse}
        on:up={up}
        on:down={down}
    />
</main>

<style>
    main {
        display: flex;
        min-height: 100%;
        flex-direction: column;
        align-items: center;
    }
</style>
