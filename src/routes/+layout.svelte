<script lang="ts">
	let { children } = $props();
	import "../app.css";
	import "../fonts.css";
</script>

<nav>
	<a href="/">Home</a>
	<a href="/about">How to play</a>
	<a href="/settings">Setting</a>
</nav>

{@render children()}

<style>
	:global(body) {
		font-family: "Satoshi-Regular", sans-serif;
	}

	nav {
		display: flex;
		justify-content: center;
		margin-bottom: 1rem;
	}

	nav a {
		margin: 0 1rem;
	}

	nav a[href] {
		text-decoration: none;
		color: #ededed;
	}

	nav a[href]:hover {
		color: #00995e;
	}

</style>