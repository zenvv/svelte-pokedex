<script lang="ts">
	import type { PageData } from './$types';

	export let data: PageData;
</script>

<div class="mt-20">
	<h1>Hello</h1>
	<p>{data.about}</p>
</div>
