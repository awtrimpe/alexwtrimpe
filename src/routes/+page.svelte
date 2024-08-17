<script lang="ts">
	import { onMount } from 'svelte';
	import Angular from '../images/angular.svelte';
	import CSharp from '../images/c-sharp.svelte';
	import Express from '../images/express.svelte';
	import Flask from '../images/flask.svelte';
	import GCP from '../images/gcp.svelte';
	import GitHub from '../images/github.svelte';
	import Go from '../images/go.svelte';
	import JavaScript from '../images/javascript.svelte';
	import Jenkins from '../images/jenkins.svelte';
	import LinkedIn from '../images/linkedin.svelte';
	import Postgres from '../images/postgres.svelte';
	import Python from '../images/python.svelte';
	import Signal from '../images/signal.svelte';
	import Strapi from '../images/strapi.svelte';
	import Tekton from '../images/tekton.svelte';
	import Typescript from '../images/typescript.svelte';
	import WordPress from '../images/wordpress.svelte';
	const images = [
		Angular,
		CSharp,
		Express,
		Flask,
		GCP,
		GitHub,
		Go,
		JavaScript,
		Jenkins,
		Postgres,
		Python,
		Strapi,
		Tekton,
		Typescript,
		WordPress
	];

	let dialog: HTMLDialogElement;
	let dialog2: HTMLDialogElement;
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
	const year = new Date().getFullYear();
	const dialogs = [
		{
			title: 'Background',
			component: ''
		},
		{
			title: 'Expertise',
			component: ''
		},
		{
			title: 'About Site',
			component: ''
		},
		{
			title: 'Contact',
			component: ''
		}
	];

	onMount(async () => {
		document.title = 'Alex W. Trimpe';
		dialog = document.getElementById('confirmation-dialog') as HTMLDialogElement;
		dialog2 = document.getElementById('confirmation-dialog2') as HTMLDialogElement;
	});

	// Show the dialog when clicking "Delete everything"
	const showDialogClick = (diag: HTMLDialogElement): null => {
		diag.show();
		return null;
	};

	const closeClick = (diag: HTMLDialogElement): null => {
		diag.close();
		return null;
	};
</script>

<body>
	<div class="title-icon"></div>
	<span class="title-line">
		<span></span>
		<span></span>
	</span>
	<div class="title">
		<hr />
		<h1>Alex W Trimpe</h1>
		<hr />
	</div>
	<span class="title-line">
		<span></span>
		<span></span>
	</span>
	<span class="links">
		{#each dialogs as dialog}
			<div>{dialog.title}</div>
		{/each}
	</span>
	<main>
		<section>
			<h2>Background</h2>
			<p>
				I am a spring 2018 graduate of Indiana University's School of Informatics,
				Computing, and Engineering. After graduation, I started working for Ford Motor
				Company in their rotational college graduate program. During that time I also
				acquired my Master's of Business Administration from the University of Michigan -
				Dearborn.
			</p>
		</section>

		<section>
			<h2>Expertise</h2>
			<p>
				Over the years I have learned quite a few technologies. Some I am more knowledgeable
				in than others, while others I have high proficiency. Here are a few that I most
				enjoy.
			</p>
			<div class="technologies">
				<div class="tech">
					{#each images as image}
						<span class="icon">
							<svelte:component this={image} />
						</span>
					{/each}
				</div>
			</div>

			<button on:click={() => showDialogClick(dialog)}>Read More</button>
			<dialog id="confirmation-dialog">
				<div class="close-button">
					<button on:click={closeClick(dialog)}>&#10006;</button>
				</div>
				<p>Hello world!</p>
			</dialog>
		</section>

		<section>
			<h2>About this Site</h2>
			<p>
				This site was created using <a href="https://kit.svelte.dev/" target="_blank"
					>SvelteKit</a
				>. The desire was to reduce server costs to a minimum and maximize efficiency of
				load time. To do this I:
			</p>

			<ul>
				<li>Favored embedded SVGs over image files</li>
				<li>Favored CSS over JS</li>
				<li>Opted for client-side rendering</li>
			</ul>
			<button on:click={() => showDialogClick(dialog2)}>Read More</button>
			<dialog id="confirmation-dialog2">
				<div class="close-button">
					<button on:click={closeClick(dialog2)}>&#10006;</button>
				</div>
				<p>
					This site was made using Svelte structured for client-side only. The reason for
					using Svelte was because of its simplicity to get started, scalability, and
					small size. I also particularly am a fan of SvelteKit enforcing <a
						href="https://kit.svelte.dev/docs/accessibility">accessibility</a
					> rules by default.
				</p>
				<p>
					I chose to not include an project dependencies outside of the standard
					SvelteKit. This is to reduce the risk of vulnerabilities in 3rd-party packages,
					as well as reduce the risk of the site breaking during version upgrades. Overall
					this should limit the long-term maintenance effort required.
				</p>
				<p>While I am a huge fan of various design systems,</p>
				<ul>
					Here are some of my favorites design systems if you need one
					<li><a href="https://primedesignsystem.com/" target="_blank">Prime 6</a></li>
					<li><a href="https://m3.material.io/" target="_blank">Material 3</a></li>
					<li>
						<a href="https://atlassian.design/" target="_blank">Atlassian Design</a>
					</li>
				</ul>
				<p>
					What that means though, is that for better or worse, what you see here was
					developed all on my own.
				</p>
			</dialog>
		</section>

		<section>
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
		</section>
	</main>
</body>

<footer>
	<!-- Copyright -->
	<div class="copyright">Alex W. Trimpe &copy;</div>
	&nbsp;
	<span id="year">{year}</span>
</footer>

<style>
	div.technologies {
		overflow: hidden;
		width: 100%;
		height: 20em;
	}

	.technologies .tech {
		display: flex;
		position: relative;
		overflow: hidden;
		left: 100%;
		align-items: center;
		width: fit-content;
		margin: 1em 0;
		padding: 0;
		gap: 1em;
		animation: 3s linear 0s infinite alternate horizontal-bounce;
	}

	.technologies .tech .icon {
		width: 10em;
	}

	.technologies:hover .tech,
	.technologies .tech:hover {
		animation-play-state: paused;
	}

	.contact {
		display: flex;
		gap: 1em;
	}

	.contact .icon {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-decoration: none;
		color: white;
		transition: all 0.3s ease-in-out;
		width: 6em;
	}

	.contact .icon:hover {
		color: rgba(255, 255, 255, 0.75);
		animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
		transform: translate3d(0, 0, 0);
		backface-visibility: hidden;
		perspective: 1000px;
	}

	@keyframes horizontal-bounce {
		0%,
		25% {
			transform: translateX(0%);
			left: 0%;
		}

		75%,
		100% {
			transform: translateX(-100%);
			left: 100%;
		}
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
