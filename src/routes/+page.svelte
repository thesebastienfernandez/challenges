

<script>
    import '@picocss/pico'
    import Card from './Card.svelte';
    import challenges from "/src/challenges.json"
    let name = "Seb"
    let subtitle = `More difficulties for more <strong> fun !</strong>` 
    let src = "/challenges-wallpaper2.jpg"
    let points = $state(0)
    const addPoint = () => {
        points ++
    }
</script>
<header>
    <hgroup>
        <h1 class="pico-color-cyan-200">Lethal Company Challenges</h1>
        <p>{@html subtitle}</p>
    </hgroup>
</header>
<main>
    <span>
        <p>Points de {name.toLocaleUpperCase()} : {points}</p>
        <button onclick={addPoint}> + </button>
    </span>
    <section id="challenges">
        {#each challenges.data as challenge, index}
            <Card title={challenge.title} description={challenge.description} type={challenge.type} name={name}/>
        {/each}
    </section>
    <section>
        <img src={src} alt="lethal company wallpaper" />
    </section>
</main>





<style>
#challenges {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around; 
    max-width: 100%;
}
p {
    font-style: italic;
}
</style>
