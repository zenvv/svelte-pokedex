<script lang="ts">
	import { generations } from '$lib/generations';
	import { page } from '$app/stores';

	export let updateSearchParams: (key: string, value: string) => void;

	$: selectedGenerationId = $page.url.searchParams.get('generation_id') || '';
</script>

<div class="flex items-start justify-start w-2/3 h-full gap-2">
	<button
		class="region-btn"
		class:active={selectedGenerationId == 'all'}
		on:click={() => updateSearchParams('generation_id', 'all')}>All</button
	>
	{#each generations as generation (generation.id)}
		<button
			on:click={() => updateSearchParams('generation_id', generation.id.toString())}
			class:active={selectedGenerationId == generation.id.toString()}
			class="region-btn"
		>
			{generation.main_region}
		</button>
	{/each}
</div>

<style lang="postcss">
	.region-btn {
		@apply flex items-center text-center justify-center outline-none cursor-pointer relative hover:bg-gray-800/15 w-full h-10 text-gray-800 font-bold text-sm border-none transition-colors;
	}

	.region-btn::after {
		content: '';
		width: 12px;
		height: 12px;
		position: absolute;
		top: -6px;
		right: -6px;
		z-index: 0;
		transform: rotate(45deg);
		@apply bg-gray-200;
	}

	.active {
		@apply bg-gray-800 text-gray-200 hover:bg-gray-800/80;
	}
</style>
