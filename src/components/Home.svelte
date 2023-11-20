<script>
	import Scrolly from "./Scrolly.svelte";
    import '@fontsource/merriweather';
</script>

<div>
<div id="text-wrapper"> 
	<h1 id="headline">The Language Server Protocol</h1>
	<p id="intro">Code editors these days come with some fancy schmancy features like code comple<span class="tion">tion</span><span class="bar">|</span>, syntax <b id="highlight">highlighting</b>, and refactoring routines.</p>

	<p id="p-intro-end">How do language developers support these features? Let's find out.</p>
</div>
	<Scrolly />
</div>

<style>
    /* all mobile styles */
    #text-wrapper {
        position: relative;
        font-family: 'Merriweather', serif;
    }

	.tion {
		animation: fadeIn 8s;
	}
	.bar {
		animation: blinkIn 1.5s steps(5, start) infinite;
	}

	@keyframes fadeIn {
		0% { opacity: 0; }
		100% { opacity: 1; }
		}

	@keyframes blinkIn {
	to {
		visibility: hidden;
	}
	}

	#headline {
        font-size: 4em;
		max-width: 50%;
		margin: auto;
		padding: 2em;
		color: #4b0d82;
	}

	#highlight {
		color: #f58607;
	}

	#p-intro-end {

		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}

	#intro {
		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	} #text-wrapper {
        position: relative;
        font-family: 'Merriweather', serif;
    }

	.tion {
		animation: fadeIn 8s;
	}
	.bar {
		animation: blinkIn 1.5s steps(5, start) infinite;
	}

	@keyframes fadeIn {
		0% { opacity: 0; }
		100% { opacity: 1; }
		}

	@keyframes blinkIn {
	to {
		visibility: hidden;
	}
	}

	#headline {
        font-size: 4em;
		max-width: 50%;
		margin: auto;
		padding: 2em;
		color: #4b0d82;
	}

	#highlight {
		color: #f58607;
	}

	#p-intro-end {

		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}

	#intro {
		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}
    /* all desktop styles */
@media (min-width: 1100px) {
    #text-wrapper {
        position: relative;
        font-family: 'Merriweather', serif;
    }

	.tion {
		animation: fadeIn 8s;
	}
	.bar {
		animation: blinkIn 1.5s steps(5, start) infinite;
	}

	@keyframes fadeIn {
		0% { opacity: 0; }
		100% { opacity: 1; }
		}

	@keyframes blinkIn {
	to {
		visibility: hidden;
	}
	}

	#headline {
        font-size: 4em;
		max-width: 50%;
		margin: auto;
		padding: 2em;
		color: #4b0d82;
	}

	#highlight {
		color: #f58607;
	}

	#p-intro-end {

		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}

	#intro {
		max-width: 50%;
		margin: auto;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}
}
</style>