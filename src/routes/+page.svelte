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

<div class="w-full font-bold">
	{#each bosses as boss}
		<div class="">
			<h3>{boss.name}</h3>
			<h4>{boss.userDeaths}</h4>
			<button on:click={() => (boss = addDeath(boss))}>Add Death</button>
		</div>
	{/each}
</div>
