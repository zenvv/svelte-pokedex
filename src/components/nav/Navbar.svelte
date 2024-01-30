<script lang="ts">
	import NavLink from './NavLink.svelte';

	let wsName: string = 'SVELTE POKEDEX';
</script>

<nav
	class="flex items-center justify-between w-full h-auto max-w-6xl gap-4 px-4 overflow-hidden text-gray-100 bg-red-500 nav-inset"
>
	<span class="px-4 py-3 select-none max-lg:w-full max-md:bg-gray-800">
		<h4 class="flex items-center justify-center gap-2 text-lg font-extrabold">
			<iconify-icon icon="ic:round-catching-pokemon" class="text-2xl align-middle"></iconify-icon>
			{wsName}
		</h4>
	</span>
	<span class="flex self-end gap-2">
		<NavLink href="/" name="Home" />
		<NavLink href="/my-monsters" name="My monsters" />
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
		bottom: -9px;
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
