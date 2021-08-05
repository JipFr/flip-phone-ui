<script>
	import { Router, Route } from "svelte-navigator";

	// Import components
	import List from "./components/List.svelte";
	import Home from "./views/Home.svelte";
	import Guilds from "./views/Guilds.svelte";

	// Stuff
	let focusedItem = 0;
	window.addEventListener("load", () => {
		doFocusState();
	});

	function getNodes() {
		return [...document.querySelectorAll("a, [tabindex]")];
	}

	function doFocusState() {
		const nodes = getNodes();
		const node = nodes[focusedItem];
		if (!node) return false;
		node.focus();
		node.scrollIntoView({ behavior: "smooth", block: "center" });
	}

	document.addEventListener("keydown", (evt) => {
		if (evt.key.startsWith("Arrow")) evt.preventDefault();

		const nodes = getNodes();

		switch (evt.key) {
			case "ArrowDown": {
				focusedItem = (focusedItem + 1) % nodes.length;
				break;
			}
			case "ArrowUp": {
				focusedItem--;
				if (focusedItem < 0) focusedItem = nodes.length + focusedItem;
				break;
			}
			case "ArrowRight":
			case "Enter": {
				if (nodes[focusedItem]) nodes[focusedItem].click();
			}
		}
		doFocusState();
	});
</script>

<Router>
	<main>
		<Route path="/">
			<Home />
		</Route>

		<Route path="/about">
			<List before="About">yo</List>
		</Route>

		<Route path="/guilds">
			<Guilds />
		</Route>
	</main>
</Router>
