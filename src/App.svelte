<script>
  import Cage from "./lib/Cage.svelte"
  import {key} from "./lib/utilt.js"
  import { setContext } from 'svelte';

  let table = [0,1,0,1,0,1,0,1,0,1]
  setContext(key,{
    getTable:() => table
  })

  function tap(e){
  if (table[e.target.innerText] == 0){
    table[e.target.innerText] = 1
    e.target.innerText = "X"
  }
  console.log(table);
}

function test(event) {
  console.log(table)
}
</script>

<button on:click={test}>test</button>


{#each table as item, i}
  <Cage i={i} item={item}></Cage>
{/each}