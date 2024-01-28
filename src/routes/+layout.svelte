<script lang="ts">
	import 'iconify-icon';
	import '../app.css';
	import Navbar from '../components/nav/Navbar.svelte';
</script>

<body class="flex justify-betwee max-w-7xl w-full mx-auto my-[20px] gap-2">
	<div class="sticky top-[20px]">
		<Navbar />
	</div>
	<main class="p-8 border border-gray-300 size-full">
		<slot />
	</main>
</body>
