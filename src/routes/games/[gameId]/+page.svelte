<script lang='ts'>

    const players = Array.from({length: 8}, (_, i) => i)
</script>

<div class="flex items-center justify-center min-h-screen">
    <div>
        <div
            class="relative bg-green-700 outline-12 outline-solid outline-amber-950 rounded-full aspect-[1/1]"
            style="width: min(70vw, 100vh);"
        >
            {#each players as player, index}
                <div class="absolute transform -translate-x-1/2 -translate-y-1/2">
                    player name
                </div>
            {/each}
        </div>
    </div>
  </div>
