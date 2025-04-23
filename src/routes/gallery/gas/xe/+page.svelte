<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Xenon Discharge Lamps",
					description: [
						"The Xenon lamp is of high value as a light source owing to the numerous spectral lines emitted by this gas when ionised, their relative intensities being such that a high quality white light is emitted. At high loading a near continuous spectrum can be achieved with outstanding colour properties, very similar to natural daylight.",
						"Xenon lamps exist in three primary formats : Short Arc lamps in which the primary objective is to achieve a compact, high brightness source; Long Arc lamps in which luminous efficacy is optimised; and Flashlamps, which are designed to provide a brilliant pulse of light of short duration for photographic applications, warning beacons and special theatrical effects."
					]
				},
				{
					subhead: "Compact Source Short Arc",
					intros: [
						["Osram", "1000W", "XBO 1001 First Short Arc Lamp", "1954 c."],
						["Thorn", "2000W", "XE/D for searchlight on the Centurion Tank", "1975 c."],
						["Mazda", "230W", "FA.5 Xenon flash tube or continuous arc", "1965"],
						["GE", "500W", "Compact Source EDR46 Reflector", "1970 c."]
					],
					pictures: [
						"/t D G Xe Osram XBO1001.jpg",
						"/t Thorn XED2000.jpg",
						"/t Mazda FA5.jpg",
						"/t D G Xe GE CSXR500.jpg"
					]
				},
				{
					subhead: "Compact Source Short Arc",
					intros: [
						["Mazda", "", "FA.12 U-shape Xenon Flash Tube", "1964"],
						["Mazda", "200J", "FA.7 Spiral Xenon Flash Tube", "1964"],
						["GE", "", "FT.24 Spiral Xenon flash with modelling lamp", ""],
						["GE", "8000W", "PXA80 Pulsed Xenon Arc Graphic Arts Lamp", "1990"],
						["Amglo", "", "Spiral shape xenon flash lamp for airfield use", "~1970"]
					],
					pictures: [
						"/t Mazda FA12.jpg",
						"/t Mazda FA7.jpg",
						"/t GE FT24.jpg",
						"/t GE PXA80.jpg",
						"/t Amglo Xenon.jpg"
					]
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
					title: "氙气放电灯",
					description: [
						"由于氙气在电离时发射出众多的光谱线，且其相对强度使得发出的光为高质量的白光，因此氙气灯作为光源具有很高的价值。在高负载下，可以实现接近连续的光谱，其色彩特性非常出色，与自然日光非常相似。",
						"氙气灯主要有三种形式：短弧灯，其主要目标是实现紧凑、高亮度的光源；长弧灯，其优化了发光效率；以及闪光灯，这种灯是为摄影应用、警示灯标和特殊舞台效果提供短暂而明亮的光脉冲而设计的。"
					]
				},
				{
					subhead: "紧凑型短弧光源",
					intros: [
						["Osram", "1000W", "XBO 1001 First Short Arc Lamp", "1954 c."],
						["Thorn", "2000W", "XE/D for searchlight on the Centurion Tank", "1975 c."],
						["Mazda", "230W", "FA.5 Xenon flash tube or continuous arc", "1965"],
						["GE", "500W", "Compact Source EDR46 Reflector", "1970 c."]
					],
					pictures: [
						"/t D G Xe Osram XBO1001.jpg",
						"/t Thorn XED2000.jpg",
						"/t Mazda FA5.jpg",
						"/t D G Xe GE CSXR500.jpg"
					]
				},
				{
					subhead: "长弧闪光灯管",
					intros: [
						["Mazda", "", "FA.12 U-shape Xenon Flash Tube", "1964"],
						["Mazda", "200J", "FA.7 Spiral Xenon Flash Tube", "1964"],
						["GE", "", "FT.24 Spiral Xenon flash with modelling lamp", ""],
						["GE", "8000W", "PXA80 Pulsed Xenon Arc Graphic Arts Lamp", "1990"],
						["Amglo", "", "Spiral shape xenon flash lamp for airfield use", "~1970"]
					],
					pictures: [
						"/t Mazda FA12.jpg",
						"/t Mazda FA7.jpg",
						"/t GE FT24.jpg",
						"/t GE PXA80.jpg",
						"/t Amglo Xenon.jpg"
					]
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
