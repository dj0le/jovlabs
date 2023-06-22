<script lang="ts">
	import { title, description } from '$lib/config'
	import { characters } from '$lib/data/characters.json'

	async function getCharacters() {
		return characters
	}

	let currentChar = 0

	function selectCharacter(newCharacter) {
		currentChar = newCharacter - 1
		return currentChar
	}
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />
	{@html `<script type="application/ld+json">
{
		"@context": "http://schema.org",
		"@type": "WebSite",
		  "name": "${title}",
          "description": "${description}",
		  "url": "https://jovlabs.com/",
		}
	</script>`}
</svelte:head>

<main>
	<div class="field-container">
		<h1>characters</h1>
		<div class="current-bot">
			<img
				class="current-image"
				src={characters[currentChar].imagefull}
				height="300"
				width="300"
				alt="Character"
			/>
			<div class="seperator">
				<h2 class="current-name">{characters[currentChar].name}</h2>
				<p>Personality: {characters[currentChar].personality}</p>
				<p>Description: {characters[currentChar].description}</p>
			</div>
			<button class="chat-button"><span>CHAT</span> </button>
		</div>

		<div class="bot-select">
			<h2 class="seperator-horizontal">Select your chat partner</h2>
			<div class="bot-grid">
				{#each characters as character}
					<button class="bot-pill" on:click={() => selectCharacter(character.id)}>
						<img class="bot-pic" src={character.image} height="64" width="64" alt="character" />
						<h3 class="bot-name">{character.name}</h3>
					</button>
				{/each}
			</div>
		</div>
	</div>
</main>

<style>
	.bot-grid :hover {
		outline: 2px solid var(--text-3);
		outline-offset: 8px;
		transition: 0.2s all ease;
	}
	.bot-pill :hover {
		outline: none;
	}
	.bot-grid :active {
		border: 2px solid var(--text-3);
	}
	.bot-pill :active {
		border: none;
	}
	.field-container {
		max-width: 80%;
		margin: 0 auto;
		margin-bottom: 30rem;
	}
	.current-bot {
		position: relative;
		display: grid;
		grid-template-columns: 300px auto;
		align-items: top;
		gap: 2rem;
		background-image: var(--bg-grad);
		border: 3px solid var(--border);
		border-radius: 16px;
		padding: 1.75rem 1.75rem;
		margin-bottom: 8rem;
	}
	.current-image {
		border-radius: 12px;
	}
	.current-name {
		font-size: 4rem;
	}
	.chat-button {
		position: absolute;
		bottom: -2.25rem;
		right: 0;
		border: 3px solid var(--border);
		background-color: var(--surface-4);
		border-radius: 8px;
		padding: 0.75rem 0;
		margin: 0 8rem;
		width: 35%;
		cursor: pointer;
		font-size: 1.5rem;
		font-weight: bold;
		letter-spacing: 2px;
		text-transform: uppercase;
		z-index: 9;
	}
	.seperator {
		border-left: 4px solid var(--surface-3);
		padding-left: 2rem;
	}
	.seperator-horizontal {
		border-bottom: 4px solid var(--surface-3);
	}
	span {
		padding: 8px 24px;
		border-radius: 4px;
		background-color: var(--surface-4);
		color: var(--text-2);
	}
	.chat-button :hover {
		outline: 2px solid var(--border);
		outline-offset: -4px;
		transition: 0.2s all ease;
	}
	h1 {
		color: var(--text-3);
	}
	h2 {
		color: var(--text-3);
	}
	h3 {
		color: var(--text-2);
		font-size: 1.25rem;
		padding: 6px 12px;
		border-radius: 4px;
		background-color: var(--surface-4);
		border-bottom: 2px solid var(--surface-2);
		border-left: 2px solid var(--surface-2);
	}
	p {
		margin-top: 16px;
		margin-bottom: 6px;
		font-weight: bold;
		letter-spacing: 1px;
		color: var(--text-2);
		padding: 6px 12px;
		border-radius: 4px;
		background-color: var(--surface-4);
		border-bottom: 2px solid var(--surface-2);
		border-left: 2px solid var(--surface-2);
	}
	.bot-grid {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 2rem;
		border-radius: 8px;
		margin-block: 2rem;
	}
	.bot-pill {
		display: grid;
		gap: 8px;
		grid-template-columns: 1fr 2fr;
		align-items: center;
		background-image: var(--bg-grad);
		border-radius: 8px;
		border: 2px solid var(--border);
	}

	@media only screen and (max-width: 950px) {
		.field-container {
			max-width: 100%;
		}
		.bot-grid {
			grid-template-columns: 1fr 1fr;
			gap: 1rem;
		}
	}

	@media only screen and (max-width: 735px) {
		.field-container {
			margin-bottom: 6rem;
		}
		.current-bot {
			grid-template-columns: 1fr;
			gap: 1rem;
			padding: 0.5rem 0.5rem;
			margin-bottom: 6rem;
		}
		.current-name {
			font-size: 3rem;
		}
		.chat-button {
			position: absolute;
			bottom: -2.5rem;
			padding: 0.75rem 0;
			margin: 0 1rem;
			width: 55%;
		}
		.seperator {
			border-left: none;
			padding-left: 0;
		}
		h1 {
			font-size: 4rem;
		}
		h2 {
			font-size: 2.5rem;
		}
		h3 {
			font-size: 1.25rem;
			padding: 3px 6px;
		}
		.bot-grid {
			grid-template-columns: 1fr;
			gap: 1rem;
		}
	}
</style>
