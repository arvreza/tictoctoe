<script>
export let value = "";

import { createEventDispatcher } from 'svelte';

const dispatch = createEventDispatcher();

function setState() {
    dispatch('setState');
}
</script>

<button on:click={setState}>
    {value}
</button>

<style>

button {
    background: #fff;
    border: 1px solid #999;
    float: left;
    font-size: 24px;
    font-weight: bold;
    line-height: 34px;
    height: 34px;
    margin-right: -1px;
    margin-top: -1px;
    padding: 0;
    text-align: center;
    width: 34px;
}

button:hover {
    outline: none;
}

</style>