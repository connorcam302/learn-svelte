<script lang="ts">
	import BossTile from '$lib/boss.svelte';

	type bossType = {
		name: string;
		totalDeaths: number;
		userDeaths: number;
		avgDeaths: number;
		img: string;
	};

	let bosses: bossType[] = [
		{
			name: 'Abyss Watchers',
			totalDeaths: 85,
			userDeaths: 1,
			avgDeaths: 17,
			img: 'abyss-watchers'
		},
		{
			name: 'Pontiff Sulyvahn',
			totalDeaths: 156,
			userDeaths: 5,
			avgDeaths: 31.2,
			img: 'pontiff-sulyvahn'
		},
		{
			name: 'Champion Gundyr',
			totalDeaths: 50,
			userDeaths: 3,
			avgDeaths: 10,
			img: 'champion-gundyr'
		},
		{
			name: 'Sister Friede',
			totalDeaths: 51,
			userDeaths: 0,
			avgDeaths: 10.2,
			img: 'sister-friede'
		},
		{
			name: 'Nameless King',
			totalDeaths: 81,
			userDeaths: 8,
			avgDeaths: 16.2,
			img: 'nameless-king'
		},
		{
			name: 'Dragonslayer Armour',
			totalDeaths: 30,
			userDeaths: 0,
			avgDeaths: 5,
			img: 'dragonslayer-armour'
		}
	];
</script>

<div class="mx-auto flex flex-wrap items-center justify-center gap-10">
	{#each bosses as boss}
		<BossTile {boss} />
	{/each}
</div>
