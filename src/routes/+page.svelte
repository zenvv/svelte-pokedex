<script lang="ts">
	import type { PageData } from './$types';
	export let data: PageData;
</script>

<header class="flex flex-col items-start gap-2 p-8 mb-8 text-gray-900 bg-gray-300">
	<h1 class="p-0 m-0">
		<iconify-icon icon="ic:round-catching-pokemon" class="text-4xl align-middle"></iconify-icon>
		Welcome to your personal Pokedex
	</h1>
	<p class="p-0 m-0">Search your pokemons bellow</p>
</header>

<div class="grid grid-cols-6 gap-3 gap-y-5 max-lg:grid-cols-3 max-lg:gap-4">
	{#each data.monsters as monster (monster.url)}
		<div
			class="flex flex-col items-start justify-center w-full h-full gap-2 p-4 my-2 text-gray-800 transition-all border border-gray-300 bg-gray-300/25 hover:bg-gray-100 hover:text-gray-900 hover:scale-110 hover:shadow-lg hover:cursor-pointer"
		>
			<p class="text-xs font-semibold opacity-80">
				#{monster.id < 100 ? `0${monster.id}` : monster.id}
			</p>
			<img src={monster.image} alt={monster.name} class="size-full aspect-square" />

			<h2 class="text-base font-bold capitalize">
				{monster.name}
			</h2>
		</div>
	{/each}
</div>
