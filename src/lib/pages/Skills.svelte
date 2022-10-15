<script lang="ts">
  import Card from "$lib/components/Card.svelte";
  import Page from "$lib/components/Page.svelte";
  import { primaryBackground, neutralBackground } from "$lib/utils/constants";
  const skills: Array<string> = [
    "Python",
    "Java",
    "C++",
    "Javascript",
    "Svelte",
    "React",
    "Astro",
    "HTML",
    "CSS",
    "Tailwind",
    "SQL",
    "Firebase",
    
  ];

  export let backgroundClass = neutralBackground;
</script>

<Page id="skills" title="Technical Skills" {backgroundClass}>
  <div
    class="container mx-auto grid max-w-screen-xl grid-cols-1 gap-4 md:grid-cols-3 sm:grid-cols-2"
  >
    {#each skills as skill}
      <Card>
        <div class="text-2xl font-medium text-center">
          {skill}
        </div>
      </Card>
    {/each}
  </div>

  
</Page>
