<script>
	// Import components
	import List from "../components/List.svelte";
	import ListItem from "../components/ListItem.svelte";

	// Import icons
	import ArrowRight from "../icons/ArrowRight.svelte";

	// Tmp
	const names = [
		"movie-web",
		"Adolla",
		"Jip and T70",
		"why'd the last dude stop",
		"Thing",
		"DesignCourse",
		"MCContent",
		"Code()",
		"Bla bla bla bla bla bla bla bla bla bla",
	];
</script>

<List before="Your guilds">
	{#each names as name}
		<ListItem to="/guilds">
			<img
				src="https://cdn.discordapp.com/icons/679090685680418829/bdaccece3c1834363e3a5c70a099096c.webp?size=128"
				alt
			/>
			<div class="main-content">{name}</div>
			<span>
				<ArrowRight />
			</span>
		</ListItem>
	{/each}
</List>
