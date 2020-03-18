<style>
    button {
        display : block;
    }

    .active {
        background-color: #ff3e00;
        color:white;
    }
</style>

<button on:click>
    <slot></slot>
</button>