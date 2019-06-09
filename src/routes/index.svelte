<script>
	import { stores } from "@sapper/app"
	import { onMount } from "svelte"

	const { session } = stores()
	$:user = $session.user

	let client;
	let dark = true;
	let light = false;

	onMount(async () => {
		if(process.browser){
			client = await import("../firebase/firebase.js") 
		}
	})

	function navigateToLogin(){
		//
	}

	function navigateToRequest(){
		//
	}

</script>

<style>
	.spec{
		height: auto;
		max-height: 80vh;
	}
</style>

<section class="hero is-light is-fullheight">
	<!-- Hero head: will stick at the top
	<div class="hero-head">
		<header class="navbar">
			<div class="container">
				<div class="navbar-brand">
					<a class="navbar-item">
						<img src="img/logo.png" alt="Logo">
					</a>
					<span on:click="{toggleMenu}" class="navbar-burger burger" data-target="navbarMenuHeroC">
						<span></span>
						<span></span>
						<span></span>
					</span>
				</div>
				<div id="navbarMenuHeroC" class="navbar-menu">
					<div class="navbar-end">
						<a class="navbar-item is-active">
							Home
						</a>
						<a class="navbar-item">
							Examples
						</a>
						<a class="navbar-item">
							Documentation
						</a>
						<span class="navbar-item">
							<a class="button is-success is-inverted">
								<span>Download</span>
							</a>
						</span>
					</div>
				</div>
			</div>
		</header>
	</div>
	-->

	<!-- Hero content: will be in the middle -->
	<div class="hero-body init">
		<div class="container">
			<div class="columns">
				<div class="column is-vcentered">
					<h1 class="title">
						Développeur Indépendant
					</h1>
					<h2 class="subtitle">
						Expert en technologies du web
					</h2>
					<button on:click="{navigateToLogin}" class="button is-outlined">Se connecter</button>
					<button on:click="{next}" class="button is-dark">Mon travail</button>
				</div>
				<div class="column">
					<div class="columns">
						<div class="spec column has-background-light">
						</div>
					</div>
				</div>			
			</div>		 
		</div>
	</div>
</section>