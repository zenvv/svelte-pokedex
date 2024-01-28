<script>
	import { generations } from '../../lib/generations';
</script>

<h1>Generations</h1>

<div class="grid w-full h-full grid-cols-3 gap-4 mt-8">
	{#each generations as generation (generation.id)}
		<div
			class="flex flex-col items-start justify-start w-full text-xs text-gray-700 border border-gray-400 hover:border-gray-600"
		>
			<span class="flex items-center justify-between w-full p-4">
				<h2 class="text-lg font-bold text-gray-800">{generation.name}</h2>
				<p>#{generation.id}</p>
			</span>
			<span class="w-full p-2 px-4 space-y-0 border-t border-gray-300 bg-gray-300/35">
				<p>Region: {generation.main_region}</p>
				<p>Games: {generation.games.join(', ')}</p>
			</span>
		</div>
	{/each}
</div>
