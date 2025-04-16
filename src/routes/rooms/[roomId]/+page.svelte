<script lang='ts'>
	import Table from "$lib/components/table.svelte";

    const players = Array.from({length: 8}, (_, i) => i)
    
    // Position players around the table edge
    const getPlayerTranslation = (seatIndex: number, totalSeats: number): [number, number] => {
        if (seatIndex > totalSeats) throw new Error('Invalid Seat Index')
        const thetaStart = -Math.PI / 2  // Start at the top (negative y-direction)
        const thetaInterval = 2 * Math.PI / totalSeats
        const theta = thetaStart + thetaInterval * seatIndex
        
        // Using 50% as the radius puts players at the edge of the circle
        // (since 50% is half the width/height of the table)
        const radius = 50
        const x = radius * Math.cos(theta)
        const y = radius * Math.sin(theta)
        return [x, y]
    }
</script>

<div class="flex items-center justify-center min-h-screen">
    <Table>
        {#each players as player, index}
            {@const [translateX, translateY] = getPlayerTranslation(index, players.length)}
            <div class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2"
                    style={`left: ${50 - translateX}%; top: ${50 - translateY}%;`}
            > 
                Player {index + 1}
            </div>
        {/each}
    </Table>
</div>