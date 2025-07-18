<script lang="ts">
	import "../app.css";
	import Nav from "$lib/components/Nav.svelte";
	import * as Sheet from "$lib/components/sheet";
	import Menu from "@lucide/svelte/icons/menu";
	import Button from "$lib/components/base/Button.svelte";

	let { children } = $props();

	// https://khromov.se/dockerizing-your-sveltekit-applications-a-practical-guide/
</script>

<div class="fixed inset-0 overflow-y-auto">
	<header
		class="bg-light-purple sticky top-0 flex h-[50px] w-full items-center justify-between border-b-2 px-4 opacity-85"
	>
		<a class="flex gap-2 leading-[1.8]" href="/">
			<img class="size-8 border-2" src="/windy.png" alt="WindySpoon's Fursona" />
			windyspoon
		</a>

		<Nav />

		<div class="flex">
			<Sheet.Root>
				<Sheet.Trigger class="sm:hidden">
					<Menu class="size-8" />
				</Sheet.Trigger>
				<Sheet.Content>
					<Sheet.Header>
						<nav class="flex flex-col">
							<Button variant="link">Home</Button>
							<Button variant="link">Games</Button>
							<Button variant="link">Music</Button>
							<Button variant="link">Blog</Button>
						</nav>
					</Sheet.Header>
				</Sheet.Content>
			</Sheet.Root>
		</div>
	</header>

	<main>
		{@render children()}
	</main>
</div>
