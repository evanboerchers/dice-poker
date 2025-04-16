<script lang='ts'>
    let {children} = $props();
</script>

<div
    id="table"
    class="relative bg-green-700 outline-12 outline-solid outline-amber-950 rounded-full aspect-[1/1]"
    style="width: min(70vw, 100vh);"
>
    {@render children()}
</div>

