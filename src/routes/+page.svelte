<script lang="ts">
	import { onMount } from 'svelte';
	import About from './dialogs/about.svelte'
	import Background from './dialogs/background.svelte';
	import Contact from './dialogs/contact.svelte';
	import Dialog from './Dialog.svelte';
	import Expertise from './dialogs/expertise.svelte';
	import Logo from '../images/at-logo.svelte';

	let dialog: HTMLDialogElement;
	let i = 0;
	const year = new Date().getFullYear();
	const dialogs = [
		{
			title: 'Background',
			component: Background,
		},
		{
			title: 'Expertise',
			component: Expertise,
		},
		{
			title: 'About Site',
			component: About,
		},
		{
			title: 'Contact',
			component: Contact,
		}
	];

	onMount(async () => {
		document.title = 'Alex W. Trimpe';
	});
</script>

<main>
	<div>
		<div class="title-icon">
			<Logo />
		</div>
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
			{#each dialogs as diag, index}
				<button on:click={() => {dialog.showModal(); i=index}}>{diag.title}</button>
			{/each}
		</span>
	</div>
	<Dialog bind:dialog>
		<svelte:component this={dialogs[i].component} />
	</Dialog>
</main>

<footer>
	<!-- Copyright -->
	<div class="copyright">Alex W. Trimpe &copy;</div>
	&nbsp;
	<span id="year">{year}</span>
</footer>
