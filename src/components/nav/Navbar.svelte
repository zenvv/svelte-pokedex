<script lang="ts">
	import RegionNav from '../region/RegionNav.svelte';
	import NavLink from './NavLink.svelte';

	let wsName: string = 'SVELTE POKEDEX';
</script>

<nav
	class="sticky top-[20px] flex flex-col items-start justify-start gap-4 text-gray-100 bg-red-500 h-[800px] ml-2 w-[300px] nav-inset py-8"
>
	<a
		href="/"
		class="w-full px-4 py-3 transition-all hover:bg-gray-100/10 active:scale-95 max-md:active:scale-100 max-lg:w-full max-md:bg-gray-800 max-md:hover:bg-gray-800"
	>
		<h4 class="flex items-center justify-center gap-2 text-lg font-extrabold">
			<iconify-icon icon="ic:round-catching-pokemon" class="text-2xl align-middle"></iconify-icon>
			{wsName}
		</h4>
	</a>
	<p class="px-8 py-0 text-lg font-semibold opacity-60">Regions</p>
	<RegionNav />
	<!-- <span class="flex items-center justify-center gap-2 max-md:w-full">
		<NavLink href="/" name="Pokémons" />
		<NavLink href="/generations" name="Generations" />
	</span> -->

	<span class="px-8 text-sm text-gray-800 justify-self-end">
		<p>
			made by
			<a
				href="https://www.github.com/zenvv"
				target="_blank"
				class="hover:cursor-pointer hover:font-semibold hover:underline">zendevv</a
			>
		</p>
	</span>
</nav>

<style lang="postcss">
	.nav-inset {
		/* position: relative; */
	}

	.nav-inset::after {
		content: '';
		width: 18px;
		height: 18px;
		position: absolute;
		top: -9px;
		right: -10px;
		transform: rotate(45deg);
		@apply bg-gray-200;
	}
	.nav-inset::before {
		content: '';
		width: 18px;
		height: 18px;
		position: absolute;
		bottom: -9px;
		left: -10px;
		transform: rotate(45deg);
		@apply bg-gray-200;
	}

	@media (max-width: 768px) {
		.nav-inset::after,
		.nav-inset::before {
			display: none;
		}
	}
</style>
