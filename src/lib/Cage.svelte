<script>
import { getContext } from "svelte";
import { key } from "./utilt";


    export let i
    export let item

    let arr = getContext(key)

    function tap(event) {
        item = (item === 1) ? -1 : -2
        event.target.disabled = true
        let table = arr.getTable()
        table[i] = item 
        console.log(table);
    }
</script>
<button on:click={tap}> {item} </button>