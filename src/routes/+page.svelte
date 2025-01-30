

<script>
    import '@picocss/pico';
    import Card from './Card.svelte';
    import challenges from "/src/challenges.json"
    let name = "Seb"
    let subtitle = `More difficulties for more <strong> fun !</strong>` 
    let src = "/challenges-wallpaper2.jpg"
    let points = $state(0)
    const addPoint = () => {
        points ++
    }
    console.log(challenges.data)
</script>
<hgroup>
    <h1 class="pico-color-cyan-200">Lethal Company Challenges</h1>
    <p>{@html subtitle}</p>
</hgroup>
<p>Points de {name.toLocaleUpperCase()} : {points}</p>
<button onclick={addPoint}> + </button>
{#each challenges.data as challenge, index}
<Card title={challenge.title} description={challenge.description}/>
{/each}
<img src={src} alt="lethal company wallpaper" />
<main>
    
</main>
<style>
p {
    font-style: italic;
}
</style>
