<!-- src/routes/+page.svelte-->
<script>
	import { page } from "$app/state";
    import Hero from '$lib/components/Hero.svelte'
    import About from '$lib/components/About.svelte'
    import Work from '$lib/components/Work.svelte'
    import Contact from '$lib/components/Contact.svelte'
</script>

<main>
    <Hero />
    <About />
    <Work />
    <Contact />
</main>

<style>
    * {
        overflow-x: hidden;
    }
</style>