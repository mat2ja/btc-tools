<script lang="ts">
	import type { Lang } from '$lib/models/bip39';

	export let wordlists: Record<string, string[]>;
	export let lang: Lang = 'en';

	const setLang = (_lang: Lang) => {
		lang = _lang;
	};

	let languages = Object.keys(wordlists).sort() as Lang[];
</script>

<div class="flex flex-wrap items-center justify-end gap-1  text-neutral-50/20">
	{#each languages as $lang}
		<button
			aria-label="Set language to {$lang}"
			on:click={() => setLang($lang)}
			class:!text-neutral-300={lang === $lang}
			class="rounded-md p-1 ring-orange-500 hover:text-neutral-500 focus:outline-none focus-visible:text-neutral-400 focus-visible:ring-2"
		>
			{$lang}
		</button>
	{/each}
</div>
