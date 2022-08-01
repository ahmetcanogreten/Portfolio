<script lang="ts">
	import '../app.css';
	import { page } from '$app/stores';

	$: isOnThisPage = (path: string): boolean => {
		return $page.url.pathname === path;
	};
</script>

<header class="grid grid-cols-12 gap-4">
	<img
		class="col-start-2 col-span-10 mx-auto mt-2 rounded-xl shadow-lg p-1"
		src="/to-space.jpg"
		alt="A man looking through the space"
	/>
	<nav
		class="col-start-4 col-span-6 mt-2 p-2 text-4xl flex justify-evenly border-t-2 border-b-2 border-gray-300"
	>
		<a
			href="/about"
			class="p-2 {isOnThisPage('/about')
				? 'bg-black text-white'
				: 'text-black hover:bg-black hover:text-white'}">Who Am I</a
		>
		<a
			href="/"
			class="p-2 {isOnThisPage('/')
				? 'bg-black text-white'
				: 'text-black hover:bg-black hover:text-white'}">My Posts</a
		>
		<a
			href="/my-projects"
			class="p-2 {isOnThisPage('/my-projects')
				? 'bg-black text-white'
				: 'text-black hover:bg-black hover:text-white'}">My Projects</a
		>
	</nav>
</header>

<slot />
