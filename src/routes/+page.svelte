<script lang="ts">
	import type { Message } from '$lib/Message';
	import ModalForm from '$lib/components/Form/Form.svelte';
	import MessageDisplay from '$lib/components/MessageDisplay/MessageDisplay.svelte';

	let messages: Message[] = [];

	function handleSubmit(author: string, text: string) {
		if (author && text) messages = [...messages, { author, text }];
	}
</script>

<div class="container my-5">
	<h1 class="text-center">Message Board</h1>

	<ModalForm {handleSubmit} />

	{#each messages as message}
		<MessageDisplay {message} />
	{/each}
</div>
