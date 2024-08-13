<script>
	import Map from "./sections/Map.svelte";
	import ConfirmarAsistencia from "./sections/ConfirmarAsistencia.svelte";
	import Agendar from "./sections/Agendar.svelte";
	import Dress from "./sections/Dress.svelte";
	import Mensaje from "./sections/Mensaje.svelte";
	import Instagram from "./sections/Instagram.svelte";
	import Presentacion from "./sections/Presentacion.svelte";
	import Hero from "./sections/Hero.svelte";
	import Contador from "./sections/Contador.svelte";
	import Footer from "./sections/Footer.svelte";
</script>


<style>
	
	main {
		background-color: var(--seasalt);
	}

</style>


<main>
	<Hero />
	<Presentacion />
	<Contador />
	<Map />
	<ConfirmarAsistencia />
	<Agendar />
	<Dress />
	<Mensaje />
	<Instagram />
	<Footer />
</main>
