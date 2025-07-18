<script lang="ts">
	import { Button } from "bits-ui";
	import type { Snippet } from "svelte";
	import { tv, type VariantProps } from "tailwind-variants";

	const buttonVariants = tv({
		base: "inline-flex h-12 items-center justify-center px-[21px] text-[15px] font-semibold active:scale-[0.98] active:transition-all",
		variants: {
			variant: {
				default: "bg-light-purple border-2",
				link: "underline-offset-4 hover:underline"
			}
		},
		defaultVariants: {
			variant: "default"
		}
	});

	type Props = {
		variant?: VariantProps<typeof buttonVariants>["variant"];
		href?: string;
		children: Snippet;
	};

	let { variant, href, children }: Props = $props();
</script>

<Button.Root class={buttonVariants({ variant })} {href}>
	{@render children()}
</Button.Root>
