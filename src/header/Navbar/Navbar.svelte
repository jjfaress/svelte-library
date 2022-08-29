<script lang='ts'>
    import type { SvelteComponent } from "node_modules/svelte/types/runtime/internal/Component.js";
    export let style: string | undefined = undefined;
    export let width: string = '100vw';
    export let button: SvelteComponent | null = null;
    export let content: {title: string, path: string}[] = [
        {
            'title': 'item1',
            'path': 'path1'
        },
        {
            'title': 'item2',
            'path': 'path2'
        },
        {
            'title': 'item3',
            'path': 'path3'
        },
    ]
</script>

<ul class="list" style="width: {width};">
    {#if button == null}
        {#each content as item}
            <li class='item'>
                <a href={item.path} class="link">
                    {item.title}
                </a> 
            </li>
        
        {/each}
    {:else}
        {#each content as item}
            <li class='item'>
                <a href={item.path} class='link'>   
                    <svelte:component this={button}>
                        <span class='label'>
                            {item.title}
                        </span>        
                    </svelte:component>
                </a> 
            </li>
        {/each}
    {/if}
</ul>


{#if style != undefined}
    <style src={style}></style>
{:else}
    <style src='./Navbar.scss'></style>
{/if}

