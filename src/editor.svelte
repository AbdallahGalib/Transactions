<span> 
    <input bind:value = {item.name} placeholder = "Name" />
    <input bind:value = {item.amount} placeholder = "Amount" />
</span>

<script>
    export let item = {name:'', amount:0}
</script>