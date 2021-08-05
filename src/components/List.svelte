<script>
	export let before = "";
</script>

<div class="list-wrapper" data-before={before}>
	{#if before}
		<h1>{before}</h1>
	{/if}
	<div class="list">
		<slot />
	</div>
</div>

<style>
	.list {
		border-top: 1px solid var(--border);
		border-bottom: 1px solid var(--border);
	}
</style>
