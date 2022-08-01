<script lang="ts">
	const getMyRepos = async () => {
		const response = await fetch('https://api.github.com/users/ahmetcanogreten/repos');
		const data = await response.json();
		return data;
	};

	let myRepos = getMyRepos();
</script>

<main class="w-4/5 mx-auto mt-16 max-w-screen-xl grid grid-cols-2">
	{#await myRepos then myFetchedRepos}
		{#each myFetchedRepos as myRepo}
			<div class="border-2 p-4 rounded-lg shadow-md hover:shadow-lg m-8 ">
				<a href={myRepo.html_url}>
					<img
						src={`${myRepo.html_url}/blob/${myRepo.default_branch}/COVER.png?raw=true`}
						alt="Repo cover"
					/>
					<h2 class="text-2xl text-center m-4">{myRepo.name}</h2>
					<p>{myRepo.description}</p>
				</a>
			</div>
		{/each}
	{/await}
</main>
