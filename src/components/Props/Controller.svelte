<script>
    import ObjectProps from "./ObjectProps.svelte";
    import Props from "./Props.svelte";

    const pkg = {
        name: 'svelte',
        version: 3,
        speed: 'blazing',
        website: 'https://svelte.dev',
    }

</script>

<Props answer={42} />
<Props />

<ObjectProps {...pkg}/>