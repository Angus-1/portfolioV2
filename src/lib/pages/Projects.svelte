<script lang="ts">
  import { primaryBackground } from "$lib/utils/constants";
  import Page from "$lib/components/Page.svelte";
 
  import Dropdown from '$lib/components/Dropdown.svelte';
  import {projects} from '../utils/projects';

	let innerWidth = 0
	let innerHeight = 0
	$: mobile = innerWidth < 1080;

  export let backgroundClass = primaryBackground;
</script>

<Page id="projects" title="Projects" {backgroundClass}>

  <div class="projects">
    <h1 class="project-experience"> </h1>			
      {#each projects as project}
        <Dropdown heading={project.heading} content={project.content} link={project.link}/>
      {/each}
    </div>


</Page>

<style>

.projects{
  position: relative;
  color:rgb(191, 229, 252);
  background-color: #1f2937;  
  padding:0;
  border-radius: 10px;
  padding-left: 10px; 
  margin-bottom: 15rem;
 }

</style>
