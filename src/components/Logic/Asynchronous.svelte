<script>
    async function getRandomNumber() {
        const res = await fetch(`https://www.random.org/integers/?num=1&min=1&max=10&col=1&base=10&format=plain&rnd=new`);
        const text = await res.text();

        if (res.ok) {
            return text;
        } else {
            throw new Error(text);
        }
    }

    let promise = getRandomNumber();

    function handleClick() {
        promise = getRandomNumber();
    }

</script>

<button on:click={handleClick}>
    Generate Random
</button>

{#await promise}
    <p>...waiting</p>
{:then number} 
    <p>The random number is {number}</p>
{:catch error}
    <p style="color: red">{error.message}</p>
{/await}