<script>
	import GoToDef from "./GoToDef.svelte";
    import RequestContainer from "./RequestContainer.svelte";
	import {onMount} from 'svelte'
	import anime from 'animejs';
    import '@fontsource/merriweather';
    import ToolTip from "./ToolTip.svelte";
	
  
    

  onMount(() => {
    if (typeof window !== 'undefined') {
    var isMobile = window.innerWidth < 1024; 
			var animation = anime({
			targets:  '.requestBox',
			keyframes: [
				{translateX: isMobile ? 120 : 270},
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
            {translateY: 270},
			{innerHTML: 'Location'},
            {translateY: -1},
        ],	
        delay: function(el, i) { return i * 400; },
        direction: 'normal',
        loop: true,
        autoplay: true,
        easing: 'easeInSine',
        duration: 7000,
		update: async function(){
				var obj = document.querySelector('.gotodef-params');
				return obj.innerHTML = obj.innerHTML.slice(0, obj.innerHTML.length - 2);
			
		}

});

document.querySelector('.request-controls .play').onclick = animation.play;
document.querySelector('.request-controls .pause').onclick = animation.pause;
}
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

<section id="purpose-of-lsp" >
	<hr>
	<div class="spacer" />
		<figure>
			<p>Before the LSP, language developers faced an issue when it came to supporting different code editors. 
            </p>
            <spacer></spacer>
              <p> 
                The work (including writing type checkers and builders) involved in supporting features like 
               <span class="codespan">goToDefinition</span> and <span class="codespan">autocomplete</span> had to be repeated <i>per editor</i>. 
            </p>
				<img class="image image-2" src='assets/1stgraphwhitebg.svg' alt="imageofgraph" />
            <p>This means the work of supporting, say 3 languages in 3 editors is the work of 3x3.</p>
		</figure>

		<figure class='sticky'>
				<img class="image image-1" src="assets/2ndgraphwhitebg.svg" alt="1">
            <p>But once the unifying Language Server Protocol was introduced by Microsoft in 2015<a href="#footnote-1">[1]</a>, the work of developers to
                support 3 languages in 3 editors was reduced to 3x1!</p>
		</figure>
        <hr id="mid-hr">
    </section>
<section id="what-is-an-lsp">
        <figure>
        <p>Ok, so what <i>is</i> the Language Server Protocol? Well, it uses <a href="https://www.jsonrpc.org/">JSON-RPC</a> to define a common protocol
        for code editors and language servers to interact with. </p> 

        <p> These servers using the protocol can handle requests from each code editor, or client, asynchronously. 
        To see what that means, press 'send' on the animation below.</p>
            <RequestContainer/>
</figure>
<figure>
    <p>So what happens, say, when you hover over a <span class="codespan">variableName</span> and click <span class="codespan">goToDefinition</span>?</p>
    <ToolTip/>
</figure>
</section>
<section id="server-requests">

    <h3>Server Requests</h3>
    <p>When you click on <span class="codespan">goToDefinition</span> you trigger a request from the editor, the client, to the server.
        This request is for the<span class="codespans">textDocument/definition</span> 
        and includes the parameters <span class="codespan">{'{documentURI, position}'}</span>.
    </p>
    <p>The server then responds with the <span class="codespan">Location</span> of the definition, so the client can send you there.</p>
    <p>(And because it can handle these requests async, it can handle multiple requests at once.)</p>
    <GoToDef/>
<p>In this way, the Language Server Protocol handles requests from code editors to support features for different languages in each client.</p>

</section>
<section id="resources">
   
    <h3 id="h3-resources">Resources</h3>
<figure>
    <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" id="blob">
        <path fill="#f58607" d="M29.6,-43.5C39.8,-39.4,50.6,-33.7,55.4,-24.8C60.3,-15.9,59.2,-3.8,55.8,6.8C52.3,17.4,46.6,26.4,39.3,33.3C32.1,40.1,23.3,44.9,13.5,49.1C3.7,53.4,-7.1,57.2,-17,55.4C-26.8,53.6,-35.8,46.1,-47.7,38.1C-59.7,30.1,-74.6,21.5,-74.9,11.5C-75.2,1.5,-60.7,-9.8,-50.3,-18.9C-39.9,-28.1,-33.4,-35,-25.7,-40.3C-18,-45.6,-9,-49.1,0.3,-49.7C9.7,-50.2,19.3,-47.7,29.6,-43.5Z" transform="translate(100 100)" />
      </svg>

    <p>This page has provided a high-level overview -- it's definitely the very tip of the iceberg, even conceptually.
        Here are some resources to help you dive deeper.
    </p>
    <h4>Official Documents</h4>
    <ul>
        <li><a href="https://microsoft.github.io/language-server-protocol/">Language Server Protocol</a>- Microsoft's Guide</li>
        <li><a href="https://langserver.org/">Langserver.org</a>- A list of languages and their features supported in the LSP.</li>
    </ul>
    <h4>Tutorials</h4>
    <ul>
        <li><a href="https://www.toptal.com/javascript/language-server-protocol-tutorial">Language Servers in Text Editors | Toptal</a></li>
        <li><a href="https://tomassetti.me/go-to-definition-in-the-language-server-protocol/">Go To Definition in the Language Server Protocol| Strumenta</a></li>
        <li><a href="https://learn.microsoft.com/en-us/visualstudio/extensibility/adding-an-lsp-extension?view=vs-2019">Adding a Language Server Extension</a></li>
    </ul>
</figure>
</section>
<section id="about-the-author">
<figure>
    <h3 id="about-h3">About the author</h3>
    <div id="author-container">
    <img src="https://avatars.githubusercontent.com/u/54046179?v=4" alt="Lucia Cerchie's headshot" id="headshot">
    <p id="about-para">Lucia Cerchie is a developer experience professional who loves to learn in public.
        You can find more of her content on her <a href="https://github.com/Cerchie">Github page</a> and her <a href="https://luciacerchie.dev/blog">blog</a>.
   Reach out via <a href="https://www.linkedin.com/in/luciacerchie">LinkedIn</a>.</p>
    </div>
</figure>
</section>
<section id="footnotes">
    <p id="footnote-1">[1] Footnote: Running <span class="codespan">curl -X GET https://api.github.com/repos/microsoft/language-server-protocol</span> reveals <span class="codespan">"created_at": "2015-09-04T09:24:55Z"</span></p>
</section>


<style>
    /* all mobile styles */
#about-h3 {
    margin-left: .5em;
    white-space: nowrap;
}
#author-container {
    padding: 20px;


}
#about-the-author {
margin-top: 90px;

}

