<script>
    function toggle(){
        window.document.body.classList.toggle('dark-mode')
    }
</script>

<button on:click={toggle}> <slot/> </button>

<style>
    button{
        margin-right: auto;
    }

    :global(body.dark-mode) button{
        background-color: #0084f6;
        color: white;
    }
</style>