<script>
	// Props
	export let to = "";

	// Import components
	import { Link } from "svelte-navigator";
</script>

<Link class="link" {to}>
	<div class="list-item">
		<slot />
	</div>
</Link>

<style>
	.list-item {
		font-size: 0.8rem;
		width: 100%;
		padding: 10px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background: linear-gradient(
			to bottom,
			var(--fade),
			transparent 30%,
			transparent 70%,
			var(--fade)
		);
	}

	:global(.list-item .main-content) {
		width: 100%;
		margin: 0 10px;
	}

	:global(.list-item img) {
		width: 1.2rem;
		height: 1.2rem;
	}

	:global(*:focus) {
		outline: 0;
		background: linear-gradient(to bottom right, var(--body), var(--glow));
	}
</style>
