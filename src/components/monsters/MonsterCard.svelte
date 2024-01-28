<script lang="ts">
	import type { IndexMonster } from '../../routes/+page';
	export let monster: IndexMonster;

	export let updateSearchParams: (key: string, value: string) => void;

	export let isInteractive: boolean = true;
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore missing-declaration -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div
	class={`${isInteractive ? 'hover:bg-gray-100 hover:text-gray-900 hover:shadow-lg hover:cursor-pointer group text-gray-800 border-gray-300/50 bg-gray-100  p-4 my-2' : 'bg-gray-800 text-gray-100 p-6 border-gray-600 m-0'} relative flex flex-col size-full justify-center  gap-2 items-start transition-all border`}
>
	{#if isInteractive == true}
		<span class="absolute top-0 right-0 z-10 flex p-3">
			<div data-sveltekit-noscroll on:click={() => updateSearchParams('monsterId', monster.id)}>
				<iconify-icon
					icon="icon-park-solid:one-key"
					class="text-xl text-gray-300 align-middle transition-all hover:text-blue-500"
				></iconify-icon>
			</div>
			<div data-sveltekit-noscroll on:click={() => updateSearchParams('monsterId2', monster.id)}>
				<iconify-icon
					icon="icon-park-solid:two-key"
					class="text-xl text-gray-300 align-middle transition-all hover:text-red-500"
				></iconify-icon>
			</div>
		</span>
	{/if}

	<p class="text-xs font-semibold opacity-80">
		#{monster.id < '100' ? `0${monster.id}` : monster.id}
	</p>
	<img
		src={monster.image}
		alt={monster.name}
		class={`${isInteractive ? 'transition-all group-hover:scale-110 group-hover:drop-shadow-[0px_10px_10px_rgba(0,0,0,0.5)]' : ''} size-full aspect-square`}
	/>

	<h2 class="text-base font-bold capitalize">
		{monster.name}
	</h2>
</div>
