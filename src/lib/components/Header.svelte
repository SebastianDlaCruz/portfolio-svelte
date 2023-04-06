<script lang="ts">
	import {Icon, Moon, Sun} from "svelte-hero-icons"
	let dark: boolean = false;

	const toggleDarkMode = () => {
		window.document.body.classList.toggle('dark-mode');
		dark = !dark;
	}
</script>
<header class="bg-transparent backdrop-blur-sm sticky top-0 flex justify-between max-w-screen-xl mx-auto p-10">
	<h1 class="text-3xl">Henrry Bourgeot</h1>
	<nav class="flex justify-around w-1/2 items-center">
		<a href="#about">About Me</a>
		<a href="#exp">Experience</a>
		<a href="#projects">Projects</a>
		<a href="https://estudiandev.site">Blog</a>
		<a href="#contact">Contact</a>
		<button on:click={toggleDarkMode} class="rounded-2xl bg-gray-500/30 h-4 w-15 flex items-center gap-5">
			<Icon src={!dark ? Moon : Sun} class="p-1 rounded-1/2 h-8 w-8 transition-margin duration-500 {!dark ? 'text-[#eee] bg-[#222]' : 'text-[#222] bg-[#eee] justify-self-end ml-7'}"/>
		</button>
	</nav>
</header>

<style>
	.p-1{
		transition: margin-right 500ms;
	}
</style>
