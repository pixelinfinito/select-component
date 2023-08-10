<script>
  import { getContext } from "svelte";
  import Select from 'svelte-select';
  import { onMount } from "svelte";
 
  const { styleable } = getContext("sdk"); 
  const component = getContext("component");

  export let multiple;
  export let dataProvider
  export let label
  export let disable
  export let selectEvent
  export let placeholder 
  export let required
  export let placeholderAlwaysShow

  let items = []
  
  async function fetchData() {
    try {
      const response = dataProvider;
      
      items = response?.rows?.map((item, index)=>{
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
 
  onMount(()=>{
   fetchData()
  })

  async function handleSelectChange(event) {
    
    const selectedValue = event.detail
    const dataSend = JSON.parse(JSON.stringify(selectedValue?.item))
    
    await selectEvent({
      data: dataSend
    })
  }

</script>

<div use:styleable={$component.styles}>
  <Select disabled={disable} placeholderAlwaysShow={placeholderAlwaysShow} required={required} {items} placeholder={placeholder} multiple={multiple} class="foo bar" on:change={handleSelectChange} />
</div>
