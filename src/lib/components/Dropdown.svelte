<script lang="ts">
	import { slide } from 'svelte/transition';
	export let heading: String;
	export let content: String;
	export let link: string;
	let isOpen = false;
	const toggle = () => (isOpen = !isOpen);
</script>



<div class="Dropdown">
	<button class={isOpen ? 'active' : ''} on:click={toggle} aria-expanded={isOpen}>
		<span class="heading">{heading}</span>
		{#if isOpen}
			<span class="icon">➖</span>
		{:else}
			<span class="icon">➕</span>
		{/if}
	</button>

	{#if isOpen}
		<span class="inside" transition:slide={{ duration: 300 }}>
			<p>
				{content}
			</p>
			<div class="link">
				<a href={link} class="link-text" target="_blank" rel="noopener noreferrer">
					Link
				</a>
			</div>
		</span>
	{/if}
</div>


<style>
	p {
		color: var(--left);
		padding: 0.3rem 1.5rem;
	}

	button {
		 
		border: white;
		background: none;
		display:block; 
		color: inherit; 
		cursor: pointer;
		font-size: 1.75rem; 
		margin: 0;
		padding-bottom: 0.5em; 
		padding-top: 0.5em;
		position: center;
		border-radius: 25px;
		justify-content: space-between;
		align-items: center;
		display: flex;
		color: var(--left);
		padding: 0.5em;
	}

	button:hover {
		border-radius: 25px;
		background-color: rgb(29, 57, 135);
		color: var(--text);
	}

	button:active {
		border-radius: 25px;
		background-color: white;
		color: var(--text);
	}

	a:link {
		
		text-decoration: none;
		color: var(--left);
	}

	a:visited {
		
		text-decoration: none;
		color: var(--left);
	}

	.inside {
		border-radius: 25px;
		background-color: rgb(22, 38, 84);
		text-align: left;
		height: auto;
		margin: 0;
		padding-right: 0;
	}

	.active {
		
		background-color: var(--split);
		color: var(--text);
	}
	.Dropdown {
		border-radius: 25px;
		display: flex;
		flex-direction: column;
		width: 100%;
        color:white;
	}

	.Dropdown .inside {
		width: 100%;
        
	}

	.Dropdown button {
		width: 100%;
	}

	.link {
		border-radius: 25px;
		background-color: var(--text);
		display: flex;
		align-items: center;
		justify-content: center;
		color:  rgb(253, 253, 253);
		font-size: 1.5rem;
		margin: 0;
		padding: 0.5em;
	}

	.link-text {
		color: rgb(249, 248, 252);
		border: 2px solid var(--left);
		
	}

	.link-text:hover {
		color: rgb(117, 196, 248);
		
	}




</style>