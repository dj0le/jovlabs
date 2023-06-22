<script lang="ts">
	import { title, description } from '$lib/config'
	function handleClick() {
		alert('clicked')
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
	<h1>jovlabs ai</h1>

	<button on:click={handleClick}> Click me </button>
</main>
