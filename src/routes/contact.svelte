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

	 

</script>

<style>
	.img{
		background: url('/img/bgindex.jpg') center center;
		background-size: cover;
		height: 50vh;
		min-height: 350px;
		margin-top: 50px;
	}

	.hero-body .container{
		padding-top: 50px;
		padding-bottom: 50px;
	}
</style>

<section class="hero is-white is-fullheight">

	<!-- Hero content: will be in the middle -->
	<div class="hero-body">
		<div class="container">
			<div class="columns">
				<div class="column is-vcentered has-text-centered">
					<h1 class="title is-2">
						Le logiciel de caisse simplifié
					</h1>
					<h2 class="subtitle" style="opacity: 0.7;">
						Conçu pour les petites entreprises et les indépendants
					</h2>
					<div class="buttons is-centered">
						<button on:click="{() => {goto('/contact')}}" class="button is-outlined is-medium">Contacter un expert</button>
						<button on:click="{navigateToLogin}" class="button is-link is-medium">Réserver une démo</button>
					</div>
					
					<div class="img is-fullwidth"></div>
				</div>
			</div>		 
		</div>
	</div>
</section>
<section id="software">
	<div class="container">
		<div class="columns">
			<div class="column"></div>
			<div class="column"></div>
			<div class="column"></div>
		</div>
	</div>
</section>
<section id="ecom">
	<div class="container">
		<div class="columns">
			<div class="column"></div>
			<div class="column"></div>
			<div class="column"></div>
		</div>
	</div>
</section>
<section id="#pricing">
	<div class="container">
		<div class="columns">
			<div class="column">
				<div class="pricing-table">
					<div class="pricing-plan">
						<div class="plan-header">Starter</div>
						<div class="plan-price">
							<span class="plan-price-amount"><span class="plan-price-currency">$</span>20</span>/month
						</div>
						<div class="plan-items">
							<div class="plan-item">20GB Storage</div>
							<div class="plan-item">100 Domains</div>
							<div class="plan-item">-</div>
							<div class="plan-item">-</div>
						</div>
						<div class="plan-footer">
							<button class="button is-fullwidth" disabled="disabled">Current plan</button>
						</div>
					</div>

					<div class="pricing-plan is-warning">
						<div class="plan-header">Startups</div>
						<div class="plan-price">
							<span class="plan-price-amount"><span class="plan-price-currency">$</span>40</span>/month
						</div>
						<div class="plan-items">
							<div class="plan-item">20GB Storage</div>
							<div class="plan-item">25 Domains</div>
							<div class="plan-item">1TB Bandwidth</div>
							<div class="plan-item">-</div>
						</div>
						<div class="plan-footer">
							<button class="button is-fullwidth">Choose</button>
						</div>
					</div>

					<div class="pricing-plan is-active">
						<div class="plan-header">Growing Team</div>
							<div class="plan-price">
								<span class="plan-price-amount"><span class="plan-price-currency">$</span>60</span>/month
							</div>
							<div class="plan-items">
							<div class="plan-item">200GB Storage</div>
							<div class="plan-item">50 Domains</div>
							<div class="plan-item">1TB Bandwidth</div>
							<div class="plan-item">100 Email Boxes</div>
						</div>
						<div class="plan-footer">
							<button class="button is-fullwidth">Choose</button>
						</div>
					</div>
				</div>					
			</div>
		</div>
	</div>
</section>