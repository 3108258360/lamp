<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "SOX Low Pressure Sodium with IR Coating",
					description: [
						"The final great breakthrough in improving the thermal insulation of sodium lamps came in 1964, when thin heat-reflecting films of exotic materials were introduced. A microscopically thin coating on the inside of the outer jacket successfully dispensed with the cumbersome heat-reflecting glass sleeves of the SOI design. Film composition and thickness is arranged such that they reflect the infrared while still allowing the visible light to pass through. Initially a 50-nanometre film of pure gold was employed, on the Linear sodium range. This remains the best heat reflector, but it also absorbs a lot of light. Bismuth was tried in some German lamps, but the biggest improvements came with the use of metal oxide semiconductor films and the name SOX was introduced with these lamps. These materials can be doped so that they have high infrared reflectivity, while still being transparent to visible light.",
						"Between 1964 and 1967 a range of SOX lamps having stannic oxide coatings was marketed. Because of the great increase in efficacy, lamp wattages had to be reduced. This material was superseded in 1967-68 with a 0.32 micron coating of tin-doped indium oxide, the film still employed in today's SOX lamps. The corresponding increase in efficacy saw the SOX lamps re-rated once again.",
						"A further improvement was made in 1983 with so-called SOX-E lamps. These employ a film of greater thickness which delivers improved heat reflection. Lamp power had to be reduced again to prevent overheating, with the reduced current density leading to efficacies up to 200 lm/W. Some types feature an advanced platinum catalyst in the outer jacket to crack hydrdocarbon vapours and further reduce conducted heat losses.",
						"Incidentally it is often possible to tell the coating type from the colour of surface reflections in the film. Stannic oxide lamps produce a yellow/orange colour, indium oxide takes on a greenish hue, while SOX-E coatings impart a reddish colour to reflected light."
					]
				},
				{
					subhead: "Tin Oxide Lamps",
					intros: [
						["Philips", "40W", "SO-X with IR coating of stannic oxide", "1963"],
						["Osram-GEC", "40W", "SOX/H with IR coating of stannic oxide", "1967"]
					],
					pictures: ["/t D SLP Philips SOX40.jpg", "/t D SLP GEC SOX40.jpg"]
				},
				{
					subhead: "Indium Oxide Lamps",
					intros: [
						["Philips", "90W", "SO-X of Philips' first indium construction", "1968"],
						["Philips", "35W", "SO-X of Philips' first indium construction", "1971"],
						["Philips", "90W", "SOX with improved inner support assembly", "1988"],
						["Philips", "35W", "SOX-Plus design with increased service life", "1996"],
						["Philips", "35W", "SOX-PSG with increased reliability and service life", "2003"],
						["Osram-GEC", "90W", "SOX/H 1st generation : Dimpled discharge tube", "1967"],
						["Osram-GEC", "55W", "SuperSOX 2nd gen.: Ring Moulds & Graded Film", "1978"],
						["Osram-GEC", "90W", "SuperSOX 3rd gen.: Improved top support", "1983"],
						["Osram", "55W", "SuperSOX 4th gen.: Improved top support", "1993"],
						["Osram", "35W", "SOX-Plus 5th gen.: Improved top support", "1996"],
						["Osram", "55W", "SOX  6th gen.: Manufactured by Philips", "2003"],
						["Thorn", "135W", "SOX lamp of Thorn's second generation", "1983"],
						["Thorn EMI", "35W", "SOX lamp of Thorn's second generation", "1986"],
						["GE-Thorn", "35W", "SOX lamp of Thorn's third generation", "1991"],
						["GE", "35W", "SOX-Plus with increased life guarantee", "2004"]
					],
					pictures: [
						"/t D SLP Philips SOX90.jpg",
						"/t D SLP Philips SOX35.jpg",
						"/t D SLP Philips SOX90 Mk2.jpg",
						"/t D SLP Philips SOXP35.jpg",
						"/t D SLP Philips SOXPSG35.jpg",
						"/t D SLP GEC SOX90 Dimpled.jpg",
						"/t D SLP GEC SOX55.jpg",
						"/t D SLP GEC SOX90.jpg",
						"/t D SLP Osram SOX55.jpg",
						"/t D SLP Osram SOXP35.jpg",
						"/t D SLP Osram SOX55 Hamilton.jpg",
						"/t D SLP Thorn SOX135.jpg",
						"/t D SLP Thorn SOX35.jpg",
						"/t D SLP Thorn SOX35 Mk2.jpg",
						"/t D SLP GE SOXP35.jpg"
					]
				},
				{
					subhead: "Improved Indium Oxide (Economy) Lamps",
					intros: [
						["Philips", "26W", "SOX-E Economy with improved efficacy", "1984"],
						["Osram-GEC", "26W", "SOX-E Economy with improved efficacy", "1985"],
						["GE", "26W", "SOX-E Economy with improved efficacy", "2003"],
						["Philips", "36W", "SOX-E PSG with solid-state getter", "2012"]
					],
					pictures: [
						"/t D SLP Philips SOXE26.jpg",
						"/t D SLP GEC SOXE26.jpg",
						"/t D SLP GE SOXE26.jpg",
						"/t D SLP Philips SOXEPSG36.jpg"
					]
				},
				{
					subhead: "Miniature Lamps",
					intros: [
						["Philips", "18W", "Mini-SOX lamp for security lighting", "1977"],
						["Osram-GEC", "18W", "Miniature 18-watt lamp for security lighting", "1981"],
						["Osram-GEC", "10W", "Miniature 10-watt lamp for security lighting", "1981"],
						["Thorn", "6W", "Experimental 6-watt miniature lamp", "~1985"],
						["Philips", "18W", "Experimental 18-watt improved efficacy lamp", "~1985"]
					],
					pictures: [
						"/t D SLP Philips SOX18.jpg",
						"/t D SLP GEC SOX18.jpg",
						"/t D SLP GEC SOX10.jpg",
						"/t Thorn SOX6.jpg",
						"/t D SLP Philips SOX-HV18.jpg"
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
					title: "SOX 带红外涂层的低压钠灯",
					description: [
						"在1964年，通过引入稀有材料的薄热反射膜，钠灯隔热性能的改进取得了最终的重大突破。在外罩内部的微观薄涂层成功地取代了SOI设计中笨重的热反射玻璃袖。薄膜的成分和厚度被安排得能够反射红外线，同时仍然允许可见光通过。最初，在线性钠灯系列中使用了50纳米厚的纯金薄膜。这仍然是最好的热反射材料，但它也会吸收很多光。在一些德国灯具中尝试过使用铋，但最大的改进来自于使用金属氧化物半导体薄膜，而SOX这个名字正是随着这些灯具被引入的。这些材料可以通过掺杂，使其具有高红外反射率，同时对可见光保持透明。",
						"在1964年至1967年间，市场上销售了一系列带有二氧化锡涂层的SOX灯具。由于光效大幅提高，灯具的功率不得不降低。这种材料在1967-1968年被0.32微米厚的掺锡氧化铟涂层所取代，这种薄膜至今仍用于SOX灯具中。相应的光效提高使得SOX灯具再次被重新评级。",
						"1983年，所谓的SOX-E灯具又有了进一步的改进。这些灯具使用了更厚的薄膜，提供了更好的热反射效果。为了防止过热，灯具的功率再次降低，降低后的电流密度使得光效高达200流明/瓦。一些型号在外罩中采用了先进的铂催化剂，以分解烃类蒸汽，进一步减少传导热损失。",
						"顺便说一下，通常可以从薄膜表面反射光的颜色来判断涂层的类型。二氧化锡灯具会产生黄色/橙色的反射光，氧化铟呈现绿色调，而SOX-E涂层则使反射光带有红色。"
					]
				},
				{
					subhead: "氧化锡灯",
					intros: [
						["Philips", "40W", "SO-X with IR coating of stannic oxide", "1963"],
						["Osram-GEC", "40W", "SOX/H with IR coating of stannic oxide", "1967"]
					],
					pictures: ["/t D SLP Philips SOX40.jpg", "/t D SLP GEC SOX40.jpg"]
				},
				{
					subhead: "氧化铟灯",
					intros: [
						["Philips", "90W", "SO-X of Philips' first indium construction", "1968"],
						["Philips", "35W", "SO-X of Philips' first indium construction", "1971"],
						["Philips", "90W", "SOX with improved inner support assembly", "1988"],
						["Philips", "35W", "SOX-Plus design with increased service life", "1996"],
						["Philips", "35W", "SOX-PSG with increased reliability and service life", "2003"],
						["Osram-GEC", "90W", "SOX/H 1st generation : Dimpled discharge tube", "1967"],
						["Osram-GEC", "55W", "SuperSOX 2nd gen.: Ring Moulds & Graded Film", "1978"],
						["Osram-GEC", "90W", "SuperSOX 3rd gen.: Improved top support", "1983"],
						["Osram", "55W", "SuperSOX 4th gen.: Improved top support", "1993"],
						["Osram", "35W", "SOX-Plus 5th gen.: Improved top support", "1996"],
						["Osram", "55W", "SOX  6th gen.: Manufactured by Philips", "2003"],
						["Thorn", "135W", "SOX lamp of Thorn's second generation", "1983"],
						["Thorn EMI", "35W", "SOX lamp of Thorn's second generation", "1986"],
						["GE-Thorn", "35W", "SOX lamp of Thorn's third generation", "1991"],
						["GE", "35W", "SOX-Plus with increased life guarantee", "2004"]
					],
					pictures: [
						"/t D SLP Philips SOX90.jpg",
						"/t D SLP Philips SOX35.jpg",
						"/t D SLP Philips SOX90 Mk2.jpg",
						"/t D SLP Philips SOXP35.jpg",
						"/t D SLP Philips SOXPSG35.jpg",
						"/t D SLP GEC SOX90 Dimpled.jpg",
						"/t D SLP GEC SOX55.jpg",
						"/t D SLP GEC SOX90.jpg",
						"/t D SLP Osram SOX55.jpg",
						"/t D SLP Osram SOXP35.jpg",
						"/t D SLP Osram SOX55 Hamilton.jpg",
						"/t D SLP Thorn SOX135.jpg",
						"/t D SLP Thorn SOX35.jpg",
						"/t D SLP Thorn SOX35 Mk2.jpg",
						"/t D SLP GE SOXP35.jpg"
					]
				},
				{
					subhead: "改良型氧化铟灯(经济型)",
					intros: [
						["Philips", "26W", "SOX-E Economy with improved efficacy", "1984"],
						["Osram-GEC", "26W", "SOX-E Economy with improved efficacy", "1985"],
						["GE", "26W", "SOX-E Economy with improved efficacy", "2003"],
						["Philips", "36W", "SOX-E PSG with solid-state getter", "2012"]
					],
					pictures: [
						"/t D SLP Philips SOXE26.jpg",
						"/t D SLP GEC SOXE26.jpg",
						"/t D SLP GE SOXE26.jpg",
						"/t D SLP Philips SOXEPSG36.jpg"
					]
				},
				{
					subhead: "微型灯",
					intros: [
						["Philips", "18W", "Mini-SOX lamp for security lighting", "1977"],
						["Osram-GEC", "18W", "Miniature 18-watt lamp for security lighting", "1981"],
						["Osram-GEC", "10W", "Miniature 10-watt lamp for security lighting", "1981"],
						["Thorn", "6W", "Experimental 6-watt miniature lamp", "~1985"],
						["Philips", "18W", "Experimental 18-watt improved efficacy lamp", "~1985"]
					],
					pictures: [
						"/t D SLP Philips SOX18.jpg",
						"/t D SLP GEC SOX18.jpg",
						"/t D SLP GEC SOX10.jpg",
						"/t Thorn SOX6.jpg",
						"/t D SLP Philips SOX-HV18.jpg"
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
