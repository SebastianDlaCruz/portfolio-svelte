<script lang="ts">
	import 'virtual:windi.css';
	import {
		Bolt,
		Hexagon,
		HexagonLetterE,
		Coffee,
		Pepper,
		Wind,
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
		BrandDocker,
		Database
	} from '@steeze-ui/tabler-icons';
	import { Icon } from '@steeze-ui/svelte-icon';
	import Header from '$lib/components/Header.svelte';
	import gopherXl from '$lib/assets/gopher-xl.png';
	import gopherLg from '$lib/assets/gopher-lg.png';
	import about from '$lib/assets/about.jpeg';
	import { createSearchStore, searchHandler } from '../store/search';
	import { onDestroy } from 'svelte';

	let x: number;
	let y: number;
	let dark = false;

	const skills = [
		{ component: BrandHtml5, name: 'HTML', category: 'frontend', framework: false },
		{ component: BrandCss3, name: 'CSS', category: 'frontend', framework: false },
		{
			component: BrandTailwind,
			name: 'Tailwind',
			category: 'frontend',
			framework: true,
			keywords: 'css'
		},
		{
			component: BrandBootstrap,
			name: 'Bootstrap',
			category: 'frontend',
			framework: true,
			keywords: 'css'
		},
		{ component: Wind, name: 'Windi', category: 'frontend', framework: true, keywords: 'css' },
		{
			component: BrandJavascript,
			name: 'JavaScript',
			category: 'frontend backend',
			framework: false,
			keywords: 'javascript js'
		},
		{
			component: BrandTypescript,
			name: 'TypeScript',
			category: 'frontend backend',
			framework: false,
			keywords: 'typescript ts'
		},
		{
			component: BrandSvelte,
			name: 'Svelte',
			category: 'frontend',
			framework: true,
			keywords: 'javascript typescript ts js'
		},
		{
			component: BrandVue,
			name: 'Vue',
			category: 'frontend',
			framework: true,
			keywords: 'javascript typescript ts js'
		},
		{
			component: BrandSolidjs,
			name: 'Solid',
			category: 'frontend',
			framework: true,
			keywords: 'javascript typescript ts js'
		},
		{
			component: Hexagon,
			name: 'NodeJS',
			category: 'backend',
			framework: true,
			keywords: 'javascript typescript ts js'
		},
		{
			component: BrandCpp,
			name: 'C++',
			category: 'multi platform',
			framework: false,
			keywords: 'cpp'
		},
		{
			component: BrandGolang,
			name: 'Go',
			category: 'backend',
			framework: false,
			keywords: 'golang go gopher'
		},
		{
			component: HexagonLetterE,
			name: 'Echo',
			category: 'backend',
			framework: false,
			keywords: 'golang go'
		},
		{
			component: BrandPython,
			name: 'Python',
			category: 'backend multiplatform',
			framework: false,
			keywords: 'py python'
		},
		{
			component: Pepper,
			name: 'Flask',
			category: 'backend',
			framework: true,
			keywords: 'py python'
		},
		{
			component: Bolt,
			name: 'FastAPI',
			category: 'backend',
			framework: true,
			keywords: 'py python'
		},
		{ component: Coffee, name: 'Java', category: 'backend multiplatform', framework: false },
		{ component: BrandDocker, name: 'Docker', category: 'cloud', framework: false },
		{
			component: BrandAmazon,
			name: 'AWS',
			category: 'cloud',
			framework: false,
			keywords: 'amazon web services'
		},
		{
			component: Sql,
			name: 'SQL',
			category: 'database',
			framework: false,
			keywords: 'mysql postgres server mariadb'
		},
		{ component: BrandGit, name: 'git', category: 'control version', framework: false }
	];

	const skillsToSearch = skills.map((skill) => ({
		...skill,
		searchTerms: `${skill.name} ${skill.category} ${skill.framework ? 'framework' : ''} ${
			skill.keywords
		}`
	}));

	const searchSkills = createSearchStore(skillsToSearch);

	const unsubscribe = searchSkills.subscribe((model) => searchHandler(model));

	onDestroy(() => unsubscribe());
	const toggleDarkMode = () => {
		window.document.body.classList.toggle('dark-mode');
		dark = !dark;
	};
