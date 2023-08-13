<script lang="ts">
	import BossTile from '$lib/boss.svelte';
	import bossesJson from '$lib/ds3-bosses.json';

	type bossType = {
		name: string;
		totalDeaths: number;
		userDeaths: number;
		avgDeaths: number;
		img: string;
	};

	let bosses: bossType[] = bossesJson;

	let currentBoss = bosses[bosses.length - 1];

	let setBoss = (boss: bossType) => {
		currentBoss = boss;
	};
</script>

<div class="mx-auto flex min-h-screen w-6/12 bg-stone-700">
	<div class="flex flex-col text-left">
		{#each bosses as boss}
			<button class="w-52 px-2 py-1 text-left leading-5" on:click={() => setBoss(boss)}
				>{boss.name}</button
			>
		{/each}
	</div>
	<div class="mx-auto">
		<BossTile bind:boss={currentBoss} />
	</div>
</div>
