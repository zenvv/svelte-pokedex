<script lang="ts">
	import { page } from '$app/stores';
	export let href: string;
	export let name: string;
</script>

<a {href} class="link" class:active={$page.url.pathname === href}>
	{name}
</a>

<style lang="postcss">
	.link {
		@apply flex items-center text-left justify-start outline-none cursor-pointer relative hover:bg-gray-100/15 py-1.5 pt-6 w-40 px-3 text-gray-100 hover:text-gray-50 font-bold border-none transition-colors m-0 max-md:w-full;
	}

	.link::after {
		content: '';
		width: 18px;
		height: 18px;
		position: absolute;
		top: 45px;
		right: -10px;
		transform: rotate(45deg);
		@apply bg-red-500;
	}

	.link.active {
		@apply bg-gray-800 text-gray-300 hover:bg-gray-800/80 hover:border-transparent;
	}
</style>
