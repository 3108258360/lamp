<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "LED - Integrated Lamps",
					description: [
						"This page features the category of Integrated LED lamps - in other words lamps that contain either a plurality of individual LED emitters, or in which the LEDs are packaged with other optical, thermal, mechanical or electronic components to deliver satisfactory operation. Individual LED emitters can be found under the separate section of Discrete LED Lamps.",
						"The category of Integrated LED Lamps is one of the newest families of light source, emerging only at the turn of the twenty-first century. This trend has been driven firstly by the possibility to create warm-white light of relatively high luminous flux, and by developments in compact electronic drivers which together allow the creation of LED Lamps that are capable of replacing traditional light sources with a substantial increase in luminous efficacy and lifetime."
					]
				},
				{
					intros: [
						["Philips", "400lm", "MasterLED 'Glow' with Remote Phosphor", "2009"],
						["Philips", "806lm", "MasterLED 'Prince' with Remote Phosphor", "2010"],
						["Philips", "470lm", "ClassicLED Glass Design with Gas-Phase Cooling", "2014"]
					],
					pictures: [
						"/t LEDi 230-7A60IF827-E27 Philips.jpg",
						"/t LEDi 230-12K58RP830-B22d Philips.jpg",
						"/t LEDi Philips 470A60IF827-E27 Midpower-in-Glass.jpg"
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
					title: "LED - 集成灯",
					description: [
						"本页面介绍的是集成式LED灯具类别，即包含多个单独的LED发射器，或者将LED与其他光学、热学、机械或电子元件封装在一起以实现满意运行的灯具。单独的LED发射器可以在分立式LED灯具部分找到。",
						"集成式LED灯具是最新出现的光源类别之一，仅在21世纪初才开始出现。这一趋势首先是由能够产生相对较高的光通量的暖白光的可能性推动的，同时紧凑型电子驱动器的发展也使得能够制造出LED灯具，这些灯具能够以显著提高的发光效率和使用寿命来替代传统光源。"
					]
				},
				{
					intros: [
						["Philips", "400lm", "MasterLED 'Glow' with Remote Phosphor", "2009"],
						["Philips", "806lm", "MasterLED 'Prince' with Remote Phosphor", "2010"],
						["Philips", "470lm", "ClassicLED Glass Design with Gas-Phase Cooling", "2014"]
					],
					pictures: [
						"/t LEDi 230-7A60IF827-E27 Philips.jpg",
						"/t LEDi 230-12K58RP830-B22d Philips.jpg",
						"/t LEDi Philips 470A60IF827-E27 Midpower-in-Glass.jpg"
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
