<script>
	
	import Board from "./Board.svelte";
</script>

<div class="game">
	<div>
		<Board />
	</div>
	<div class="game-info">
		<div></div>
		<ol></ol>
	</div>
</div>

<style>

:global(body) {
  font: 14px "Century Gothic", Futura, sans-serif;
  margin: 20px;
}


.game {
	display: flex;
	flex-direction: row;
}

.game-info {
  margin-left: 20px;
}
</style>