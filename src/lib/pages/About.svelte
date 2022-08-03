<script lang="ts">
  import Link from "$lib/components/Link.svelte";
  import Page from "$lib/components/Page.svelte";
  import Text from "$lib/components/Text.svelte";
  import { primaryBackground } from "$lib/utils/constants";

  export let backgroundClass = primaryBackground;
</script>

<Page id="about" title=" " {backgroundClass}>
  <Text>
    <section id = About> 
      <div class="about-container">
         <section>
               <h2 class="about-title">About me</h2><br>
               <div class = "header-image"></div>
               <div class="about-subtitle">
                   <p>
                  I'm a first generation student majoring in computer science at California State University, Fullerton. <br><br>
                  
                  I really enjoy learning new concepts on a regular basis, some fields I find pretty interesting to research in my free time are web development, game development, and occasionally cyber security. <br><br>
                 
                  Outside of school I like to play video games, learn about cars, lift weights, listen to many types of music genres, and try new foods. My favorite game franchise is the Elder Scrolls series and my favorite food is Sushi! 
                   </p>     
             </div>
           </section>
      </div>
      </section>
  </Text>
</Page>
<style>


.about-container {
      position: relative;
      background-color: #192a4e; 
      background-position-x: right; 
      border-radius: 10px;
      padding-left: 20px;
      padding-bottom: 10px;
      color:rgb(154, 213, 250);
  }
  .about-title {
       font-size: 3.0rem;
       font-weight: 650;
    
       color:rgb(215, 219, 223);
       text-align: center;
   }
   
   .about-subtitle {
       margin-top: -2rem;
       width: 70%;
       font-weight: 500;
       font-size: 1.5rem;
       line-height: 2rem;
       color:rgb(215, 219, 223);
   }
</style>