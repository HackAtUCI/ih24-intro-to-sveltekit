<script lang="ts">
	export let handleSubmit: (author: string, text: string) => void;
	let author: string = "";
	let text: string = "";
</script>

<form on:submit|preventDefault={() => handleSubmit(author, text)} class="my-5">
	<div class="mb-3">
		<label class="form-label" for="author">Author</label>
		<input type="text" id="author" name="author" class="form-control" bind:value={author} required/>
	</div>

	<div class="mb-3">
		<label class="form-label" for="text">Text</label>
		<textarea id="text" name="text" class="form-control" bind:value={text} required></textarea>
	</div>

	<button type="submit" class="btn btn-primary">Submit</button>
</form>
