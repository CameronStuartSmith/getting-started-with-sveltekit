<script>
	// Global SCSS file to style the whole app
	import '../global.scss';
	// The PostCSS file that imports all of the tailwind stuff, created by the svelte-add/tailwind command
	import '../app.postcss';
	import { page } from '$app/stores';

	const routes = [
		{ href: '/', name: 'Home' },
		{ href: '/about', name: 'About' },
		{ href: '/about/products', name: 'About Our Products' },
		{ href: '/contact', name: 'Contact Us' }
	];
</script>

<nav class="border-b border-gray-400 p-3">
	{#each routes as route}
		<a
			href={route.href}
			class="underline px-2"
			class:text-blue-300={route.href !== $page.path}
			class:text-gray-400={route.href === $page.path}>{route.name}</a
		>
	{/each}
</nav>

<!-- This is where the page will be rendered -->
<slot />

<footer>I am the footer</footer>
