<script lang="ts">
	import { onMount } from "svelte";
	type Language = "en" | "zh";
	let language: Language = "zh";
	let buttonText: string;

	const texts = {
		en: {
			title: "Welcome to the Museum of Electric Lamp Technology",
			description: [
				"The first artificial electric light was demonstrated during 1802 in London, by Sir Humphry Davy at the Royal Institution of Great Britain. It was the carbon arc discharge lamp, and since then the electric discharge has been intensely researched and developed for one fundamental reason - that it creates light from electricity more efficiently than any other kind of artificial light source.",
				"Over time it was learned that the discharge could be made to generate light more efficiently by arranging that it took place inside a rare gas instead of through the air. This led to the creation of gaseous discharge lamps which frequently make use of the noble gases helium, neon, argon, krypton or xenon. Carbon dioxide was also of considerable interest owing to its white light output.",
				"During the later parts of the nineteenth and  early twentieth centuries, developments in discharge lamps took a back seat whilst efforts were focussed  on the development of an incandescent lamp. Although the arc was very efficient by comparison with other sources of its time, it was intensely bright and mainly suited to outdoor illumination. Small oil and gas burners continued to dominate indoors and to coin a phrase of Sir Joseph Swan, it was recognised that efforts should be made to 'subdivide the electric light', such that it could be made in smaller lumen packages for the mass market of indoor lighting.",
				"There were numerous contributors, but the first men to achieve practical success with commercially viable lamps were Sir Joseph Swan in England, and Thomas Edison in America, who quite independently invented the carbon filament incandescent lamp in 1878. Numerous changes have taken place over the years in search of better filament materials yielding increased efficacy and longer life. In addition, developments in halogen chemistry have realised smaller, longer lived and still more efficient lamps, and optical innovations have played an important role in efficiently creating beams of usable light.",
				"In the 1930s attention returned to the discharge lamps, this time employing metallic vapours instead of the former gaseous fillings. Sodium and mercury were initially employed on account of their high vapour pressures and desirable emission in the visible spectrum, but their light colours are not white.  The combination of luminescent materials with the mercury discharge has led to tremendous progress in the field of fluorescent lighting, and since the 1950s the colour properties of the discharge itself were improved by the introduction of other elements in the form of metal halide salts.",
				"In more recent years, a  new category of solid-state light sources is emerging in the form of Light Emitting Diodes and their Organic counterparts, which are having an equally profound effect on the lighting market. In addition to general illumination with white light, their potential to create saturated colours with high efficacy has opened up entirely new areas in decorative lighting.",
				"This website traces the development of the materials, science and technology behind electric light sources from their earliest beginnings right up to the present day. Where possible, these developments are illustrated with examples of historic lamps. Please follow the links on the left to choose a particular family of light source. Clicking on the category title will reveal technical information regarding the development of that style of light source. Choosing individual sub-category headings will bring up a page illustrating that technology with historic examples of the same."
			],

			buttonText: "中文"
		},
		zh: {
			title: "欢迎来到本站",
			description: ["本站花费了大量时间来整理和翻译，致力于提供一个优秀的灯泡科普平台，"],
			buttonText: "English"
		}
	} as const;

	function updateLanguage(lang: Language) {
		language = lang;
		localStorage.setItem("language", language);
		buttonText = texts[language].buttonText;
	}

	onMount(() => {
		const savedLanguage = localStorage.getItem("language") as Language;
		if (savedLanguage) {
			updateLanguage(savedLanguage);
		} else {
			updateLanguage("zh");
		}
	});

	function toggleLanguage() {
		updateLanguage(language === "en" ? "zh" : "en");
	}

	$: text = texts[language];
</script>

<button on:click={toggleLanguage} style="position:fixed; top: 20px; right: 20px;">
	{buttonText}
</button>
<div class="box">
	<h1>{text.title}</h1>
	{#each text.description as descriptionItem}
		<p>{descriptionItem}</p>
	{/each}
</div>
