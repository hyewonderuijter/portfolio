<!-- src/routes/+page.svelte-->
<script>
	import { page } from "$app/state";
    import Hero from '$lib/components/Hero.svelte'
    import About from '$lib/components/Aboutme.svelte'
</script>

<main>
    <Hero />
    <About />
</main>

<style>
    * {
        overflow-x: hidden;
    }
</style>