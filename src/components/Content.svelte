<script>
    import {createEventDispatcher} from "svelte"

    export let data

    const emit = createEventDispatcher()

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
        margin-top: 15px;
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
	}
    .info span {
        display: block;
    }
    :global(.row:last-child .content){
        justify-content: space-between;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
    }
    .content h3, .content span{
        text-align: left;
    }
    .content h3{
        font-weight: bold;
    }
    
</style>