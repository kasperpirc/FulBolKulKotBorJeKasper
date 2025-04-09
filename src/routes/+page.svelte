<script lang="ts">
	export let data;

	const { games } = data;
</script>

<div class="grid grid-cols-3 p-4 gap-4 color rounded">
	{#each games as game}
		<div class="rounded-2xl bg-red-300">
			<div class=" text-lg font-bold">
				#{game.id} NAME: {game.name}
			</div>
			<div class="text-sm text-gray-600">Rating {game.rating}</div>
			<div class="text-sm text-gray-600">{game.type}</div>
			<a class=" text-white rounded-sm" href={game.id}>Edit</a>
		</div>
	{/each}
</div>

<h1 class="text-3xl font-bold underline"></h1>
<form method="POST" action="?/addGame" class=" bg-blue-300 flex flex-col gap-4 p-4">
	<div>Ime igrice:</div>
	<input name="name" required />
	<div>Kok je dobra:</div>
	<input type="range" min="1" max="10" value="5" name="rating" />
	<select name="type" required
		><option value="">Izberi tip igrice</option>
		<option value="Sport">športna</option>
		<option value="Rouge like">rouge like</option>
		<option value="FPS">shooter game</option></select
	>
	<button type="submit">Dodaj igrico</button>
</form>
