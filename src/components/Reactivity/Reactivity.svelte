<script>
    let count = 0;
    $: doubled = count * 2;
    $: {
        console.log(`The count is ${count}`);

        if (count >= 10) {
            alert(`Count is dangerously high`);
            count = 9;
        }
    }

    function handleClick() {
        count += 1;
    }
</script>

<button on:click={handleClick}>
    Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<p>
    {count} doubled is {doubled}
</p>