<script>
    let isDarkMode = false;

    function toggle() {
        isDarkMode = !isDarkMode;
        window.document.body.classList.toggle('dark-mode');
    }
</script>

<div class="toggle-switch" on:click={toggle} class:active={isDarkMode}>
    <div class="switch"></div>
</div>

<style>
    .toggle-switch {
        width: 50px;
        height: 26px;
        background-color: #ccc;
        border-radius: 26px;
        position: relative;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .toggle-switch.active {
        background-color: #0084f6;
    }

    .switch {
        width: 22px;
        height: 22px;
        background-color: white;
        border-radius: 50%;
        position: absolute;
        top: 2px;
        left: 2px;
        transition: left 0.3s;
    }

    .toggle-switch.active .switch {
        left: calc(100% - 24px);
    }

    :global(body.dark-mode) .toggle-switch.active {
        background-color: #0084f6;
    }
</style>
