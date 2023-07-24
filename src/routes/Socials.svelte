<script>
  import yourData from "../lib/data/portfolio.json";
  import { onMount } from "svelte";
</script>

<div class={`flex flex-wrap mob:flex-nowrap link socials text-2xl`}>
  <button
    class="font-bold text-lg tablet:text-lg p-1 laptop:p-2 m-1 laptop:m-2 rounded-lg flex items-center transition-all ease-out duration-300 hover:scale-105 active:scale-100 tablet:first:ml-0 link"
    >{yourData.socials[0].title}</button>
    <button
    class="font-bold text-lg tablet:text-lg p-1 laptop:p-2 m-1 laptop:m-2 rounded-lg flex items-center transition-all ease-out duration-300 hover:scale-105 active:scale-100 tablet:first:ml-0 link"
    >{yourData.socials[1].title}</button>
    <button
    class="font-bold text-lg tablet:text-lg p-1 laptop:p-2 m-1 laptop:m-2 rounded-lg flex items-center transition-all ease-out duration-300 hover:scale-105 active:scale-100 tablet:first:ml-0 link"
    >{yourData.socials[2].title}</button>
</div>
 
<style lang="postcss">
  button {
    color: white;
    z-index: 999;
  }
</style>