</script>

<svelte:head>
	<title>I'm Henrry Bourgeot</title>
</svelte:head>
<svelte:window bind:innerWidth={x} bind:innerHeight={y} />
<svelte:body />
<div>
	<Header {dark} func={toggleDarkMode} />
	<main
		class={`${
			x < 1024 ? 'flex-col mb-10 h-full mx-5' : ''
		} flex justify-center max-w-screen-xl mx-auto items-center`}
		style={`--height: ${x < 1024 ? y : y - 120}px`}
	>
		<section class="{x < 1024 ? 'w-full' : 'w-1/2'} flex flex-col gap-3 p-6 justify-center">
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
		{#if x > 1024}
			<img src={gopherXl} class="w-1/2" alt="Gopher" />
		{:else}
			<img src={gopherLg} class="w-4/6" alt="Gopher" />
		{/if}
	</main>
	<section
		id="about"
		class="p-7 mx-auto flex justify-center items-center transition-bg duration-500 {!dark
			? 'bg-[#A5D7E8]'
			: 'bg-[#19376D]'} {x < 1100 ? 'h-full w-full px-0' : 'h-screen'}"
	>
		<div
			class="flex items-center md:container space-between w-full {x < 1024
				? 'flex-col-reverse items-center'
				: ''}"
		>
			<article class="{x < 1024 ? 'self-center' : ''} w-full">
				<img
					src={about}
					alt="Pic with IA"
					class="shadow-xl mb-7 rounded-md {x < 1024 ? 'w-1/2' : 'w-3/2'} mx-auto"
				/>
				<p class="text-lg text-center font-bold">Image generated with IA</p>
			</article>
			<article class="p-20 {x < 1100 ? 'w-full p-5' : 'w-13/12'}">
				<h2 class="text-5xl font-bold mb-10">About me</h2>
				<p class="text-xl leading-relaxed mb-5 w-11/12">
					I'm from Venezuela and I have 20 years old, actually I study the third year of five of the
					Systems Engineer major from the Polytechnic University Institute <em>Santiago Mariño</em>.
					Also, I love teach others about IT topics. My hobbie are the videogames and enjoy the life
					with my friends and family.
				</p>
				<p class="text-xl leading-relaxed w-11/12">
					I've 1 year working as a FullStack Dev. in my actual work, I use technologies as Svelte,
					Python, TypeScript and others. If you hire me, you'll get clean code and the best
					practices for make a clean and readable code. However, something that I like of
					programming, is resolve problems that are really annoying.
				</p>
			</article>
		</div>
	</section>
	<section id="skills" class="skills">
		<div class="overlay caskaydia p-2 md:p-5 flex flex-col">
			<h2 class="text-5xl font-bold text-center mb-10">Skills</h2>
			<input
				type="search"
				name="search-skill"
				id="search-skill"
				placeholder="Search skills..."
				bind:value={$searchSkills.search}
				class="input[type='search'] outline-0 rounded-md text-dark-900 mx-auto mb-5"
			/>
			<ul class="icons grids">
				{#each $searchSkills.filtered as skill}
					<li class="flex flex-col justify-center items-center">
						<Icon
							src={skill.component}
							style="stroke: #576CBC"
							class="h-30 w-30"
							theme="rounded"
						/>{skill.name}
					</li>
				{/each}
			</ul>
		</div>
	</section>
	<section
		id="projects"
		class="py-5 h-screen text-[#576CBC] transition-bg duration-500 {!dark
			? 'bg-[#eee] '
			: 'bg-[#222]'}"
	>
		<h2 class="text-5xl font-bold text-center p-10">Projects</h2>
		<article class="flex justify-between items-center projects crud">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://github.com/hbourgeot/crud-go">Golang CLI CRUD</a>
				</h3>
				<p class="text-xl">Golang CLI CRUD maked from 0</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandGolang} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />Golang
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon
						src={Database}
						style="stroke: #576CBC"
						class="h-30 w-30"
						theme="rounded"
					/>PostgreSQL
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects todotech">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://github.com/hbourgeot/todotech">Todotech Store</a>
				</h3>
				<p class="text-xl">Ecommerce with SSR and CRUD operations, has a admin dashboard.</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandGolang} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />Golang
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon
						src={Database}
						style="stroke: #576CBC"
						class="h-30 w-30"
						theme="rounded"
					/>PostgreSQL
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandHtml5} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />HTML
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandCss3} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />CSS
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon
						src={BrandJavascript}
						style="stroke: #576CBC"
						class="h-30 w-30"
						theme="rounded"
					/>JavaScript
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects karma">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://t.me/karmagobot">Go Karma Bot</a>
				</h3>
				<p class="text-xl">Telegram Bot for add or substract karma, only works on groups.</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandGolang} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />Golang
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Database} style="stroke: #576CBC" class="h-30 w-30" theme="rounded" />MySQL
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects weather text-light-300">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://henrryweather.netlify.app">Henrry Weather</a>
				</h3>
				<p class="text-xl">Weather app built in Svelte consuming an Weather API from RapidAPI.</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandSvelte} class="stroke-light-200 h-30 w-30" theme="rounded" />Svelte
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects solidjs text-light-200">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://solid-todoapp.vercel.app/">Solid ToDo App</a>
				</h3>
				<p class="text-xl">
					ToDo app maded with solidjs, the styles are the same like other todo app.
				</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandSolidjs} class="stroke-light-200 h-30 w-30" theme="rounded" />SolidJS
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects fastapi text-dark-900">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://github.com/hbourgeot/soluciones-hsl/">Soluciones HSL</a>
				</h3>
				<p class="text-xl">
					API Project builded with Python, MySQL and Fast API, simulates project management.
				</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandPython} class="stroke-dark-900e h-30 w-30" theme="rounded" />Python
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Bolt} class="stroke-dark-900e h-30 w-30" theme="rounded" />FastAPI
				</li>
				<li class="flex flex-col justify-center items-center">
					<Icon src={Database} class="stroke-dark-900e h-30 w-30" theme="rounded" />MySQL
				</li>
			</ul>
		</article>
		<article class="flex justify-between items-center projects solidjs text-light-200">
			<div class="content">
				<h3 class="text-3xl font-bold underline">
					<a href="https://legendary-yeot-bd3af5.netlify.app/">Vue ToDo App</a>
				</h3>
				<p class="text-xl">Vue App using the same style like solidjs todo.</p>
			</div>
			<ul class="icons flex">
				<li class="flex flex-col justify-center items-center">
					<Icon src={BrandVue} class="stroke-dark-900e h-30 w-30" theme="rounded" />VueJS
				</li>
			</ul>
		</article>
	</section>
