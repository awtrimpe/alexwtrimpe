<script lang="ts">
	import Angular from "../../images/angular.svelte";
	import CSharp from "../../images/c-sharp.svelte";
	import Express from "../../images/express.svelte";
	import Flask from "../../images/flask.svelte";
	import GCP from "../../images/gcp.svelte";
	import GitHub from "../../images/github.svelte";
	import Go from "../../images/go.svelte";
	import JavaScript from "../../images/javascript.svelte";
	import Jenkins from "../../images/jenkins.svelte";
	import Postgres from "../../images/postgres.svelte";
	import Python from "../../images/python.svelte";
	import Strapi from "../../images/strapi.svelte";
	import Tekton from "../../images/tekton.svelte";
	import Typescript from "../../images/typescript.svelte";
	import WordPress from "../../images/wordpress.svelte";
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
		WordPress,
	];
</script>

<h2>Expertise</h2>
<p>
	Over the years I have learned quite a few technologies. Some I am more
	knowledgeable in than others, while others I have high proficiency. Here are
	a few that I most enjoy.
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
<p>
	I am also a strong advocate of open source software. I have contributed to a
	few open source projects, and am active in reporting issues with self-hosted
	software.
</p>
<p>
	With many years of experience, I am able to analyze problems, identify key
	areas for improvement, and implement effective solutions that meet the needs
	of stakeholders. With a passion for open-source software and a commitment to
	contributing back to the community, I strive to continually improve my craft
	through ongoing learning and experimentation.
</p>
<p>
	As a full-stack software engineer, I bring together the best of both worlds:
	front-end and back-end expertise. My proficiency in web technologies such as
	Angular, Python, and TypeScript allows me to craft responsive user
	interfaces that seamlessly integrate with robust server-side applications.
	With experience in Express, Flask, Strapi, and WordPress, I can deploy
	scalable solutions on cloud platforms like GCP and AWS.
</p>

<style>
	div.technologies {
		width: 100%;
		height: 20em;
		overflow: hidden;
	}

	.technologies .tech {
		display: flex;
		position: relative;
		left: 100%;
		align-items: center;
		gap: 1em;
		animation: 4s linear 0s infinite alternate horizontal-bounce;
		margin: 1em 0;
		padding: 0;
		width: fit-content;
		overflow: hidden;
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
			left: 0%;
			transform: translateX(0%);
		}

		75%,
		100% {
			left: 100%;
			transform: translateX(-100%);
		}
	}

	@media only screen and (max-width: 600px) {
		.technologies .tech {
			animation: 6s linear 0s infinite alternate horizontal-bounce;
		}
	}
</style>
