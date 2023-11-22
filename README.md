# [What Is The Language Server Protocol?](https://what-is-the-lsp.netlify.app/) 

I built this website for two purposes:

1. to share my interest in [the LSP](https://microsoft.github.io/language-server-protocol/) with others
2. to hone my frontend skills, specifically in CSS and animation 

If you want to learn more about the LSP start here: https://what-is-the-lsp.netlify.app/

If you want to know what I learned by creating this site, read on. 

## svelte.js

PLACEHOLDER

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

https://github.com/juliangarnier/anime/issues/870

## CSS
PLACEHOLDER
