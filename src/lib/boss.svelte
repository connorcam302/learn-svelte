<script lang="ts">
	type bossType = {
		name: string;
		totalDeaths: number;
		userDeaths: number;
		avgDeaths: number;
		img: string;
	};

	function addDeath(boss: bossType) {
		console.log(boss);
		boss.userDeaths += 1;
		boss.totalDeaths += 1;
		return boss;
	}

	export let boss: bossType;
</script>

<div class="gap-10 text-center">
	<div class="flex h-52 w-52 items-center justify-center">
		<img class="max-h-full max-w-full" src={`/${boss.img}.png`} alt={boss.name} />
	</div>
	<div class="text-lg">{boss.name}</div>
	<div>{boss.userDeaths} Deaths</div>
	<button
		class="m-3 rounded bg-amber-300 px-2 py-1 font-bold text-stone-800 transition-all duration-200 hover:bg-amber-400 hover:text-red-800"
		on:click={() => (boss = addDeath(boss))}>Add Death</button
	>
</div>
