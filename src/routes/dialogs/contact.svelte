<script lang="ts">
	import Bluesky from "../../images/bluesky-logo.svelte";
	import LinkedIn from "../../images/linkedin.svelte";
	import Signal from "../../images/signal.svelte";
	const contacts = [
		{
			link: "https://bsky.app/profile/awtrimpe.bsky.social",
			image: Bluesky,
			text: "awtrimpe.bsky.social",
		},
		{
			link: "https://www.linkedin.com/in/alexwtrimpe/",
			image: LinkedIn,
			text: "/in/alexwtrimpe",
		},
		{
			linked: "https://signal.me/#eu/JsORTnAW1ESVNCw8HxE5mZ5Vq9D-mQgzfZS_XQ_ccnzH4bLZ3YZP0beHzg-e1GUe",
			image: Signal,
			text: "awtrimpe.11",
		},
	];
</script>

<h2>Contact</h2>
<p>Feel free to contact me at any time</p>
<br />
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
		justify-content: center;
		gap: 1em;
		width: 100%;
	}

	.contact .icon {
		display: flex;
		flex-direction: column;
		align-items: center;
		transition: all 0.3s ease-in-out;
		width: 8em;
		height: 9em;
		text-decoration: none;
	}

	.contact .icon:hover {
		transform: translate3d(0, 0, 0);
		perspective: 1000px;
		backface-visibility: hidden;
		animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
		color: rgba(255, 255, 255, 0.75);
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

	@media only screen and (max-width: 1000px) {
		.contact {
			flex-direction: column;
		}

		.contact a {
			margin: auto;
		}
	}
</style>
