<script lang="ts">
	import 'iconify-icon';
	import '../app.css';
	import Navbar from '../components/nav/Navbar.svelte';
</script>

<body class="w-full h-screen overflow-hidden">
	<div class="max-w-5xl mx-auto">
		<Navbar />

		<main class="flex-1">
			<slot />
		</main>
	</div>
</body>
