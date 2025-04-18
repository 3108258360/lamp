<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Tungsten Halogen - Single Ended",
					description: [
						"The Single-Ended family of halogen lamps was developed to permit a reduction in dimensions vs the original Double-Ended versions. Not only does this permit more compact lamps and luminaires, it allows a reduction in the dimensions of the filament size which may bring optical benefits in many applications. The cost of the lamps and resulting systems is also slightly lower, owing to the requirement to produce only one seal during lamp manufacture, and only one lampholder is needed. Some additional types of single ended lamps may be found under the page detailing Special Lamps."
					]
				},
				{
					subhead: "Low Voltage Capsules",
					intros: [
						["GEC", "100W", "First Single Ended Halogen Capsule A1/215", "1966"],
						["Mazda", "50W", "First Low Volt Halogen for Spotlighting M/32", "1969"]
					],
					pictures: [
						"/t TH SE LV Q100T10C-12 A1-215 GEC.jpg",
						"/t TH SE LV Q50T10C-GY6.35-12V Mazda.jpg"
					]
				},
				{
					subhead: "High Voltage Capsules",
					intros: [["Osram", "60W", "Halopin Mains Volt G9 capsule of first design", "2005"]],
					pictures: ["/t TH SE HV Q60T12C-G9-230 Osram.jpg"]
				}
			],
			viewFullImage: "View Full Image",
			close: "Close",
			returnHome: "Home",
			contents: "Cont"
		},
		zh: {
			boxes: [
				{
					title: "钨丝卤素-单端",
					description: [
						"单端卤素灯系列是为了与最初的双端版本相比减小尺寸而开发的。这不仅允许制造更紧凑的灯和灯具，还可以减小灯丝尺寸，这在许多应用中可能带来光学优势。由于在灯的制造过程中只需要制作一个密封，并且只需要一个灯座，因此灯和相应系统的成本也略有降低。在详细介绍特种灯的页面中，还可以找到一些额外类型的单端灯。"
					]
				},
				{
					subhead: "低压胶囊",
					intros: [
						["GEC", "100W", "First Single Ended Halogen Capsule A1/215", "1966"],
						["Mazda", "50W", "First Low Volt Halogen for Spotlighting M/32", "1969"]
					],
					pictures: [
						"/t TH SE LV Q100T10C-12 A1-215 GEC.jpg",
						"/t TH SE LV Q50T10C-GY6.35-12V Mazda.jpg"
					]
				},
				{
					subhead: "高压胶囊",
					intros: [["Osram", "60W", "Halopin Mains Volt G9 capsule of first design", "2005"]],
					pictures: ["/t TH SE HV Q60T12C-G9-230 Osram.jpg"]
				}
			],
			viewFullImage: "查看原图",
			close: "退出",
			returnHome: "首页",
			contents: "目录"
		}
	};
	type Language = "zh" | "en";
	let language: Language = "en";
	let showContents = false;

	onMount(() => {
		language = (localStorage.getItem("language") as Language) || "en";
		if (!translations[language]) {
			language = "en";
		}
	});
</script>

<TranslationBox {translations} {language} {showContents} />
<button on:click={() => goto("/")} class="return-home">{translations[language].returnHome}</button>
<button
	on:click={() => {
		showContents = !showContents;
	}}
	class="show-contents">{translations[language].contents}</button
>
