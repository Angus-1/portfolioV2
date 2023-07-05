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
          
               <div class="about-title">About me</div>
               <div class = "header-image">   <img src = 'profile.png'width="250px"  alt=linkedin/>    </div>                  
               <div class="about-subtitle">
                   
                  Hello! I'm currently studying computer science at California State University, Fullerton. <br><br><br>
                  
                 My interests include web development, and web security. <br><br><br>
                 
                 In my free time I like to lift weights, go dancing, see live music, play video games, learn about cars, and try new foods. My favorite game is the Elder Scrolls series and my favorite food is Sushi! <br><br>
                    
             </div>
           </section>
      </div>
      </section>
      
  </Text>
</Page>
<style>


.about-container {
      position: relative;
      background-color: #1F2937; 
      background-position-x: right; 
      border-radius: 10px;
      padding-left: 20px;
      padding-bottom: 10px;
      color:rgb(154, 213, 250);
  }
  .about-title {
       font-size: 3.0rem;
       font-weight: 650;
       padding-left:3rem;
      padding-top:10px;
       color:rgb(215, 219, 223);
   }
   
   .about-subtitle {
       width: 90%;
       font-weight: 500;
       font-size: 1.5rem;
       line-height: 2rem;
       color:rgb(215, 219, 223);
   }
 
 img{
  border-radius: 50%;
  margin-left:2rem;
  float:left;
  margin-right:15px;
  border-color:#4370d1;
  border-width: 4px;
 }
</style>