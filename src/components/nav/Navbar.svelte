<script lang="ts">
	import NavLink from './NavLink.svelte';

	let wsName: string = 'S-POKEDEX';
</script>

<nav
	class="flex items-center justify-between p-0 px-4 m-0 overflow-hidden text-gray-100 bg-red-500 nav-inset max-md:flex-col max-md:p-0"
>
	<a
		href="/"
		class="hover:bg-gray-100/10 px-4 py-1.5 active:scale-95 max-md:active:scale-100 transition-all max-lg:w-full max-md:bg-gray-800 max-md:hover:bg-gray-800"
	>
		<h4 class="flex items-center gap-2 text-lg font-extrabold max-md:justify-center">
			<iconify-icon icon="gg:pokemon" class="text-xl"></iconify-icon>
			{wsName}
		</h4>
	</a>

	<span class="flex items-center justify-center gap-2 max-md:w-full">
		<NavLink href="/" name="Pokemons" />
		<NavLink href="/generations" name="Generations" />
	</span>
</nav>

<style lang="postcss">
	.nav-inset {
		position: relative;
	}

	.nav-inset::after {
		content: '';
		width: 18px;
		height: 18px;
		position: absolute;
		top: 45px;
		right: -10px;
		transform: rotate(45deg);
		@apply bg-gray-200;
	}
	.nav-inset::before {
		content: '';
		width: 18px;
		height: 18px;
		position: absolute;
		top: 45px;
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
