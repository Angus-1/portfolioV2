<script lang="ts">
  import Anchor from "$lib/components/Anchor.svelte";
  import Socials from "$lib/components/Socials.svelte";
  let color = "text-grey-200";
</script>

<Anchor id="home" />
<div
  class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed bg-neutral-600 bg-blend-soft-light dark:bg-blend-soft-light dark:bg-neutral-700"
  id="bg">
  <div class="text-center">
      <h1 class="text-6xl m-6 {color} font-light">Hi, I'm Angel.</h1>
      <p class="text-2xl m-2"> 💻  Information Technology  📱</p> <br> 
      <p class="text-xl m-2">   🔹 California State University, Fullerton Graduate Student🔸  </p> <br>

  </div>
    <Socials color="white" sizeClass="h-8 w-8"/>
</div>

<style>
  #bg{
    background-image: radial-gradient(circle,#2064e2, #16519e,#26434b);  
   }
</style>
