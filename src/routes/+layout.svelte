<script lang="ts">
	import 'iconify-icon';
	import '../app.css';
	import Navbar from '../components/nav/Navbar.svelte';
</script>

<body class="flex flex-col items-center justify-center w-full max-w-6xl gap-2 mx-auto my-0">
	<Navbar />

	<main class="flex-1 size-full">
		<slot />
	</main>
</body>
