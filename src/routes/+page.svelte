<script lang="ts">
	import MonsterCard from '../components/monsters/MonsterCard.svelte';
	import { goto } from '$app/navigation';
	import { page } from '$app/stores';
	import type { PageData } from './$types';
	import { generations } from '$lib/generations';
	import RegionNav from '../components/region/RegionNav.svelte';
	import MonsterSearch from '../components/monsters/MonsterSearch.svelte';

	export let data: PageData;

	let searchString: string = '';

	$: selectedMonsters = data.monsters.filter((monster) => {
		return monster.name.toLowerCase().includes(searchString.toLowerCase());
	});

	$: monsterId = $page.url.searchParams.get('monsterId');
	$: monster = data.monsters.find((monster) => monster.id === monsterId);

	$: monsterId2 = $page.url.searchParams.get('monsterId2');
	$: monster2 = data.monsters.find((monster) => monster.id === monsterId2);

	const updateSearchParams = (key: string, value: string) => {
		const searchParams = new URLSearchParams($page.url.searchParams);
		searchParams.set(key, value);
		goto(`?${searchParams.toString()}`);
	};
</script>

{#if monster || monster2}
	<div
		class="flex items-center w-full h-64 min-h-0 gap-10 p-8 my-8 mt-20 bg-gray-300 border rounded-md justify-evenly border-gray-400/40"
	>
		{#if monster}
			<span class="flex overflow-hidden border rounded-md shadow-md border-gray-400/20">
				<p
					class="p-2 px-4 m-0 font-semibold text-gray-100 bg-gradient-to-t from-gray-800 to-blue-500"
				>
					Monster 1
				</p>
				<MonsterCard {monster} {updateSearchParams} isInteractive={false} />
			</span>
		{/if}
		<p class="text-lg italic font-extrabold">VS</p>
		{#if monster2}
			<span class="flex overflow-hidden border rounded-md shadow-md border-gray-400/20">
				<MonsterCard monster={monster2} {updateSearchParams} isInteractive={false} />
				<p
					class="flex items-end p-2 px-4 m-0 font-semibold text-right text-gray-100 bg-gradient-to-b from-gray-800 to-red-500"
				>
					Monster 2
				</p>
			</span>
		{/if}
	</div>
{/if}

<span
	class="sticky z-50 flex items-end justify-between w-full pt-4 mb-8 bg-gray-200 border-b border-gray-300 top-16"
>
	<RegionNav {updateSearchParams} />

	<input
		type="text"
		class="sticky top-0 h-full px-4 py-3 text-sm font-bold text-gray-800 border rounded w-80 border-gray-400/50 bg-gray-300/50 placeholder:text-gray-500 placeholder:italic placeholder:font-normal"
		placeholder="Search a pokémon"
		bind:value={searchString}
	/>
</span>

<div class="grid w-full grid-cols-6 gap-3 mt-20 max-lg:grid-cols-3 max-lg:gap-2 gap-y-5">
	{#each selectedMonsters as monster (monster.url)}
		<MonsterCard {monster} {updateSearchParams} />
	{/each}
</div>
