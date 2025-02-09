<script lang="ts">

</script>

<div class="relative flex flex-col justify-center items-center">

    <h1 class="text-8xl font-bold m-10"> Puzzle Game </h1>

    <div class="w-lg flex justify-between items-center mb-5">
        <button id="new-game-btn" class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer">New Game</button>

        <div class="flex items-center">
            <label for="difficulty" class="mr-2">Difficulty:</label>
            <select id="difficulty" class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] text-white text-lg cursor-pointer">
                <option value="3">Easy</option>
                <option value="4">Medium</option>
                <option value="5">Hard</option>
            </select>
        </div>
    </div>

    <div class="grid grid-cols-4 grid-rows-4 gap-[5px] w-[400px] h-[400px] rounded-xs bg-[#00995E] shadow" id="puzzle-container"></div>

    <div class="w-lg flex justify-between items-center mt-5">

        <button id="shuffle-btn" class="py-2.5 px-5 border-0 rounded-xs bg-[#00995E] hover:bg-[#007A4D] text-white text-lg cursor-pointer">shuffle 🎲</button>

        <div class="flex">
            <div class="flex flex-col">
                <p>Movimientos: </p>
                <span id="moves" class="font-bold">0</span>
            </div>
            <div class="flex flex-col ml-5">
                <p>Tiempo: </p>
                <span id="time" class="font-bold">0</span>
            </div>
        </div>
    </div>

    <div id="message" class="mt-5 text-center hidden">
        <p> Felicidades! resolviste el puzzle. 🎈 </p>
    </div>

    <div class="mt-10 text-center">
        Made with ❤️ by <a class="hover:text-[#007A4D]" href="https://github.com/ingfranciscastillo" aria-label="github">Francis Castillo, </a>
        powered by <a href="https://svelte.dev/" aria-label="svelte">Svelte</a>

        <div class="flex justify-center mt-5 gap-[5px]">
            <a href="https://github.com/ingfranciscastillo">
            <img src="https://img.shields.io/github/followers/ingfranciscastillo?label=Follow%20%40ingfranciscastillo&style=social" alt="github" />
        </a>
        <a href="https://github.com/ingfranciscastillo/puzzle-game">
            <img src="https://img.shields.io/github/stars/ingfranciscastillo/puzzle-game?style=social" alt="github" />
        </a>
        </div>
    </div>

</div>

<style>
    :global(body){
        background-color: #00284C;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        color: #ededed;
}

</style>