<script lang="ts">
	type bossType = {
		name: string;
		totalDeaths: number;
		userDeaths: number;
		avgDeaths: number;
	};

	function addDeath(boss: bossType) {
		console.log(boss);
		boss.userDeaths += 1;
		boss.totalDeaths += 1;
		return boss;
	}

	let abysswatchers: bossType = {
		name: 'Abyss Watchers',
		totalDeaths: 85,
		userDeaths: 0,
		avgDeaths: 17
	};
	let bosses: bossType[] = [
		{
			name: 'Abyss Watchers',
			totalDeaths: 85,
			userDeaths: 1,
			avgDeaths: 17
		},
		{
			name: 'Pontiff Sulyvahn',
			totalDeaths: 156,
			userDeaths: 5,
			avgDeaths: 31.2
		},
		{
			name: 'Champion Gundyr',
			totalDeaths: 50,
			userDeaths: 3,
			avgDeaths: 10
		}
	];
</script>

<div class="mx-auto flex w-fit flex-col gap-10">
	{#each bosses as boss}
		<div class="text-center">
			<div class="text-lg">{boss.name}</div>
			<div>{boss.userDeaths} Deaths</div>
			<button
				class="rounded bg-amber-300 px-2 py-1 font-bold text-white transition-all duration-200 hover:bg-amber-400"
				on:click={() => (boss = addDeath(boss))}>Add Death</button
			>
		</div>
	{/each}
</div>
