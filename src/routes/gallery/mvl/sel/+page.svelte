<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Self-Ballasted Mercury Blended",
					description: [
						"At the time of the introduction of high pressure mercury lamps, they were considered to have two principal drawbacks compared to their incandescent predecessors. Firstly, the cool white light colour with apalling colour rendering properties, and secondly the fact that they could not be connected directly to AC mains electricity supplies and required some form of electrical ballast.",
						"Both of these problems were alleviated with the concept of the mercury-blended lamp - which was achieved by mixing its blue-rich light with the red-rich radiation from an ordinary tungsten filament lamp. In the early 1900s it was recognised that specially designed filament lamps could be used as a resistive ballast to provide current regulation and colour correction for the arc, but it was not until 1929 that the filament and the arc were united within the same bulb to create the first blended-light lamps.",
						"Initial experiments in this field were limited to low pressure lamps for Ultraviolet applications. In 1935 the first mercury-blended lamp for general lighting was introduced, in the form of the Medium pressure MAT lamps invented by Siemens of England. A variety of high pressure MBT blended lamps followed quickly, and the addition of fluorescent phosphors achieved continual improvements in parallel with the developments being made in mercury-fluoresscent lamps."
					]
				},
				{
					subhead: "Low Pressure",
					intros: [["Philips", "110W", "Ultrasol 5023 Self-Ballasted Sunlamp", "1935"]],
					pictures: ["/t D MC Philips Ultrasol 5023.jpg"]
				},
				{
					subhead: "Medium Pressure",
					intros: [
						["Siemens", "300W", 'Sieray "Dual" MAT/V first self-ballasted lamp', "1940"],
						["Mazda", "300W", "MAT/V of final production design", "~1955"]
					],
					pictures: ["/t D MAT Siemens 300W.jpg", "/t Mazda MAT300.jpg"]
				},
				{
					subhead: "High Pressure",
					intros: [
						["Mazda", "200W", "MBT/V with shrink seals and pearl outer bulb", "~1945"],
						["Philips", "250W", "ML500 First model mercury blended", "~1940-45"],
						["Osram", "165W", "HWA 302 German lamp in pearl outer bulb", "1958"],
						["Bumix", "860W", '"Jupiter" variable colour mushroom-shape', "~1950"],
						["Philips", "160W", "ML Mixed Light Clear pear-shaped", "~1955"],
						["Philips", "160W", "ML with new design for automatic production", "2003"],
						["Thorn", "160W", "MBT Sunlight Clear mercury blended", "1987"],
						["National", "100W", "BH100 with preheated arc tube electrodes", "2001"],
						["DuroTest", "750W", "Self-Ballasted Lamp of high efficiency design", "~1960"],
						["XingJi", "500W", "HMB Halogen-Ballasted Mercury Vapour", "2003"]
					],
					pictures: [
						"/t Mazda MBT200.jpg",
						"/t Philips ML500.jpg",
						"/t Osram HWA165.jpg",
						"/t Bumix Jupiter.jpg",
						"/t D MBT Philips ML160 Clear PS90.jpg",
						"/t Philips ML160.jpg",
						"/t Thorn MBT160.jpg",
						"/t National MBT100V.jpg",
						"/t D MBT Jewel SB750.jpg",
						"/t XingJi HMB500.jpg"
					]
				},
				{
					subhead: "High Pressure Fluorescent",
					intros: [
						["Philips", "160W", "MBTL with Magnesium fluoro-germanate", "1960"],
						["Atlas", "250W", "MBTF with Yttrium Vanadate coated bulb", "1970"],
						["Osram", "500W", "HWL with isothermal bulb shape", "1974?"],
						["GE", "160W", "E-Z Lux low voltage HSB160/PS30/M", "~1980"],
						["DuroTest", "450W", "Fluomeric with special high efficiency design", "1970/78"],
						["Philips", "160W", "MLR mercury blended reflector style", "1984"]
					],
					pictures: [
						"/t Philips MBTL160.jpg",
						"/t Atlas MBTF250.jpg",
						"/t Osram HWL500.jpg",
						"/t GE MBTF160.jpg",
						"/t Durotest SB450R.jpg",
						"/t Philips MLR160.jpg"
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
					title: "自镇流汞混合灯",
					description: [
						"在高压汞灯首次推出时，与白炽灯相比，它们被认为存在两个主要缺点。首先，其冷白色光的显色性能极差，其次，它们不能直接连接到交流电源，需要某种形式的电气镇流器。",
						"通过汞混合灯的概念解决了这两个问题，即通过将蓝光丰富的汞灯光与普通白炽灯发出的红光丰富的辐射混合。早在20世纪初就认识到，特殊设计的白炽灯可以用作电阻镇流器，为弧光提供电流调节和颜色校正，但直到1929年，灯丝和弧光才被统一到同一个灯泡中，从而创造了第一盏混合光灯。",
						"该领域的初步实验仅限于用于紫外线应用的低压灯。1935年，第一盏用于普通照明的汞混合灯问世，即由英国西门子发明的中压MAT灯。随后很快出现了多种高压MBT混合灯，通过添加荧光粉，与汞荧光灯的发展同步实现了持续改进。"
					]
				},
				{
					subhead: "低压",
					intros: [["Philips", "110W", "Ultrasol 5023 Self-Ballasted Sunlamp", "1935"]],
					pictures: ["/t D MC Philips Ultrasol 5023.jpg"]
				},
				{
					subhead: "中压",
					intros: [
						["Siemens", "300W", 'Sieray "Dual" MAT/V first self-ballasted lamp', "1940"],
						["Mazda", "300W", "MAT/V of final production design", "~1955"]
					],
					pictures: ["/t D MAT Siemens 300W.jpg", "/t Mazda MAT300.jpg"]
				},
				{
					subhead: "高压",
					intros: [
						["Mazda", "200W", "MBT/V with shrink seals and pearl outer bulb", "~1945"],
						["Philips", "250W", "ML500 First model mercury blended", "~1940-45"],
						["Osram", "165W", "HWA 302 German lamp in pearl outer bulb", "1958"],
						["Bumix", "860W", '"Jupiter" variable colour mushroom-shape', "~1950"],
						["Philips", "160W", "ML Mixed Light Clear pear-shaped", "~1955"],
						["Philips", "160W", "ML with new design for automatic production", "2003"],
						["Thorn", "160W", "MBT Sunlight Clear mercury blended", "1987"],
						["National", "100W", "BH100 with preheated arc tube electrodes", "2001"],
						["DuroTest", "750W", "Self-Ballasted Lamp of high efficiency design", "~1960"],
						["XingJi", "500W", "HMB Halogen-Ballasted Mercury Vapour", "2003"]
					],
					pictures: [
						"/t Mazda MBT200.jpg",
						"/t Philips ML500.jpg",
						"/t Osram HWA165.jpg",
						"/t Bumix Jupiter.jpg",
						"/t D MBT Philips ML160 Clear PS90.jpg",
						"/t Philips ML160.jpg",
						"/t Thorn MBT160.jpg",
						"/t National MBT100V.jpg",
						"/t D MBT Jewel SB750.jpg",
						"/t XingJi HMB500.jpg"
					]
				},
				{
					subhead: "高压荧光灯",
					intros: [
						["Philips", "160W", "MBTL with Magnesium fluoro-germanate", "1960"],
						["Atlas", "250W", "MBTF with Yttrium Vanadate coated bulb", "1970"],
						["Osram", "500W", "HWL with isothermal bulb shape", "1974?"],
						["GE", "160W", "E-Z Lux low voltage HSB160/PS30/M", "~1980"],
						["DuroTest", "450W", "Fluomeric with special high efficiency design", "1970/78"],
						["Philips", "160W", "MLR mercury blended reflector style", "1984"]
					],
					pictures: [
						"/t Philips MBTL160.jpg",
						"/t Atlas MBTF250.jpg",
						"/t Osram HWL500.jpg",
						"/t GE MBTF160.jpg",
						"/t Durotest SB450R.jpg",
						"/t Philips MLR160.jpg"
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