</div>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600&display=swap');

	@font-face {
		font-family: 'CaskaydiaCove';
		src: url('$lib/fonts/Caskaydia Cove Nerd Font Complete Mono Regular.otf');
		font-weight: 700;
	}

	.caskaydia {
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

	.shadow-xl {
		box-shadow: -8px 10px 23px 6px rgba(0, 0, 0, 0.75);
		-webkit-box-shadow: -8px 10px 23px 6px rgba(0, 0, 0, 0.75);
		-moz-box-shadow: -8px 10px 23px 6px rgba(0, 0, 0, 0.75);
	}
	.overlay {
		background-color: #22222299;
		height: 100%;
		width: 100%;
	}
	.skills {
		background-image: url('$lib/assets/skills.png');
		background-position: center center;
		background-attachment: fixed;
		color: #eeeeee;
		height: max-content;
	}

	.grids {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
		row-gap: 10px;
	}

	.projects {
		padding: 40px;
		background-size: cover;
		background-position: center 600px;
		transition: height 300ms;
		height: 25%;
		@media (min-width: 1024px) {
			&:hover {
				height: 45%;
			}
		}
	}

	.crud {
		background-image: url('$lib/assets/crud.jpg');
		background-position: bottom center;
	}

	.todotech {
		background-image: url('$lib/assets/todotech.jpg');
	}

	.karma {
		background-image: url('$lib/assets/karmagobot.jpg');
	}

	.weather {
		background-image: url('$lib/assets/weather.png');
	}

	.solidjs {
		background-image: url('$lib/assets/solidtodo.png');
		background-position: center top;
	}

	.fastapi {
		background-image: url('$lib/assets/fastapi.png');
	}
</style>
