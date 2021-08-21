<script>
	
	import Board from "./Board.svelte";
</script>

<main>
	<div>
		<Board />
	</div>
	<div class="game-info">
		<div></div>
		<ol></ol>
	</div>
</main>

<style>

:global(body) {
  font: 14px "Century Gothic", Futura, sans-serif;
  margin: 20px;
}

main {
	display: flex;
	flex-direction: row;
}

.game-info {
  margin-left: 20px;
}
</style>