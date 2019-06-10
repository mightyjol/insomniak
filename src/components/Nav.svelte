<script>
	import { slide } from 'svelte/transition'

	export let segment
	
	let active = false

	function toggleMenu(){
		active = !active
	}

	function closeMenu(){
		active = false
	}


</script>

<nav class="navbar has-shadow is-fixed-top" role="navigation" aria-label="main navigation">
	<div class="navbar-brand">
		<a class="navbar-item has-text-link" href="/">
			<span class="level is-mobile">
				<span class="level-item">
					<img src="https://ik.imagekit.io/financeimmo/logo_cu-PtgRR-.png?tr=h-250" height="28">
				</span>
				<span class="level-item" style="margin-left: 10px;">
					<h5 class="title is-5">EasyBiz</h5>
				</span>
			</span>
		</a>

		<a class:is-active="{active}" on:click="{toggleMenu}" role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
			<span aria-hidden="true"></span>
			<span aria-hidden="true"></span>
			<span aria-hidden="true"></span>
		</a>
	</div>
	
	<div class="navbar-menu is-hidden-touch">
		<div class="navbar-start">
			<a on:click="{closeMenu}" href="/#software" class="navbar-item">Logiciel de caisse</a>
			<a on:click="{closeMenu}" href="/#ecom" class="navbar-item">eCommerce</a>
			<a on:click="{closeMenu}" href="/#prix" class="navbar-item">Prix</a>
		</div>

		<div class="navbar-end">
			<div class="navbar-item">
				<div class="buttons">
					<a class="button is-outlined" href="tel:0478090780">+32 478 09 07 80</a>
					<a class="button is-link">Essai gratuit</a>
				</div>
			</div>
		</div>
	</div>

	{#if active}
		<div transition:slide="{{duration:350}}" id="navbarBasicExample" class="navbar-menu is-active is-hidden-desktop">
			<div class="navbar-start">
				<a on:click="{closeMenu}" href="/#software" class="navbar-item">Logiciel de caisse</a>
				<a on:click="{closeMenu}" href="/#ecom" class="navbar-item">eCommerce</a>
				<a on:click="{closeMenu}" href="/#prix" class="navbar-item">Prix</a>
			</div>

			<div class="navbar-end">
				<div class="navbar-item">
					<div class="level is-mobile">
						<div class="level-left">
							<div class="level-item">
								<a class="button is-outlined" href="tel:0478090780">+32 478 09 07 80</a>
							</div>
						</div>
						<div class="level-right">
							<div class="level-item">
								<a class="button is-link">
									Essai gratuit
								</a>
							</div>
						</div>
					</div>
				</div>

			</div>
		</div>
	{/if}
</nav>