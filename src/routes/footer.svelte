<script lang="ts">
	import * as config from '$lib/config'
</script>

<footer>
	<p>
		{config.title}&nbsp; &copy {new Date().getFullYear()}
	</p>
	<p>-| all rights reserved |-</p>
</footer>

<style>
	p {
		color: var(--text-3);
	}
	footer {
		display: flex;
		justify-content: center;
		gap: 3rem;
		padding: 1rem;
		border-top: 3px solid var(--text-3);
	}

	@media only screen and (max-width: 767px) {
		footer {
			gap: 1rem;
			padding: 8px;
		}
	}
</style>
