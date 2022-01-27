<script>
	import { onMount } from "svelte";
	import Card from './components/Card.svelte'
	import NavigationBarNiezalogowany from "./components/Navigation_Bar_niezalogowany.svelte";
	import NavigationBarZalogowany from "./components/Navigation_Bar_zalogowany.svelte";
	import Footer from "./components/Footer.svelte";
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
	<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@100&display=swap" rel="stylesheet">

<NavigationBarZalogowany></NavigationBarZalogowany>

	<h6>Ogłoszenia</h6>
	
 
<div class="Card-div">

	<div>
		<Card>
			<div class="photo">
				<!-- svelte-ignore a11y-missing-attribute -->
				<img src="https://dbdzm869oupei.cloudfront.net/img/sticker/preview/20084.png" width="300px" height="150px">
			</div>
			<div class="title">
				<h3>Nazwa_ogłoszenia</h3>
			</div>
			<div class="price">
				<h4>CENA</h4>
			</div>
			<div class="descr">
				<p>Opis</p>
			</div>
		</Card>
	</div>

	<div>
		<Card>
			<div class="photo">
				<!-- svelte-ignore a11y-missing-attribute -->
				<img src="https://dbdzm869oupei.cloudfront.net/img/sticker/preview/20084.png" width="300px" height="150px">
			</div>
			<div class="title">
				<h3>Nazwa_ogłoszenia_1</h3>
			</div>
			<div class="price">
				<h4>CENA_1</h4>
			</div>
			<div class="descr">
				<p>Opis_1</p>
			</div>
		</Card>
	</div>

	<div>
		<Card>
			<div class="photo">
				<!-- svelte-ignore a11y-missing-attribute -->
				<img src="https://dbdzm869oupei.cloudfront.net/img/sticker/preview/20084.png" width="300px" height="150px">
			</div>
			<div class="title">
				<h3>Nazwa_ogłoszenia_2</h3>
			</div>
			<div class="price">
				<h4>CENA_2</h4>
			</div>
			<div class="descr">
				<p>Opis_2</p>
			</div>
		</Card>
	</div>
	
	<Footer>
	</Footer>
	
</div>
</main>




<style>
	/* Content strony */
	
	:global(body) {
        background-color: #2A2B2E;
        align-items: center;
        overflow:hidden;
        box-sizing: border-box;
    }
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0px auto;
	}
	h6 {
		font-weight: bold;
		margin-left: 70px;
		margin-top: 20px;
		font-size: 30px;
		color: #06D6A0;
	}
	
	.Card-div{
        width: 100vw;
        height: 50vh;

        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;

    }
	


	

	@media (min-width: 650px) {
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