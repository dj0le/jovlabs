<div class="field-container">
	<h1>about</h1>
	<div class="about-card">
		<h2>JovLabs Ai</h2>
		<p>
			Jovlabs Ai is a proof of concept that allows you to run any open sourced LLM locally from your
			own GPU and serve it to the whole world on the internet. The backend is python, and the front
			end is done using the Svelte framework.
		</p>
		<p>
			Only registered users are allowed to actually chat with the various Ai personalities. If you
			would like access please contact us. Otherwise, enjoy the proof of concept you see here
		</p>
		<p>
			deep in the bowels of a sweltering basement, mad scientists run in every direction, frantic to
			deliver the results of their latest experiments.
		</p>
		<p>
			Reserved space for a future time when more interesting (and accurate) information is added
			here.
		</p>
	</div>
</div>

<style>
	.field-container {
		max-width: 80%;
		margin: 0 auto;
	}
	h1 {
		color: var(--text-3);
	}
	h2 {
		margin-bottom: 2rem;
		color: var(--text-2);
	}
	.about-card {
		background-image: var(--bg-grad);
		border: 3px solid var(--border);
		border-radius: 16px;
		padding: 1.75rem 1.75rem;
		margin-block: 4rem;
	}
	p {
		margin-block: 1rem;
		color: var(--text-2);
	}
	@media only screen and (max-width: 767px) {
		.field-container {
			max-width: 100%;
		}
		.about-card {
			margin-top: 1rem;
			margin-bottom: 6rem;
		}
		h1 {
			display: none;
		}
	}
</style>
