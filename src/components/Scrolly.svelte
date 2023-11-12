<script>
	import ScrollyHelper from "./ScrollyHelper.svelte";
	import GoToDef from "./GoToDef.svelte";
    import RequestContainer from "./RequestContainer.svelte";
	import {onMount} from 'svelte'
	import anime from 'animejs';
    import '@fontsource/merriweather';
	
	// https://blog.hubspot.com/website/css-animate-on-scroll

	let value;


  onMount(() => {
		
			var animation = anime({
			targets:  '.requestBox',
			keyframes: [
				{translateX: 270},
				{rotateY: 180},
				{translateX: -27},
			],	
			delay: function(el, i) { return i * 300; },
			direction: 'normal',
			loop: false,
			autoplay: false,
			easing: 'easeInOutSine',
			duration: 4000
		});
		


	var animationGoToDefReq = anime({
        targets:  '.gotodef-params',
        keyframes: [
            {translateY: 150},
			{innerHTML: 'Location'},
            {translateY: -2},
        ],	
        delay: function(el, i) { return i * 400; },
        direction: 'normal',
        loop: true,
        autoplay: true,
        easing: 'easeInSine',
        duration: 4000,
		update: async function(){
				var obj = document.querySelector('.gotodef-params');
				return obj.innerHTML = obj.innerHTML.slice(0, obj.innerHTML.length - 2);
			
		}

});

document.querySelector('.request-controls .play').onclick = animation.play;
document.querySelector('.request-controls .pause').onclick = animation.pause;

document.querySelector('.play-gotodef').onclick = animationGoToDefReq.play;


const observer = new IntersectionObserver(entries => {
  // Loop over the entries
  entries.forEach(entry => {
    // If the element is visible
    if (entry.isIntersecting) {
      // Add the animation class
      entry.target.classList.add('animation');
    }
  });
});

observer.observe(document.querySelector('.image.image-1'));

});
</script>

<section id="scrolly" >
	<hr>
	<div class="spacer" />

	<ScrollyHelper bind:value>
		<figure>
			<p>Before the LSP, language developers faced an issue when it came to supporting different code editors. 
            </p>
            <spacer></spacer>
              <p> 
                The work (including writing type checkers and builders) involved in supporting features like 
               <span class="codespan">goToDefinition</span> and <span class="codespan">autocomplete</span> had to be repeated <i>per editor</i>. 
            </p>
			<div class="img-container">
				<img class="image image-2" src='assets/1stgraphwhitebg.svg' alt="imageofgraph" />
			</div>	
            <p>This means the work of supporting, say 3 languages in 3 editors is the work of 3x3.</p>
		</figure>

		<figure class='sticky'>

			<div class="img-container-2">
				<img class="image image-1" src="assets/2ndgraphwhitebg.svg" alt="1">
	
			</div>	
            <p>But once the unifying Language Server Protocol was introduced by Microsoft in 2015<a href="#footnote-1">[1]</a>, the work of developers to
                support 3 languages in 3 editors was reduced to 3x1!</p>
		</figure>
        <hr>
        <figure>
        <p>Ok, so what <i>is</i> the Language Server Protocol? Well, it uses <a href="https://www.jsonrpc.org/">JSON-RPC</a> to define a common protocol
        for code editors and language servers to interact with. These servers using the protocol can handle requests from each code editor, or client, asynchronously. 
        To see what that means, press 'play' on the animation below.</p>
            <RequestContainer/>
</figure>
	</ScrollyHelper>

	<div class="editorwindow">
		<div class="exit-btn">X</div>
	<span 
	data-text="goToDefinition" 
	class="tooltip"
  >variableName</span> = newValue;</div>

<div class="spacer"></div>

<GoToDef/>
	<div class="spacer" />

    <p id="footnote-1">[1] Running <span class="codespan">curl -X GET https://api.github.com/repos/microsoft/language-server-protocol</span> reveals <span class="codespan">"created_at": "2015-09-04T09:24:55Z"</span></p>
</section>

<style>

#footnote-1 {
    font-size: x-small;
}

.codespan {
    font-family: 'Courier New', Courier, monospace;
}

p {
    max-width: 40rem;
	margin: auto;
    color: #4b0d82;
}
#scrolly {
    font-family: 'Merriweather', serif;
    }

hr {
	width: 50vw;
	margin:0 auto;
	border: 1px solid #4b0d82;
}
.exit-btn {
	border: 2px solid black;
	height: 1.5em;
	width: 1.5em;
	margin-top: .5em;
	margin-left: .5em;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	font-weight: 200;
	border-radius: 2px;
	background-color: white;
}
.editorwindow {
	border: 2px solid black;
	border-radius: 2px;
	width: 50%;
	margin: auto;
	text-align: center;
	padding-bottom: 1em;
	font-family: 'Courier New', Courier, monospace;
	font-weight: 700;
	background-color: #edebf5;
}
.tooltip {
  position:relative; /* making the .tooltip span a container for the tooltip text */
  border-bottom:1px dashed #000; /* little indicater to indicate it's hoverable */
}

.tooltip:before {
  content: attr(data-text); /* here's the magic */
  position:absolute;
  
  /* vertically center */
  top:50%;
  transform:translateY(-50%);
  
  /* move to right */
  left:100%;
	margin-left: -2em;
  margin-top: -2em;
  
  /* basic styles */
  width:200px;
  padding:10px;
  border-radius:10px;
  background:#000;
  color: #fff;
  text-align:center;

  display:none; 
  /* hide by default */
}


.tooltip:hover:before {
  display:block;
}

/* source: https://blog.logrocket.com/creating-beautiful-tooltips-with-only-css/ */
	
	

.img-container-2 {
	align-content: center;

}

.image.image-2 {
	margin: auto;
	width: 80vw;
}

.image.image-1 {
	margin: auto;
	width: 80vw;
}



.spacer {
	margin-top: 4em;
	height: 25vh;
}

@keyframes fadeIn {
0% { opacity: 0; }
100% { opacity: 1; }
}

@keyframes fadeOut {
0% { opacity: 1; }
100% { opacity: 0; }
}
</style>
