<script>
	import Hero from "./sections/Hero.svelte";
	import Contador from "./sections/Contador.svelte";
	import Map from "./sections/Map.svelte";
	import Agendar from "./sections/Agendar.svelte";
	import Mensaje from "./sections/Mensaje.svelte";
	import Instagram from "./sections/Instagram.svelte";
	import Regalos from "./sections/Regalos.svelte";
	import Footer from "./sections/Footer.svelte";
</script>


<style>
	
	main {
		background-color: var(--seasShell);
		overflow: hidden;
	}

</style>


<main>
	<Hero />
	<Contador />
	<Map />
	<Agendar />
	<Mensaje />
	<Instagram />
	<Regalos />
	<Footer />
</main>
