<script>
  import Footer from "$lib/components/Footer.svelte";
</script>

<div class="relative flex flex-col justify-center items-center">
  <h1 class="text-8xl font-bold m-10">Fifteen Puzzle</h1>

  <div class="w-lg flex justify-between items-center mb-5">
    <button
      id="new-game-btn"
      class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer"
      >Nuevo juego</button
    >

    <div class="flex items-center">
      <label for="difficulty" class="mr-2">Dificultad:</label>
      <select
        id="difficulty"
        class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] text-white text-lg cursor-pointer"
      >
        <option value="3">Facil</option>
        <option value="4">Medio</option>
        <option value="5">Dificil</option>
      </select>
    </div>
  </div>

  <div
    class="grid grid-cols-4 grid-rows-4 gap-[5px] w-[400px] h-[400px] rounded-xs bg-[#00995E] shadow"
    id="puzzle-container"
  ></div>

  <div class="w-lg flex justify-between items-center mt-5">
    <button
      id="shuffle-btn"
      class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer"
      >Aleatorio 🎲</button
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

<svelte:head>
  <title>Fifteen Puzzle Game</title>
  <meta name="description" content="Juego de puzzle de 15 piezas" />
  <meta name="keywords" content="puzzle, 15 puzzle, juego, svelte" />
  <meta name="author" content="Francis Castillo" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

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
