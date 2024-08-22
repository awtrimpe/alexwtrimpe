<script lang="ts">
	import LinkedIn from '../../images/linkedin.svelte';
	import Signal from '../../images/signal.svelte';
	const contacts = [
		{
			link: 'https://www.linkedin.com/in/alexwtrimpe/',
			image: LinkedIn,
			text: '/in/alexwtrimpe'
		},
		{
			linked: 'https://signal.me/#eu/JsORTnAW1ESVNCw8HxE5mZ5Vq9D-mQgzfZS_XQ_ccnzH4bLZ3YZP0beHzg-e1GUe',
			image: Signal,
			text: 'awtrimpe.11'
		}
	];
</script>

<h2>Contact</h2>
<p>Feel free to contact me at any time</p>
<div class="contact">
	{#each contacts as contact}
		<a class="icon" href={contact.link} target="_blank">
			<svelte:component this={contact.image} />
			<p>{contact.text}</p>
		</a>
	{/each}
</div>

<style>
	.contact {
		display: flex;
		gap: 1em;
		width: 100%;
		justify-content: center;
	}

	.contact .icon {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-decoration: none;
		color: white;
		transition: all 0.3s ease-in-out;
		width: 8em;
	}

	.contact .icon:hover {
		color: rgba(255, 255, 255, 0.75);
		animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
		transform: translate3d(0, 0, 0);
		backface-visibility: hidden;
		perspective: 1000px;
	}

	@keyframes shake {
		10%,
		90% {
			transform: translate3d(-1px, 0, 0);
		}

		20%,
		80% {
			transform: translate3d(2px, 0, 0);
		}

		30%,
		50%,
		70% {
			transform: translate3d(-4px, 0, 0);
		}

		40%,
		60% {
			transform: translate3d(4px, 0, 0);
		}
	}
</style>
