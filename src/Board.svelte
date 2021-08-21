<script>
import Square from "./Square.svelte";

var squares = new Array(9).fill('');
var isNext = true;
var status = '';

function handleClick(index) {
    if (squares[index] != '') return;

    if (calculateWinner(squares) || squares[index]) {
      return;
    }
    
    var state = isNext ? "X" : "O";
    squares[index] = state;
    status = 'Next player is:' + isNext ? "O" : "X";
    isNext = !isNext;

    console.log('Squares: ' + squares.toString());
}

function calculateWinner() {
  const lines = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ];
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}

</script>

<div>
    <div class="status">Next Player: {status}</div>

    <div class="board-row">
        <Square value={squares[0]} on:setState={() => handleClick(0)} />
        <Square value={squares[1]} on:setState={() => handleClick(1)} />
        <Square value={squares[2]} on:setState={() => handleClick(2)} />
    </div>
    <div class="board-row">
        <Square value={squares[3]} on:setState={() => handleClick(3)} />
        <Square value={squares[4]} on:setState={() => handleClick(4)} />
        <Square value={squares[5]} on:setState={() => handleClick(5)} />
    </div>
    <div class="board-row">
        <Square value={squares[6]} on:setState={() => handleClick(6)} />
        <Square value={squares[7]} on:setState={() => handleClick(7)} />
        <Square value={squares[8]} on:setState={() => handleClick(8)} />
    </div>
</div>

<style>

    .status {
        margin-bottom: 10px;
    }
    
    .board-row::after {
        clear: both;
        content: "";
        display: table;
    }
</style>

