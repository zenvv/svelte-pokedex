<script lang="ts">
	import 'iconify-icon';
	import '../app.css';
	import Navbar from '../components/nav/Navbar.svelte';
</script>

<body class="flex flex-col w-full h-full max-w-6xl min-h-screen gap-6 mx-auto my-0">
	<Navbar />
	<main class="flex-1 px-3">
		<slot />
	</main>
</body>
