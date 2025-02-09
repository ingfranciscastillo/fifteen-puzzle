<script>
  import Footer from "$lib/components/Footer.svelte";

  let puzzleSize = 4;
  let tiles = [];
  let emptyTile = puzzleSize * puzzleSize - 1;

  let moves = 0;
  let time = 0;
  let timer;

  function inicializePuzzle() {
    tiles = Array.from(
      { length: puzzleSize * puzzleSize - 1 },
      (_, i) => i + 1
    );
    tiles.push(null);
    shufflePuzzle();
  }

  function shufflePuzzle() {
    for (let i = tiles.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [tiles[i], tiles[j]] = [tiles[j], tiles[i]];
    }
    emptyTile = tiles.indexOf(null);
  }

  // Mueve una ficha si es válida
  function moveTile(index) {
    if (
      (index % puzzleSize === emptyTile % puzzleSize &&
        Math.abs(index - emptyTile) === puzzleSize) ||
      (Math.floor(index / puzzleSize) === Math.floor(emptyTile / puzzleSize) &&
        Math.abs(index - emptyTile) === 1)
    ) {
      [tiles[index], tiles[emptyTile]] = [tiles[emptyTile], tiles[index]];
      emptyTile = index;
    }
  }

  // Verifica si el jugador ha ganado
  function isSolved() {
    return tiles.every((tile, index) => tile === null || tile === index + 1);
  }

  // Actualiza el contador de movimientos
  function updateMoves() {
    moves++;
    document.getElementById("moves").textContent = moves;
  }

  // Inicializa el tablero al cargar el componente
  inicializePuzzle();
</script>

<svelte:head>
  <title>Fifteen Puzzle Game</title>
  <meta name="description" content="Juego de puzzle de 15 piezas" />
  <meta name="keywords" content="puzzle, 15 puzzle, juego, svelte" />
  <meta name="author" content="Francis Castillo" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="relative flex flex-col justify-center items-center">
  <h1 class="text-8xl font-bold m-10">Fifteen Puzzle</h1>

  <div class="w-lg flex justify-between items-center mb-5">
    <button
      id="new-game-btn"
      class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer"
      on:click={inicializePuzzle}>Nuevo juego</button
    >

    <div class="flex items-center">
      <label for="difficulty" class="mr-2">Dificultad:</label>
      <select
        id="difficulty"
        class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] text-white text-lg cursor-pointer"
        on:change={(e) => {
          puzzleSize = parseInt(e.target.value);
          inicializePuzzle();
        }}
      >
        <option value="3">Facil</option>
        <option value="4" selected>Medio</option>
        <option value="5">Dificil</option>
      </select>
    </div>
  </div>

  <div
    class="grid gap-[5px] w-[300px] m-5 rounded-xs bg-[#00995E] shadow"
    id="puzzle-container"
    style="grid-template-columns: repeat({puzzleSize}, 1fr);"
  >
    {#each tiles as tile, index}
      <button
        class="flex justify-center items-center text-white text-2xl font-bold rounded-xs cursor-pointer h-[70px] {tile ===
        null
          ? 'bg-[#f0f0f0] cursor-default'
          : ''}"
        on:click={() => moveTile(index)}
        on:keydown={(e) =>
          (e.key === "Enter" || e.key === " ") && moveTile(index)}
        aria-label="Tile {tile}"
        role="tileButton"
      >
        {tile}
      </button>
    {/each}
  </div>

  <div class="w-lg flex justify-between items-center mt-5">
    <button
      id="shuffle-btn"
      class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer"
      on:click={shufflePuzzle}>Aleatorio 🎲</button
    >

    <div class="flex">
      <div class="flex flex-col">
        <p>Movimientos:</p>
        <span id="moves" class="font-bold">0</span>
      </div>
      <div class="flex flex-col ml-5">
        <p>Tiempo:</p>
        <span id="time" class="font-bold">0</span>
      </div>
    </div>
  </div>

  <div id="message" class="mt-5 text-center hidden">
    <p>Felicidades! resolviste el puzzle. 🎈</p>
  </div>

  <Footer />
</div>

<style>
  :global(body) {
    background-color: #1a202c;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    color: #ededed;
  }
</style>
