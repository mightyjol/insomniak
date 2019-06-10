<script>
	import { stores } from '@sapper/app'
	import { onMount } from 'svelte'

 	import Nav from '../components/Nav.svelte'
 	import Footer from '../components/Footer.svelte'
	
	export let segment;
	
	let { session } = stores()
	let loading = false

	onMount(async () => {
		if(process.browser){
			const mod = await import('../firebase/auth.js')
			let auth = mod.default
			
			auth.onAuthStateChanged(user => {
				if (user) {
					session.update(s => {
						s.user = user
						return s
					})
					console.error('session updated', $session, $session.user)
				} else {
					session.update(s => {
						s.user = undefined
						return s
					})
					console.error('session updated', $session, $session.user)
				}

				loading = false
			});
		}
		
	})
</script>


<svelte:head>
	<title>EasyBiz | Logiciel de caisse simplifié | pour PME et indépendants</title>
</svelte:head>

<Nav {segment} />
<main>
	<slot></slot>
</main>
<Footer />