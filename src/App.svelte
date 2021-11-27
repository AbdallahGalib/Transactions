
<div>

	<ul>
		{#each funds as fund}
			<li on:click = {() => {select(fund)}} class:selected = {fund == selectedFund} grid-2 class = "fund" full><span>{fund.name}</span><span amount>{fund.amount} {fund.cur || 'tk'}</span></li>
		{/each}
	</ul>
	<Editor bind:item = {selectedFund}></Editor>	
</div>



<script>
	import Editor from './editor.svelte'
	let selectedFund = {}, funds = [
		{name:'Abdallah', amount:100}, 
		{name:'Afia Anwar', amount: 3000}, 
		{name:'Pahely', amount:500}, 
		{name:'House Hold', amount:120, cur:'$'},
	]
	function select(fund){
		selectedFund = fund
	}
</script>
		 
<style>
	[grid-2] {display: grid; grid-template-columns: repeat(2, 1fr);}
	
	.fund { gap:2rem; }
	[amount] {text-align:right;}
	[full] {width:100%;}
	ul, li {padding:0.5rem;; margin: 0}
	* { box-sizing: border-box; }
	.selected {background: darkgreen; color:black;}
</style>



