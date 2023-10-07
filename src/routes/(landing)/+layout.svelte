<script lang="ts">
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<AppShell>
	<svelte:fragment slot="header">
		<AppBar background='variant-surface-500/50 backdrop-blur' shadow='shadow-xl'>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">
                    Miss Litt Kittt
                </strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<div class="hover:scale-105 transition-transform">
                    <a href="/sign-up" class="btn variant-filled-secondary cursor-pointer">
                        Create<span class='hidden md:inline'>&nbsp;an Account</span>
                    </a>
                </div>
			</svelte:fragment>
		</AppBar>
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
