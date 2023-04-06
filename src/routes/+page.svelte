<script lang="ts">
import "virtual:windi.css"
import Header from "$lib/components/Header.svelte";
import gopherXl from "$lib/assets/gopher-xl.png";
import gopherLg from "$lib/assets/gopher-lg.png";
let x: number;
let y: number;

</script>
<svelte:head>
	<title>I'm Henrry Bourgeot</title>
</svelte:head>
<svelte:window bind:innerWidth={x} bind:innerHeight={y}/>
	<svelte:body class="transition-all duration-500"/>
<div>
	<Header/>
	<main class={`${x < 768 ? "flex-col" : ""} flex justify-center max-w-screen-xl mx-auto items-center`} style={`--height: ${x<768 ? y-50 : y-120}px`}>
		<section class="w-1/2 flex flex-col gap-3 p-6 justify-center">
			<h3 class="text-xl font-bold">Hi there! I'm</h3>
			<h2 class="text-5xl mb-6">Henrry Bourgeot, a Fullstack Developer based in Maracay, Venezuela</h2>
			<p class="text-xl mb-12">I have professional experience working with Svelte, Python, Go, and other languages and frameworks that you will find in the <a href="#skills">skills section</a> of this page.</p>
			<a href="#projects" class="border-4 border-blue-600 mx-auto ml-0 py-3 px-7">See projects</a>
		</section>
		{#if x > 768}
			<img src={gopherXl} class="w-150" alt="Gopher"/>	
		{:else}
			<img src={gopherLg} class="w-150" alt="Gopher"/>
		{/if}
	</main>

	<section id="about" class="sm:container mx-auto">
		<div>
		<h2 class="text-xl font-bold">About me</h2>

		</div>
		<img src="" alt="">
	</section>
</div>
<style>
    @import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600&display=swap');
	:global(body) {
		font-family: 'Raleway', sans-serif;
		transition: background-color 500ms, color 500ms;

	}

	:global(body.dark-mode){
		background-color: #222;
		color: #eee;
	}

	main.justify-center{
		height: var(--height);
	}

</style>
