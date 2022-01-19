<script>
	import { onMount } from "svelte";
	import Card from './components/Card.svelte'
	import NavigationBarNiezalogowany from "./components/Navigation_Bar_niezalogowany.svelte";
	import NavigationBarZalogowany from "./components/Navigation_Bar_zalogowany.svelte";
		let name = 'Tomek';
	let articles = [];
	onMount(async () => {
		try{
		const response = await fetch('http://localhost:8899/api/articles');
		const data = await response.json();
		console.log(data.articles);
		articles = data.articles;
		} catch(error){
			console.log(error)
		}
	});
</script>



<main>

<NavigationBarZalogowany></NavigationBarZalogowany>

	
	{#each articles as article}
	<div>
		<Card>
			<div class="photo">
				<img src="https://dbdzm869oupei.cloudfront.net/img/sticker/preview/20084.png" width="400px" height="300px">
			</div>
			<div class="title">
				<h3>{article.title}</h3>
			</div>
			<div class="price">
				<h4>Author: {article.author.name}</h4>
			</div>
			<div class="descr">
				<p>{article.body}</p>
			</div>
		</Card>
	</div>
	{/each}
	
	
</main>




<style>
	/* Content strony */
	
	
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	
	


	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}


	/* Styling card contents */
	.title{
		color: black;
		font-weight: bold;
		margin: 0.5em
	}
	.price{
		text-align: left;
		color: #5465FF;
		font-weight: 200;
		margin: 0.5em;
	}
	.descr{
		color: #5465FF;
		margin: 0.5em;
		text-align: left;
	}
	
</style>