<script lang="ts">
	import IU from "../../images/iu-logo.svelte";
	import UM from "../../images/um-logo.svelte";
</script>

<h2>Background</h2>
<h4>
	<i>
		Indiana University graduate with a passion for technology and business.
	</i>
</h4>
<p>
	I began my career at Ford Motor Company after earning my Bachelor's degree
	in Informatics from Indiana University's School of Informatics, Computing,
	and Engineering. During my time at Ford, I also completed my Master's of
	Business Administration from the University of Michigan - Dearborn.
</p>

<div class="flex fully-centered uni-logos">
	<div class="svg">
		<IU />
	</div>
	<div class="svg">
		<UM />
	</div>
</div>

<p>
	With a strong foundation in technology and a keen interest in business, I'm
	dedicated to crafting innovative solutions. My experience in both corporate
	and academic settings has equipped me with the skills to excel in a dynamic
	and competitive environment.
</p>

<p>
	Outside of work, I enjoy exploring Detroit's vibrant culture, tackling DIY
	projects, and tinkering with new technologies. My enthusiasm for learning
	and creating drives me to continually expand my knowledge and skills.
</p>

<style>
	.uni-logos {
		gap: 3em;
	}
	.uni-logos > .svg:first-of-type {
		width: 8em;
	}
	.uni-logos > .svg {
		width: 10em;
	}
	@media only screen and (max-width: 600px) {
		.uni-logos {
			gap: 1em;
		}
	}
</style>
