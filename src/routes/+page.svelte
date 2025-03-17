<!-- src/routes/+page.svelte-->
<script>
	import { page } from "$app/state";
    import Hero from '$lib/components/Hero.svelte'
</script>

<main>
    <Hero />
</main>

<style>
    * {
        overflow-x: hidden;
    }
</style>