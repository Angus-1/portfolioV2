<script lang="ts">
  import { primaryBackground } from "$lib/utils/constants";
  import Page from "$lib/components/Page.svelte";
 
  import Dropdown from '$lib/components/Dropdown.svelte';
  import CollapsibleCard from 'svelte-collapsible-card'


  import {projects} from '../utils/projects';

	let innerWidth = 0
	let innerHeight = 0
	$: mobile = innerWidth < 1080;

  export let backgroundClass = primaryBackground;
</script>

<Page id="projects" title="Projects" {backgroundClass}>

 

    <ul>
	
      { #each projects as project }
        <li>
          <CollapsibleCard>
            <div slot='header' class='header'>
              <div class='names'>
                <h2>{ project.heading }</h2>
              </div>
            </div>
            <div slot='body' class='body'>
              { project.content } <br><br>

              <a href={project.link} class="link-text" target="_blank" rel="noopener noreferrer">
                <p> <img src={project.image} alt="image here" width=900 > </p> </a>
                <br>  <br>
              
            </div>
        
          </CollapsibleCard>
        </li>
      { /each }
    
    </ul>


</Page>

<style>


 ul {
		list-style: none;
		padding: 0;
		margin: 0 auto;
		width:90%;
		color:  #ffffff;
		font-size: 1.5rem;
    font-weight:bold;
    background-color:#1f2937;
    border-radius: 10px;

	}
	
	li {
		margin-bottom: 0em;
    border-radius: 10px; 
    border-bottom: 1px solid #6B91A4;

	}
	
	.header {
		padding: 0.3em;
		display: flex;
    background-color: #1F2937;
    border-radius: 10px;
	}
  .header:hover{
    background-color: #2b3d57;
  }
 
  

	.names {
		padding: 0 0 0 1em;
		display: flex;
		flex-direction: column;
		justify-content: center;

	}
	
	h2 {
		margin: 0;
		width: 100%;
    
	}
	
	p {
		margin: 0;
	}
	
	.body {
    padding: 0 0 3em 3em;
	}
 



</style>
