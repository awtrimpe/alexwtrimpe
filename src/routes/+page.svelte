<script>
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
</script>

<body>
	<h1 id="title">alexwtrimpe.com</h1>
	<main>
		<h2>Background</h2>
		<p>
			I am a spring 2018 graduate of Indiana University's School of Informatics, Computing,
			and Engineering. After graduation, I started working for Ford Motor Company in their
			rotational college graduate program. During that time I also acquired my Master's of
			Business Administration from the University of Michigan - Dearborn.
		</p>
		<h2>Expertise</h2>
		<p>
			Over the years I have learned quite a few technologies. Some I am more knowledgeable in
			than others, while others I have high proficiency. Here are a few that I most enjoy.
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

		<h2>About this Site</h2>
		<p>
			Overall, this site sits at only kilobytes in size. The goal was create a page that would
			be responsive, but would be extremely small. The desire was to reduce server costs to a
			minimum and maximize efficiency of load time. To do this I:
		</p>

		<ul>
			<li>Used only a single HTML file for the site</li>
			<li>Favored embedded SVGs over image files</li>
			<li>Favored CSS over JS</li>
			<li>Minified the file before deployment</li>
		</ul>
		<p>
			Of course there is tooling and frameworks that can make this easier, but I kept this
			basic and simple to reduce any pain in long-term maintenance
		</p>

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
	</main>
</body>

<footer>
	<!-- Copyright -->
	<div class="copyright">Alex W. Trimpe &copy;</div>
	&nbsp;
	<span id="year">{year}</span>
</footer>

<style>
	body {
		background-color: #201e22;
		color: white;
		font-family: Arial, sans-serif;
	}

	main {
		background-color: #515151;
		border-radius: 15px;
		margin: 2em 1em;
		padding: 2em;
	}

	footer {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	#title {
		margin: 0;
		text-align: center;
	}

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
