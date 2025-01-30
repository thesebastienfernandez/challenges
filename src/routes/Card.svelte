<button onclick={() => clickOnChallenge()} class="challenge">
    <h3>{title}</h3>
    <p>{description}</p>
    {#if checked === true}
        <p>{messageCheck()}</p>
    {/if}
</button>

<script>
let {title, description, type, name} = $props()
let checked = $state(false)
const clickOnChallenge = () => {
    checked = !checked
}
const messageCheck = () => {
    let message = ""
    if(type === "solo") {
        message = "Défi accompli par " + name
    } else {
        message = "Défi accompli par la Team"
    }
    return message
}
</script>

<style>
.challenge {
    background-color: black;
    margin-top: 0.2em;
    margin-bottom: 0.2em;
    width: 14em;
    height: 16em;
    border: 4px black solid;
}
h3 {
    color: aquamarine;
}
p {
    font-size: small;
}
</style>