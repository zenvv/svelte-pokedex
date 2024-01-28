<script>
	import { generations } from '$lib/generations';
</script>

<div class="flex flex-col items-end justify-start w-2/3 h-full gap-2">
	<button class="region-btn active">All</button>
	{#each generations as generation (generation.id)}
		<button class="region-btn">{generation.main_region}</button>
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
		bottom: -6px;
		right: -6px;
		z-index: 0;
		transform: rotate(45deg);
		@apply bg-red-500;
	}

	.active {
		@apply bg-gray-800 text-gray-200 hover:bg-gray-800/80;
	}
</style>
