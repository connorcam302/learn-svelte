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

	function removeDeath(boss: bossType) {
		console.log(boss);
		boss.userDeaths -= 1;
		boss.totalDeaths -= 1;
		return boss;
	}

	export let boss: bossType;
</script>

<div class="flex flex-col gap-4 text-center text-lg">
	<div class="mx-auto h-72 w-72">
		<img class="block h-full w-full object-cover" src={`/${boss.img}.png`} alt={boss.name} />
	</div>
	<div class="text-lg">{boss.name}</div>
	<div class="mx-auto flex flex-wrap">
		<button
			class="rounded-l-lg bg-amber-300 px-3 py-1 font-bold text-stone-800 transition-all duration-200 hover:bg-amber-400 hover:text-red-800"
			on:click={() => (boss = removeDeath(boss))}>-</button
		>
		<div class="leading-1 bg-amber-300 px-3 font-black text-stone-800">
			{boss.userDeaths} Deaths
		</div>
		<button
			class="rounded-r-lg bg-amber-300 px-3 text-2xl font-bold text-stone-800 transition-all duration-200 hover:bg-amber-400 hover:text-red-800"
			on:click={() => (boss = addDeath(boss))}>+</button
		>
	</div>
</div>
