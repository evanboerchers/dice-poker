<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class="w-screen h-screen bg-slate-800">
	{@render children()}
</div>
