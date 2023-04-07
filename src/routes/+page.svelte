<script lang="ts">
	import 'virtual:windi.css';
	import {
		Bolt,
		Hexagon,
		HexagonLetterE,
		Coffee,
		Pepper,
		BrandAmazon,
		BrandHtml5,
		BrandCss3,
		BrandBootstrap,
		BrandTailwind,
		BrandCpp,
		Sql,
		BrandGit,
		BrandJavascript,
		BrandVue,
		BrandSvelte,
		BrandTypescript,
		BrandSolidjs,
		BrandGolang,
		BrandPython,
		BrandDocker
	} from "@steeze-ui/tabler-icons"
	import {Icon} from "@steeze-ui/svelte-icon";
	import Header from "$lib/components/Header.svelte";
	import gopherXl from "$lib/assets/gopher-xl.png";
	import gopherLg from "$lib/assets/gopher-lg.png";
	import about from "$lib/assets/about.jpeg";
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
			<a href="#projects" class="border-4 border-[#576CBC] mx-auto ml-0 py-3 px-7">See projects</a>
		</section>
		{#if x > 768}
			<img src={gopherXl} class="w-150" alt="Gopher" />
		{:else}
			<img src={gopherLg} class="w-150" alt="Gopher" />
		{/if}
	</main>
	<section id="about" class="py-5 px-5 mx-auto flex justify-center items-center transition-bg duration-500 { !dark ? 'bg-[#A5D7E8]' : 'bg-[#19376D]'} {x < 1100 ? 'h-full w-full px-0': 'h-screen'}">
		<div class="flex items-center md:container space-between w-full {x < 1024 ? 'flex-col-reverse items-center' : ''}">
		<article class="{x<1024 ? 'self-center' : ''} w-full">
			<img src={about} alt="Pic with IA" class="shadow-xl mb-7 w-full rounded-md w-3/2 mx-auto" />
			<p class="text-lg text-center font-bold">Image generated with IA</p>
		</article>
		<article class="p-20 {x<1100 ? 'w-full p-5' : 'w-13/12'}">
			<h2 class="text-5xl font-bold mb-10">About me</h2>
			<p class="text-xl leading-relaxed mb-5 w-11/12">
				I'm from Venezuela and I have 20 years old, actually I study the third year of five
				of the Systems Engineer major from the Polytechnic
				University Institute <em>Santiago Mariño</em>. Also, I love teach others about
				IT topics. My hobbie are the videogames and enjoy the life with my friends and family.
			</p>
			<p class="text-xl leading-relaxed w-11/12">
				I've 1 year working as a FullStack Dev. in my actual work, I use technologies as Svelte, Python,
				TypeScript and others. If you hire me, you'll get clean code and the best practices for make a clean and
				readable code. However, something that I like of programming, is resolve problems that are really
				annoying.
			</p>
		</article>
		</div>
	</section>
	<section id="skills" class="skills p-2 md:p-5">
		<div class="overlay p-2 sm:p-10 caskaydia">
			<h2 class="text-5xl font-bold text-center mb-10">Skills</h2>
			<ul class="icons grids">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandHtml5} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>HTML
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandCss3} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>CSS
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandBootstrap} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Bootstrap
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandTailwind} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Tailwind
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandCpp} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>C++
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandGit} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Git
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandJavascript} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>JavaScript
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandTypescript} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>TypeScript
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandSolidjs} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>SolidJS
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandVue} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Vue
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandSvelte} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Svelte/SvelteKit
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Hexagon} style="stroke: #576CBC; fill: #576CBC" class="h-35 w-35" theme="rounded"/>NodeJS
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandGolang} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Golang
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={HexagonLetterE} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Golang Echo
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandPython} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Python
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Bolt} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>FastAPI
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Pepper} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Flask
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Coffee} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Java
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandDocker} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>Docker
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandAmazon} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>
					Amazon Web Services
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Sql} style="stroke: #576CBC" class="h-35 w-35" theme="rounded"/>SQL
				</li>
			</ul>
		</div>
	</section>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600&display=swap');

	@font-face {
		font-family: 'CaskaydiaCove';
		src: url("src/lib/fonts/Caskaydia Cove Nerd Font Complete Mono Regular.otf");
		font-weight: 700;
	}

	.caskaydia{
		font-family: 'CaskaydiaCove', monospace;
	}

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
  
	.shadow-xl{
		box-shadow: -8px 10px 23px 6px rgba(0,0,0,0.75);
		-webkit-box-shadow: -8px 10px 23px 6px rgba(0,0,0,0.75);
		-moz-box-shadow: -8px 10px 23px 6px rgba(0,0,0,0.75);
	.overlay{
		background-color: #22222299;
		height: 100%;
		width: 100%;
	}
	.skills{
		background-image: url("../lib/assets/skills.png");
		background-position: center center;
		background-attachment: fixed;
		position: relative;
		color: #eeeeee;
	}

	.grids {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
		row-gap: 10%;
	}
</style>
