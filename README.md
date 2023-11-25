# What I Learned By Building An Educational Static Site

I built this website for two purposes:

1. to share my interest in [the LSP](https://microsoft.github.io/language-server-protocol/) with others
2. to hone my frontend skills, specifically in CSS and animation 

If you want to learn more about the LSP start here: [https://what-is-the-lsp.netlify.app/](https://what-is-the-lsp.netlify.app/)

If you want to know some of what I learned by creating this site, read on. 

## svelte.js

I stumbled onto using svelte.js by accident. Originally, I was going to use parallax scroll and use a [Pudding template](https://github.com/the-pudding/svelte-starter) for that, which just happened to use svelte.js. I didn't end up using the main functionality in the starter, but I did end up sticking with svelte because I thought it was an interesting frontend framework and a good learning opportunity -- technically all this project required was JS+CSS but then again, learning new things was part of my goal. 

One of the main things I learned was that svelte.js uses [bind directives](https://svelte.dev/docs/element-directives#bind-property) to send information from child to parent element. Hence, I have some refactoring to do later. In `Scrolly.svelte` I use the document object to access an element so I can implement anime.js:

```
document.querySelector('.request-controls .play').onclick = animation.play;
```

But this isn't very 'svelte-y' because I could using a binding-- maybe something like `click:` if not a bind directive itself. Todo!

A gotcha in svelte: I had trouble at first though because in svelte, the JS functions you write are within the <script> tag, and that's not executed on mount so it might not run if you don't have the function execution tied to a user event-- you have to use the `onMount` [svelte function](https://svelte.dev/docs/svelte#onmount) to avoid this issue.

## anime.js

[anime.js](https://animejs.com/) is a JavaScript library that enables you to animate DOM elements. Typically, you feed the API a 'target' and then specify the movement from there:

```
anime({
  targets: '.element-classname',
  translateX: 990,
  duration: 4000
});
```

I ended up using a couple sets of [keyframes](https://animejs.com/documentation/#animationKeyframes) to animate elements, so I could lay out the animation in steps. 

I also used [Play/Pause](https://animejs.com/documentation/#playPause) controls. I chose them for two reasons. First, because when the user controls the motion, it is more accessible to users who prefer reduced motion (I have yet to implement the `prefers-reduced-motion` CSS query for the last animation I've used, but I should for the same reason). The second reason was because I wanted to give the user the ability to pause the motion to let the concept of asynchronicity sink in. You can see what I mean in [this section](https://what-is-the-lsp.netlify.app/#what-is-an-lsp).

I ran into an issue when animating the `goToDefinition` server request. I wanted to change the text on the parameter to go from `Location` to `Document URI, Position`. 

<img width="350" alt="Screenshot 2023-11-22 at 1 40 48 PM" src="https://github.com/Cerchie/what-is-the-lsp/assets/54046179/fd7c767d-9059-41b2-ac93-eea49df18d63">
<img width="382" alt="Screenshot 2023-11-22 at 1 41 10 PM" src="https://github.com/Cerchie/what-is-the-lsp/assets/54046179/0c4ef4fd-cce3-4656-abae-c47aacdeced3">


I'd do this by using keyframes and changing the innerHTML:


```
	var animationGoToDefReq = anime({
        targets:  '.gotodef-params',
        keyframes: [
            {translateY: 270},
			{innerHTML: 'Location'},
            {translateY: -1},
        ],	
```

Unfortunately, in V3 of anime.js this is not supported-- it adds a 0 to the end of every piece of HTML because it expects a number and 0 is the default. This [will be fixed in V4](https://github.com/juliangarnier/anime/issues/870). 



## CSS

I learned _so much_ about CSS for this! I've been taking Josh W. Comeau's course [CSS for JS Devs](https://css-for-js.dev/), and I'm only halfway through, but I'm no longer scared of CSS. 🤯

Basically, I didn't know before that CSS has different [layout algorithms](https://www.joshwcomeau.com/css/understanding-layout-algorithms/). Once you learn how those algorithms (flexbox, position, grid, table, flow) work, the mystery and confusion surrounding CSS dissipates.

For this particular project, I used a flexbox layout algo for my 'about the author' section:

```
#author-container {
    padding: 20px;;
    display:flex;
    justify-content: space-around;
}
```
I used it because I wanted the elements to be surrounded by space and oriented around the main axis. 

For the rest, I mainly used _positioned_ layout. If you want to learn more about these algorithms, [this blog post](https://www.joshwcomeau.com/css/understanding-layout-algorithms/) by Josh would be a great start. 

## Conclusion

These are just some tidbits and notes on what I've learned. I've got more to learn, including:

- implementing 'prefers reduced motion'
- finding a way to generate a scrollytelling template for my own purposes using ChatGPT
- the other CSS algos besides positioned and flexbox
- working my svelte.js muscles and making working in the bindings natural to me

But I've learned a few broader things along the way about creating static sites and animation. I've learned that animation design is a complex process that involves taking away more animation than you'd think (it was super hard deciding what movements were really necessary when it comes to educating readers on the concepts I wanted to teach, and which movement were just 'flair'). I've learned that user event-based coding isn't just limited to React. I've learned that it's easier to set up the design of your SPA (single page web app) at the beginning rather than having to go painstakingly back over the CSS alignment because you built stuff incrementally and it's now all wonky. Hopefully these lessons stick with me. :) 


