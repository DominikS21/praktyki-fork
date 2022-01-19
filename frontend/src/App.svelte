<script>
	import { onMount } from "svelte";
	import Card from './components/Card.svelte'
	import Navigation_Bar_Niezalogowany from "./components/Navigation_Bar_niezalogowany.svelte";
	import Navigation_Bar_zalogowany from "./components/Navigation_Bar_zalogowany.svelte";
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

<div class="bar">
	<h1>DMK</h1>
	<input type="text" placeholder="wyszukiwanie">
	<a href="#asda">Logowanie</a>
					
</div>
	
	{#each articles as article}
	<div>
		<Card>
			<div class="photo">
				<h3>{article.title}</h3>
			</div>
			<div class="descr">
				<h4>Author: {article.author.name}</h4>
			</div>
			<div class="price">
				<p>{article.body}</p>
			</div>
		</Card>
	</div>
	{/each}
	
	
</main>




<style>
	/* Content strony */
	
	.bar{
  	background-color: #BFD7FF;
  	text-align: center;
  	padding: 20px 20px;
	
	}
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

<<<<<<< HEAD
	h1 {
		color: #5465FF;
		text-transform: uppercase;
		font-size: 64px;
		font-weight: 500;
		display: inline;
		
	}
	


=======
>>>>>>> 49c08d63c47053b9f57b6c3c8bd0980441ef95a6
	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}


	/* Styling card contents */
	.photo{
		color: black;
		font-weight: bold;
		margin: 0.5em
	}
	.descr{
		text-align: left;
		color: #5465FF;
		font-weight: 200;
		margin: 0.5em;
	}
	.price{
		color: #5465FF;
		margin: 0.5em;
		text-align: right;
	}
	
</style>