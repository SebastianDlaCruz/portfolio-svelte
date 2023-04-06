<script lang="ts">
	import 'virtual:windi.css';
	import Header from "$lib/components/Header.svelte";
	import gopherXl from "$lib/assets/gopher-xl.png";
	import gopherLg from "$lib/assets/gopher-lg.png";
	import gopherAbout from "$lib/assets/about.png";
	let x: number;
	let y: number;
	let dark = false;

	const toggleDarkMode = () => {
		window.document.body.classList.toggle('dark-mode');
		dark = !dark;
	}
</script>

<svelte:head>
	<title>I'm Henrry Bourgeot</title>
</svelte:head>
<svelte:window bind:innerWidth={x} bind:innerHeight={y} />
<svelte:body />
<div>
	<Header {dark} func={toggleDarkMode} />
	<main
		class={`${x < 768 ? 'flex-col mb-10' : ''} flex justify-center max-w-screen-xl mx-auto items-center`}
		style={`--height: ${(x < 768) ? y : y - 120}px`}
	>
		<section class="{x<768 ? 'w-full' : 'w-1/2'} flex flex-col gap-3 p-6 justify-center">
			<h3 class="text-xl font-bold">Hi there! I'm</h3>
			<h2 class="text-5xl mb-6">
				Henrry Bourgeot, a Fullstack Developer based in Maracay, Venezuela
			</h2>
			<p class="text-xl mb-12">
				I have professional experience working with Svelte, Python, Go, and other languages and
				frameworks that you will find in the <a href="#skills">skills section</a> of this page.
			</p>
			<a href="#projects" class="border-4 border-blue-600 mx-auto ml-0 py-3 px-7">See projects</a>
		</section>
		{#if x > 768}
			<img src={gopherXl} class="w-150" alt="Gopher" />
		{:else}
			<img src={gopherLg} class="w-150" alt="Gopher" />
		{/if}
	</main>
	<section id="about" class="mx-auto flex items-center space-between transition-bg duration-500 { !dark ? 'bg-blue-200' : 'bg-blue-900'} {x < 768 ? 'h-full': 'h-screen'}">
		<img src={gopherAbout} alt="myGopher" class="w-1/2 {x < 768 ? 'hidden' : ''}"   />
		<div class="p-10">
			<h2 class="text-5xl font-bold mb-10">About me</h2>
			<p class="text-xl leading-relaxed w-9/12 mb-5">
				I'm from Venezuela and I have 20 years old, actually I study the sixth semester of ten of the Systems Engineer major from the Polytechnic
				University Institute <em>Santiago Mariño</em>. Also, I love teach others about
				IT topics. My hobbie are the videogames and enjoy the life with my friends and family.
			</p>
			<p class="text-xl leading-relaxed w-9/12">
				I've 1 year working as a FullStack Dev. in my actual work, I use technologies as Svelte, Python,
				TypeScript and others. If you hire me, you'll get clean code and the best practices for make a clean and
				readable code. However, something that I like of programming, is resolve problems that are really
				annoying.
			</p>
		</div>
	</section>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600&display=swap');

	:global(html) {
		scroll-behavior: smooth;
	}
	:global(body) {
		font-family: 'Raleway', sans-serif;
		transition: background-color 500ms, color 500ms;
	}

	:global(body.dark-mode) {
		background-color: #222;
		color: #eee;
	}

	main.justify-center {
		height: var(--height);
	}
</style>
