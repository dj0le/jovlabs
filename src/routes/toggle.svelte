<script lang="ts">
	import { fly } from 'svelte/transition'
	import { Sun, Moon, Mail, Github } from 'lucide-svelte'
	import { theme, toggleTheme } from '$lib/theme'
</script>

<div class="drop-socials">
	<button on:click={toggleTheme} aria-label="Toggle theme">
		{#if $theme === 'dark'}
			<div in:fly={{ y: 10 }}>
				<Sun />
			</div>
		{:else}
			<div in:fly={{ y: -10 }}>
				<Moon />
			</div>
		{/if}
	</button>
	<a href="https://github.com/pyrater/LLM-AI-BOT"><Github /></a>
	<a href="mailto: wonderbot@space-shift.com"><Mail /></a>
</div>

<style>
	.drop-socials {
		display: flex;
		gap: 1rem;
		align-items: center;
	}
	.drop-socials > * {
		color: var(--brand);
	}
	button {
		transition: all 250ms ease-in-out;
		cursor: pointer;
	}
</style>
