<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<script>
    let snake = [{ x: 5, y: 5 },{ x: 4, y: 5 },{ x: 3, y: 5 }];
    let direction = { x: 1, y: 0 };

    const move = () => {
        snake = [{ x: snake[0].x + direction.x, y: snake[0].y + direction.y }, ...snake.slice(0, -1)];
    };

    setInterval(move, 200);
</script>

<div>
    {#each snake as segment}
        <div class="snake-segment" style="top: {segment.y * 20}px; left: {segment.x * 20}px;"></div>
    {/each}
</div>

<style>
    .snake-segment {
        position: absolute;
        width: 20px;
        height: 20px;
        background: darkviolet;
    }


</style>
