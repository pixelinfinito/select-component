<script>
  import { getContext } from "svelte"
  import Select from 'svelte-select'
  import { onMount } from "svelte"
 
  const { styleable } = getContext("sdk")
  const component = getContext("component")

  export let multiple;
  export let dataProvider
  export let label = ''
  export let disable
  export let selectEvent
  export let placeholder 
  export let placeholderAlwaysShow
  export let defaultValue
  export let onClear

  let items = []

  async function fetchData() {
    try {
      const response = dataProvider;
      
      items = response?.rows?.map((item, index)=>{
        console.log(item)
        return {
          value: item[label],
          label: item[label],
          item: item 
        }
      })
    } catch (error) {
      console.error("Error fetching data:", error);
    }
  }

  $:{
    console.log(label, 'changed value', placeholder)
    fetchData()
  }
 
  onMount(()=>{
   fetchData()
  })

  async function handleSelectChange(event) {
    
    const selectedValue = event.detail    
    let itemSend = []

    if(multiple){
      
      const result = selectedValue?.map((item)=>{
        return {
          ...item?.item
        }
      })

      itemSend = result
    }else{
      itemSend = selectedValue?.item
    }
    const dataSend = JSON.parse(JSON.stringify(itemSend))

    await selectEvent({
      data: dataSend
    })
  }

  async function handleClear(item){
    console.log(item.detail)
    const dataSend = JSON.parse(JSON.stringify(item.detail))

    await onClear({
      data: dataSend
    })
  }

</script>

<div use:styleable={$component.styles}>
  <Select on:clear={handleClear} value={defaultValue}  disabled={disable} placeholderAlwaysShow={placeholderAlwaysShow}  {items} placeholder={placeholder} multiple={multiple} class="foo bar" on:change={handleSelectChange} />
</div>