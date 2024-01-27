<script lang="ts">
	import type { Message } from "$lib/Message";
	import MessageDisplay from "$lib/components/MessageDisplay/MessageDisplay.svelte";
	import ModalForm from "$lib/components/ModalForm/ModalForm.svelte";
	
	let messages: Message[] = [];
	
	function handleSubmit(author: string, text: string) {
		if (author && text) 
			messages = [...messages, {author, text}];
	}
	
</script>

<div class="container my-5">
	<h1 class="text-center">Message Board</h1>

	<ModalForm {handleSubmit} />

	{#each messages as message}
		<MessageDisplay {message} />
	{/each}
</div>



