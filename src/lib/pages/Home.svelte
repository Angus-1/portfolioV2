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
      <h1 class="text-5xl m-6 {color} font-light">Hi, I'm Angel.</h1>
      <p class="text-2"> 💻 Aspiring Software Engineer 📱 </p> <br> 
      <p class="subtitle">   🔹 California State University, Fullerton 🔸  </p> <br>
  </div>
    <Socials color="white" sizeClass="h-8 w-8"/>
</div>

<style>
  #bg{
    background-image: radial-gradient(circle,#2064e2, #16519e,#26434b);  
   }
  .text-2{
  font-size: 1.7rem;  
  margin: 0rem;
  margin-top: 0rem;
  font-weight: 200;
  line-height: 3rem;
  color:rgb(215, 219, 223);
 }    
 
  .subtitle {
    font-size: 1.8rem; 
     margin: 0rem;
    font-weight: 200;
    color:rgb(215, 219, 223);
    padding-left: 3vw;
    
  }
</style>
