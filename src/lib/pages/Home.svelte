<script lang="ts">
  import Page from "$lib/components/Page.svelte";
  import Socials from "$lib/components/Socials.svelte";
  import { neutralBackground } from "$lib/utils/constants";

  let color = "text-grey-200"; 
  export let backgroundClass = neutralBackground;

</script>
<Page id="home"  {backgroundClass}> 

<div
  class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed"
   >
  <div class="text-center">
      <h1 class="text-6xl m-6 {color} font-light">Hi, I'm Angel.</h1>
      <p class="text-2xl m-2">   Information Technology Professional </p> <br> 
      <p class="text-xl m-2">    California State University, Fullerton Graduate Student  </p> <br>

  </div>

    <Socials color="white" sizeClass="h-8 w-8"/>
</div>
</Page>
<style>

</style>
