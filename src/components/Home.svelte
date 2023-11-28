<script>
	import Scrolly from "./Scrolly.svelte";
    import '@fontsource/merriweather';
</script>

<div>
    <div id="secret-message">Hey there! Thanks for checking out my page. If you'd like to chat, email me at luciacerchie at gmail dot com.</div>
<div id="text-wrapper"> 
	<h1 id="headline">The Language Server Protocol</h1>
	<p id="intro">Code editors these days come with some fancy schmancy features like code comple<span class="tion">tion</span><span class="bar">|</span>, syntax <b id="highlight">highlighting</b>, and refactoring routines.</p>

	<p id="p-intro-end">How do language developers support these features? Let's find out.</p>
</div>
	<Scrolly />
</div>

<style>
    /* all mobile styles */
#secret-message {
    display: none;
}
    #text-wrapper {
        position: relative;
        font-family: 'Merriweather', serif;
        max-width: 100%;
        width: 100px;
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
        font-size: xxx-large;
		margin: auto;
        margin-left: -1.5em;
		padding: 2em;
		color: #4b0d82;
	}

	#highlight {
		color: #E96A01;
	}



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



	#highlight {
		color: #f58607;
	}

	#p-intro-end {
		width: 90vw;
		margin: auto;
        margin-left: 1em;
		color: #4b0d82;
		font-size: 1.5em;
        margin-bottom: 2em;
	}

	#intro {
		width: 90vw;
		margin-left: 1em;

		color: #4b0d82;
		font-size: 1.5em;
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
		margin: auto;
        margin-left: .5em;
		color: #4b0d82;
	}

	#highlight {
		color: #f58607;
	}

	#p-intro-end {
		margin: auto;
        margin-left: 4em;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}

	#intro {
		margin: auto;
        margin-left: 4em;
		padding: 1em;
		color: #4b0d82;
		font-size: 2em;
	}
}
</style>