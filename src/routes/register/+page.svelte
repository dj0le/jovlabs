<script lang="ts">
	import type { ActionData } from './$types'

	export let form: ActionData
</script>

<h1>Register</h1>

<form action="?/register" method="Post">
	<div>
		<label for="username">Username</label>
		<input id="username" name="username" type="text" required />
	</div>
	<div>
		<label for="username">Password</label>
		<input id="password" name="password" type="password" required />
	</div>

	{#if form?.user}
		<p class="error">User already exists</p>
	{/if}

	<button type="submit">Register</button>
</form>
