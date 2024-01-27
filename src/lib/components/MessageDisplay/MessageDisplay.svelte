<script lang="ts">
	import type { Message } from "$lib/Message";

	export let message: Message;
</script>

<div class="card p-4">
	<h2>{message.text}</h2>
	<p>{message.author}</p>
</div>
