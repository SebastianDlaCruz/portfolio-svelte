<script lang="ts">
	import { Moon, Sun } from '@steeze-ui/tabler-icons';
	import { Icon } from '@steeze-ui/svelte-icon';
	export let dark: boolean;
	export let func: any;
</script>

<header
	class="{!dark
		? 'bg-light-900/25'
		: 'bg-dark-900/2'} z-5 backdrop-filter backdrop-blur-lg sticky top-0 flex justify-between mx-auto p-10"
>
	<h1 class="text-3xl font-bold {!dark ? 'text-[#576CBC]' : 'text-[#A5D7E8]'}">
		<a href="/">Henrry Bourgeot</a>
	</h1>
	<nav class="flex justify-around w-1/2 items-center">
		<a href="#about">About Me</a>
		<a href="#skills">Skills</a>
		<a href="#projects">Projects</a>
		<a href="#contact">Contact</a>
		<button on:click={func} class="rounded-2xl bg-gray-500/30 h-4 w-15 flex items-center gap-5">
			<Icon
				src={!dark ? Moon : Sun}
				class="p-1 rounded-1/2 h-8 w-8 transition-margin duration-500 {!dark
					? 'text-[#eee] bg-[#222]'
					: 'text-[#222] bg-[#eee] justify-self-end ml-7'}"
			/>
		</button>
	</nav>
</header>

<style>
	.p-1 {
		transition: margin-right 500ms;
	}
</style>
