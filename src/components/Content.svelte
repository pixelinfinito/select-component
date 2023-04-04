<script>
    import {createEventDispatcher} from "svelte"
    import {keyItems} from "../store"
    export let data
    export let key
    const emit = createEventDispatcher()
    $: {
        keyItems.subscribe(e=>{
            console.log(e[key], 'value store')
            data = e[key] 
        })
    }
    function handleClick(item){
        emit('handleClick', {data: item.data})
    }

</script>
<div  class="content">
    {#each data as item}
        <div on:click={handleClick(item)}  class="info">
            <h3>{item.title}</h3>
            <span>{item.description}</span>
        </div>
    {/each}
</div>

<style>
    .content{
        overflow-y: auto;
        height: calc(100% - 19%);
        margin-top: -1px;
        padding: 10px;
	}
    :global(
    .container .row:first-child  .col:nth-child(1) .content,
    .container .row:first-child  .col:nth-child(3) .content,
    .container .row:first-child  .col:nth-child(5) .content){
        height: calc(100% - 10%) !important;
    }
	.info{   
		text-indent: 0;
		border-radius: 3px;
		font-size: 12px;
        box-shadow: 0 1px 1px 0 rgb(0,0,0,.4);
        margin-bottom: 12px;
        text-align: center;
        padding: 20px;
        height: fit-content;
        background-color: #fdf092;
        flex: 1 0 calc(100% /4);
	}
    .info span {
        display: block;
    }
    :global(.row:last-child .content){
        display: flex;
        flex-wrap: wrap;
        align-items: start;
        gap: 33px;
    }
    .content h3, .content span{
        text-align: left;
    }
    .content h3{
        font-weight: bold;
    }
    
</style>