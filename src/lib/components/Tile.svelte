<script>
    export let index;
    export let value;
    export let moveTile;
</script>

<button
    on:click={() => moveTile(index)}
    title={index}
    class="w-20 h-20 bg-[#00995E] text-white text-4xl font-bold rounded-lg shadow-lg"
>
    {value === 16 ? '' : value}
</button>