#headshot {
display: none;
    
}

#footnote-1 {
    margin-top: 10em;
    margin-left: 1em;
    font-size: large;
    width: 90%;
    word-wrap: break-word;
}
#resources {
   
    margin-top: 12em;
}
.codespan {
    font-family: 'Courier New', Courier, monospace;
}

#blob {
display: none;
}

#mid-hr {
    margin: auto;
    margin-top: 5em;
    margin-bottom: 5em;
}
h3 {
    max-width: 100%;
	margin: auto;
    margin-left: -.3em;
    z-index: 10;
    color: #130c61;
    font-size: xx-large;
}
ul {
    margin: auto;
    width: 90%;
    color: #130c61;
    text-decoration: none;
    font-size: large;
}

li {
    margin-top: 1em;
}
p {
    width: 90vw;
	margin: auto;
    font-size: large;
    margin-top: 1em;
    margin-left: -.5em;
    color: #130c61;
}
section {
    font-family: 'Merriweather', serif;
    }

hr {
	width: 50vw;
	margin:0 auto;
	border: 1px solid #4b0d82;
}

h4 {
    font-size: x-large;
    margin: auto;
    margin-bottom: 1em;
    margin-left: 1em;
    width: 50%;
    margin-top: 4em;
    color: #130c61;
}

.image.image-2 {
    display: block;
  margin-left: -2em;
  margin-right: auto;
  width: 100vw;
}

.image.image-1 {
    display: block;
    margin-left: -2em;
  margin-right: auto;
  width: 100vw;
}

#h3-resources {
    margin-left: .9em;
}

.spacer {
	height: 5vh;
}

@keyframes fadeIn {
0% { opacity: 0; }
100% { opacity: 1; }
}

@keyframes fadeOut {
0% { opacity: 1; }
100% { opacity: 0; }
}

#server-requests {
    width: 80vw;
	margin: auto;
    margin-left: 2em;
}
/* all desktop styles */
@media (min-width: 1100px) {

#author-container {
    padding: 20px;;
    display:flex;
    justify-content: space-around;
}
#about-the-author {
    margin-top: 200px;
    margin-left: 200px;
}

#about-h3 {
    margin-left: 90px;
}
#about-para {
    margin-left: 10px;
}
#headshot {
    display:block;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    margin: 30px;
    
}

#footnote-1 {
    margin-top: 20em;
    font-size: large;
}
#resources {
   
    margin-top: 12em;
}
.codespan {
    font-family: 'Courier New', Courier, monospace;
}

#blob {
    display: block;
    position: absolute;
    width: 250px;
    z-index: -10;
    margin-top: -12em;
    margin-left: 10em;

    transform: rotate(50deg);
    opacity: 50%;
}

#mid-hr {
    margin: auto;
    margin-top: 5em;
    margin-bottom: 5em;
}
h3 {
    max-width: 50%;
	margin: auto;
    z-index: 10;
    color: #130c61;
    font-size: 3em;
}
ul {
    margin: auto;
    width: 50%;
    color: #130c61;
    text-decoration: none;
    font-size: 1.75em;
}

li {
    margin-top: 1em;
}
p {
    max-width: 50%;
	margin: auto;
    font-size: 2em;
    margin-top: 1em;
    color: #130c61;
}
section {
    font-family: 'Merriweather', serif;
    }

    #h3-resources {
    margin-left: 6em;
}


hr {
	width: 50vw;
	margin:0 auto;
	border: 1px solid #4b0d82;
}

h4 {
    font-size: 2em;
    margin: auto;
    margin-bottom: 1em;
    width: 50%;
    margin-top: 4em;
    color: #130c61;
}

.image.image-2 {
    display: block;
  margin-left: auto;
  margin-right: auto;
  width: 70%;
}

.image.image-1 {
    display: block;
  margin-left: auto;
  margin-right: auto;
  width: 70%;
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
}
</style>
