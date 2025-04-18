<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent - Reflector Lamps",
					description: [
						"Although the first incandescent lamps having reflector-shaped bulbs were created in the 1890s, the available technologies for the production of reflective coatings, as well as the understanding of optics and correct profiling of the reflector surface, made the early lamps quite ineffective and they were rarely used. The modern generation of reflector lamps did not emerge until the 1930s when a new technique for creating mirror coatings was developed, combined with the parallel introduction of scientifically-designed bulb shapes to optimise the optical performance. Later developments in glass forming processes enabled a significant performance increase with the introduction of pressing instead of blow-moulding techniques. Some of the key steps in the evolution of reflector incandescent lamps are featured on this page."
					]
				},
				{
					subhead: "Blown Reflector",
					intros: [
						["GE", "1000W", "High Wattage lamp with Compound Reflector", "~1955"],
						["Atlas", "50W", "Low Voltage Display - Parabolic Diffuse", "1970"],
						["Sylvania", "75W", "Ellipsoidal Reflector for European market", "~1985"],
						["GE", "45W", "Miser BR30 Improved Double Reflector", "1994"],
						["Philips", "40W", "Spotline NR60 Improved Double Reflector", "1989"]
					],
					pictures: [
						"/t IN R GE 1000RB52.jpg",
						"/t IN R 50R63IF-12-BA20d Atlas.jpg",
						"/t IN R Sylvania 75-240ER30IF-E27 side.jpg",
						"/t IN R GE 45BR30FL-E26.jpg",
						"/t IN R Philips 40NR60IF-E27.jpg"
					]
				},
				{
					subhead: "Sealed Beam",
					intros: [
						["GE", "30W", "PAR36 Auto / Pin Spot with anti glare shield", "1951"],
						["GE-Mazda", "150W", "PAR38 - First model for general display lighting", "1942"],
						["Thorn", "200W", "Unusual PAR46 design with E27 Cap", "1974"]
					],
					pictures: [
						"/t IN R GE 30PAR36VNSP-4515.jpg",
						"/t IN R GE 150PAR38SP-E26.jpg",
						"/t IN R Thorn 200PAR46SP.jpg"
					]
				},
				{
					subhead: "Crown Mirror",
					intros: [
						["GE", "200W", "White Bowl Indirect Light", "1939"],
						["GE", "100W", "Silver Bowl Indirect Light", "1935 c."],
						["Philips", "150W", "Crown Silver with Inside Frosted Glass", "1990"],
						["Philips", "30W", "Miniature Crown Silver with Ogive Bulb", "1983"]
					],
					pictures: [
						"/t IN R GE 125-200PS30WB-E26.jpg",
						"/t IN R GE 120-100A23SB-E26.jpg",
						"/t IN R 225-150A80CSF-E27 Philips.jpg",
						"/t IN R Philips 225-30PC35CS-E14.jpg"
					]
				},
				{
					subhead: "Side Mirror",
					intros: [["Mazda", "150W", "Rectalux for Street Lighting Service", "~1960"]],
					pictures: ["/t IN R Mazda Rectalux 2.jpg"]
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
					title: "反射白炽灯",
					description: [
						"尽管第一个具有反射器形状灯泡的白炽灯是在19世纪90年代创造的，但由于当时生产反射涂层的可用技术，以及对光学和反射器表面正确轮廓的理解，使得早期的灯具效率很低，很少被使用。直到20世纪30年代，随着一种新的制造镜面涂层技术的开发，以及科学设计的灯泡形状的平行引入以优化光学性能，现代反射灯才得以出现。后来玻璃成型工艺的发展，通过引入压制技术代替吹塑成型技术，实现了显著的性能提升。本页面介绍了反射白炽灯演变过程中的一些关键步骤。"
					]
				},
				{
					subhead: "吹制反射灯",
					intros: [
						["GE", "1000W", "High Wattage lamp with Compound Reflector", "~1955"],
						["Atlas", "50W", "Low Voltage Display - Parabolic Diffuse", "1970"],
						["Sylvania", "75W", "Ellipsoidal Reflector for European market", "~1985"],
						["GE", "45W", "Miser BR30 Improved Double Reflector", "1994"],
						["Philips", "40W", "Spotline NR60 Improved Double Reflector", "1989"]
					],
					pictures: [
						"/t IN R GE 1000RB52.jpg",
						"/t IN R 50R63IF-12-BA20d Atlas.jpg",
						"/t IN R Sylvania 75-240ER30IF-E27 side.jpg",
						"/t IN R GE 45BR30FL-E26.jpg",
						"/t IN R Philips 40NR60IF-E27.jpg"
					]
				},
				{
					subhead: "密封光束灯",
					intros: [
						["GE", "30W", "PAR36 Auto / Pin Spot with anti glare shield", "1951"],
						["GE-Mazda", "150W", "PAR38 - First model for general display lighting", "1942"],
						["Thorn", "200W", "Unusual PAR46 design with E27 Cap", "1974"]
					],
					pictures: [
						"/t IN R GE 30PAR36VNSP-4515.jpg",
						"/t IN R GE 150PAR38SP-E26.jpg",
						"/t IN R Thorn 200PAR46SP.jpg"
					]
				},
				{
					subhead: "冠状反射灯",
					intros: [
						["GE", "200W", "White Bowl Indirect Light", "1939"],
						["GE", "100W", "Silver Bowl Indirect Light", "1935 c."],
						["Philips", "150W", "Crown Silver with Inside Frosted Glass", "1990"],
						["Philips", "30W", "Miniature Crown Silver with Ogive Bulb", "1983"]
					],
					pictures: [
						"/t IN R GE 125-200PS30WB-E26.jpg",
						"/t IN R GE 120-100A23SB-E26.jpg",
						"/t IN R 225-150A80CSF-E27 Philips.jpg",
						"/t IN R Philips 225-30PC35CS-E14.jpg"
					]
				},
				{
					subhead: "侧反射灯",
					intros: [["Mazda", "150W", "Rectalux for Street Lighting Service", "~1960"]],
					pictures: ["/t IN R Mazda Rectalux 2.jpg"]
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
