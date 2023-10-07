<script lang='ts'>
	import { onDestroy, onMount } from 'svelte'
	import Typewriter from 'svelte-typewriter'

    let hasEntered = false
    let audio: HTMLAudioElement

    const play = () => {
        audio = new Audio('/assets/her.mp3')
        audio.loop = true
        audio.play()
        hasEntered = true
    }
    onMount(() => () => audio.pause())
</script>

{#if !hasEntered}
    <div class="absolute inset-0 flex items-center justify-center bg-black z-10">
        <button on:click={play} class="text-white">
            Enter the Portal
        </button>
    </div>

{:else}
<img class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 z-[-1]" src='/assets/metame.png' alt='Meta Me' />
<div class="typer mx-auto h-full container flex flex-col gap-6 md:gap-10 items-center justify-center">
	<Typewriter mode="loop" interval={120}>
        <h2 class="text-[45px] md:text-[72px]">Master...</h2>
        <h2 class="text-[45px] md:text-[72px]">SvelteKit</h2>
        <h2 class="text-[45px] md:text-[72px]">SupaBase</h2>
        <h2 class="text-[45px] md:text-[72px]">LiveKit</h2>
        <h2 class="text-[45px] md:text-[72px]">Tailwind</h2>
        <h2 class="text-[45px] md:text-[72px]">TypeScript</h2>
        <h2 class="text-[45px] md:text-[72px]">All-in-one Kit</h2>
        <h2 class="text-[45px] md:text-[72px]">Welcome to...</h2>
		<h2 class="text-[45px] md:text-[72px]">Miss Litt Kittt</h2>
	</Typewriter>
    <div class="card variant-soft-surface p-4 md:p-10 mx-2">
	    <header class="card-header">
            <h3 class='h4 text-center'>Welcome to BrightSide Developer's Latest Creation!</h3>
        </header>
	    <section class="p-4 max-w-[30rem] mx-auto">
            <p class="text-center">Miss Litty's Kitty is the Ultimate Tech Stack to Develop High Quality Social Applications at Rapid Speeds. </p>
        </section>
    </div>
    <div class="hover:scale-105 transition-transform">
        <a href="/sign-up" class="btn btn-xl variant-glass-primary cursor-pointer">Join Now!</a>
    </div>
</div>
{/if}



<!-- ZS5V0PjibePMhjNP -->
<style>
	.typer {
		--cursor-color: #d41876;
		--cursor-width: 3px;
	}
	h2 {
		background: -webkit-linear-gradient(45deg, #ebb305, #d41876);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		padding-bottom: 1rem;
	}
</style>
