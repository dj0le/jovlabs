<script lang="ts">
	import type { ActionData } from './$types'

	export let form: ActionData
</script>

<main>
	<div class="field-container">
		<div class="login-card">
			<h1>Hello</h1>
			<form action="?/login" method="POST">
				<div>
					<label for="username">Username</label>
					<input class="input-field" id="username" name="username" type="text" required />
				</div>
				<div>
					<label for="username">Password</label>
					<input class="input-field" id="password" name="password" type="password" required />
				</div>

				{#if form?.invalid}
					<p class="error">Username and password is required.</p>
				{/if}

				{#if form?.credentials}
					<p class="error">You have entered the wrong credentials.</p>
				{/if}

				<button class="login-button" type="submit">Login</button>
			</form>
		</div>
	</div>
</main>

<style>
	.field-container {
		max-width: 60%;
		margin: 0 auto;
	}
	label {
		color: var(--text-2);
	}
	p {
		margin-top: 16px;
		margin-bottom: 6px;
		font-weight: bold;
		letter-spacing: 1px;
		color: var(--text-2);
	}
	.login-card {
		background-image: var(--bg-grad);
		border: 3px solid var(--border);
		border-radius: 16px;
		margin-top: 5rem;
		padding: 2rem 3.5rem;
	}
	.login-button {
		border: 3px solid var(--border);
		background-color: var(--surface-1);
		width: 100%;
		border-radius: 8px;
		padding: 0.75rem 0;
		cursor: pointer;
		font-size: 1.5rem;
		font-weight: bold;
		letter-spacing: 2px;
		text-transform: uppercase;
		margin: 2rem 0;
	}

	.input-field {
		border: 3px solid var(--border);
		background-color: hsl(var(--gray-6-hsl) / 50%);
		color: var(--text-2);
		width: 100%;
		border-radius: 8px;
		padding: 8px 16px;
		margin: 8px 0;
		text-transform: uppercase;
	}

	@media only screen and (max-width: 950px) {
		.field-container {
			max-width: 80%;
		}
		h1 {
			padding: 1rem 0;
		}
		.login-card {
			margin-top: 1rem;
			padding: 2rem 4rem;
		}
		.login-button {
			font-size: 1rem;
			margin: 1rem 0;
		}
	}

	@media only screen and (max-width: 500px) {
		.field-container {
			max-width: 100%;
		}
		h1 {
			font-size: 5rem;
		}
		.login-card {
			margin-top: 16px;
			padding: 1rem 1rem;
		}
		.login-button {
			font-size: 1rem;
			margin: 0.5rem 0;
		}
	}
</style>
