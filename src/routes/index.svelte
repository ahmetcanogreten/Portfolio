<script lang="ts">
	let myPosts = [
		{
			title: 'What and Why Flutter ?',
			excerpt:
				'Flutter is a cross-platform development framework. That is, it will allow us to create applications from a single code base. We will write the code independently from any platform, and Flutter will write platform dependent code for us.',
			url: 'https://medium.com/@ogretenahmetcan/what-and-why-flutter-b6f72610fbec',
			image_url: 'https://miro.medium.com/max/700/1*C_LBwlCDposw1vi_1kXkyw.png',
			image_alt: 'Flutter Icon'
		}
	];
</script>

<main class="w-4/5 mx-auto mt-16 max-w-screen-xl">
	{#each myPosts as myPost}
		<div class="border-2 p-4 rounded-lg shadow-md hover:shadow-2xl m-8">
			<a href={myPost.url}>
				<img class="mx-auto m-8" src={myPost.image_url} alt={myPost.image_alt} />
				<h2 class="m-8 text-2xl">{myPost.title}</h2>
				<p class="text-md m-8">{myPost.excerpt}</p>
			</a>
		</div>
	{/each}
</main>
