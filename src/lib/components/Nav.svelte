<script lang="ts">
	import { NavigationMenu } from "bits-ui";
	import ChevronDown from "@lucide/svelte/icons/chevron-down";

	const NAV_ITEM =
		"inline-flex h-12 items-center justify-center px-[21px] text-[15px] font-semibold underline-offset-4 hover:underline";
</script>

<NavigationMenu.Root class="relative hidden sm:block">
	<NavigationMenu.List class="flex">
		<NavigationMenu.Item>
			<NavigationMenu.Link class={NAV_ITEM} href="/">Home</NavigationMenu.Link>
		</NavigationMenu.Item>
		<NavigationMenu.Item>
			<NavigationMenu.Link class={NAV_ITEM} href="/games">Games</NavigationMenu.Link>
		</NavigationMenu.Item>
		<NavigationMenu.Item>
			<NavigationMenu.Link class={NAV_ITEM} href="/music">Music</NavigationMenu.Link>
		</NavigationMenu.Item>
		<NavigationMenu.Item>
			<NavigationMenu.Link class={NAV_ITEM} href="/blog">Blog</NavigationMenu.Link>
		</NavigationMenu.Item>
		<NavigationMenu.Item>
			<NavigationMenu.Trigger class={"group " + NAV_ITEM}>
				More
				<ChevronDown
					class="relative top-[1px] ml-1 size-3 transition-transform duration-200 group-data-[state=open]:rotate-180"
					aria-hidden="true"
				/>
			</NavigationMenu.Trigger>
			<NavigationMenu.Content class="bg-light-purple absolute top-10 right-0 border-2">
				<NavigationMenu.Link class={NAV_ITEM} href="/asdasdasd">Testing</NavigationMenu.Link>
			</NavigationMenu.Content>
		</NavigationMenu.Item>
	</NavigationMenu.List>
	<NavigationMenu.Viewport />
</NavigationMenu.Root>
