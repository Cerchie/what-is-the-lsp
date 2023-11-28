<script>
	export let title = "What is the LSP?";
	export let description = "A scrollytale describing why the LSP exists and how it works.";
	export let url = "https://whatisthelsp.com";
	export let keywords = ["LSP", "what is the lsp", "language server protocol"];
	export let preloadFont = [];
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />
	<meta name="author" content="Lucia Cerchie" />
	<meta name="news_keywords" content={keywords} />

	<meta property="og:title" content={title} />
	<meta property="og:site_name" content="What Is An LSP?" />
	<meta property="og:url" content={url} />
	<meta property="og:description" content={description} />
	<meta property="og:type" content="article" />
	<meta property="og:locale" content="en_US" />

	<meta property="og:image" content="{url}/assets/2ndgraphwhitebg.png" />
	<meta property="og:image:type" content="image/png" />
	<meta property="og:image:width" content="1200" />
	<meta property="og:image:height" content="600" />

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="https://whatisthelsp.com" />
	<meta name="twitter:creator" content="@CerchieLucia" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:image:src" content="..static/assets/social.png" />

	<link rel="canonical" href="{url}/" />

	{#each preloadFont as href}
		<link rel="preload" {href} as="font" type="font/woff2" crossorigin />
	{/each}
</svelte:head>