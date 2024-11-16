<script lang="ts">
	import { onMount } from "svelte";
	import { clickOutside } from "../services/outside_click";

	export let dialog: HTMLDialogElement;

	onMount(async () => {
		document.title = "Alex W. Trimpe";
		dialog = document.getElementsByTagName(
			"dialog",
		)[0] as HTMLDialogElement;
	});

	// Show the dialog when clicking "Delete everything"
	export function showDialogClick(diag: HTMLDialogElement): null {
		diag.show();
		return null;
	}

	const closeClick = (diag: HTMLDialogElement): null => {
		diag.close();
		return null;
	};
</script>

<dialog bind:this={dialog} on:close>
	<div
		use:clickOutside
		on:click_outside={closeClick(dialog)}
		style="height: 100%;"
	>
		<div class="close-button">
			<button on:click={closeClick(dialog)}>&#10006;</button>
		</div>
		<div class="dialog-content">
			<slot />
		</div>
	</div>
</dialog>
