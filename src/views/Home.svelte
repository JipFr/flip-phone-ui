<script>
	// Import components
	import List from "../components/List.svelte";
	import ListItem from "../components/ListItem.svelte";

	// Import icons
	import ArrowRight from "../icons/ArrowRight.svelte";
</script>

<List before="Chat">
	<ListItem to="/guilds">
		<div>DMs</div>
		<span>
			<ArrowRight />
		</span>
	</ListItem>
	<ListItem to="/guilds">
		<div>Guilds</div>
		<span>
			<ArrowRight />
		</span>
	</ListItem>
</List>

<List before="Appearance">
	<ListItem to="/about">
		<div>Color theme</div>
		<span>
			<ArrowRight />
		</span>
	</ListItem>
	<ListItem to="/about">
		<div>Compact style</div>
		<span>
			<ArrowRight />
		</span>
	</ListItem>
</List>
