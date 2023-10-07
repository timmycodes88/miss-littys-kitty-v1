<script lang="ts">
	import '../../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<AppShell slotSidebarLeft="bg-surface-500/5 w-0 md:w-56 md:p-4">
	<svelte:fragment slot="header">
		<AppBar background='bg-surface-500/50 backdrop-blur' shadow='shadow-xl'>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Miss Litty's Kitty</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<strong>Hello SvelteKit</strong>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>

	<svelte:fragment slot="sidebarLeft">
		<nav class="list-nav">
			<ul>
				<li><a href="/?">Home</a></li>
				<li><a href="/?about">About</a></li>
			</ul>
		</nav>
	</svelte:fragment>

	<div class="absolute z-[-1] top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2">
		<section class="glow" />
	</div>
	<slot />
</AppShell>

<style lang="postcss">
	.glow {
		@apply w-64 h-64 md:w-80 md:h-80;
		@apply rounded-full blur-[50px] transition-all;
		animation: pulse 5s cubic-bezier(0, 0, 0, 0.5) infinite,
			glow 5s linear infinite;
	}
	@keyframes glow {
		0% {
			@apply bg-primary-400/50;
		}
		33% {
			@apply bg-secondary-400/50;
		}
		66% {
			@apply bg-tertiary-400/50;
		}
		100% {
			@apply bg-primary-400/50;
		}
	}
	@keyframes pulse {
		50% {
			transform: scale(1.5);
		}
	}
</style>
