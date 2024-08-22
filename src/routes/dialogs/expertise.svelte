<script lang="ts">
		import Angular from '../../images/angular.svelte';
	import CSharp from '../../images/c-sharp.svelte';
	import Express from '../../images/express.svelte';
	import Flask from '../../images/flask.svelte';
	import GCP from '../../images/gcp.svelte';
	import GitHub from '../../images/github.svelte';
	import Go from '../../images/go.svelte';
	import JavaScript from '../../images/javascript.svelte';
	import Jenkins from '../../images/jenkins.svelte';
	import Postgres from '../../images/postgres.svelte';
	import Python from '../../images/python.svelte';
	import Strapi from '../../images/strapi.svelte';
	import Tekton from '../../images/tekton.svelte';
	import Typescript from '../../images/typescript.svelte';
	import WordPress from '../../images/wordpress.svelte';
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
</script>

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
</style>
