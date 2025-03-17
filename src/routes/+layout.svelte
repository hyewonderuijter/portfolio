<script>
	import Header from '$lib/components/Header.svelte';
    import '$lib/styles/style.css';
	import Footer from '$lib/components/Footer.svelte'
</script>



<main>
	<Header />
	<slot />
	<Footer />
</main>
