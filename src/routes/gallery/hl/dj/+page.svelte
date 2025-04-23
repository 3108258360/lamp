<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Tungsten Halogen - Double Jacket",
					description: [
						"Double Envelope halogen lamps consist of an inner halogen capsule sealed within a secondary outer bulb. The design may be adopted for a number of reasons - for instance to protect quartz capsules from accidental contamination with fingerprints, to protect surroundings from possible shattering of the inner capsule at end of life, to filter out UV radiation, to reduce the surface temperature of external parts of the lamp, or simply as a convenient mechanical structure which allows easy retrofitting of conventional incandescent lamps.",
						"They were first introduced for special applications such as photographic and studio lighting, but were later engineered to replace ordinary incandescent lamps employed in general lighting service. In particular since the phasing out of low-efficacy incandescent lamps in many parts of the world, double envelope halogen lamps have grown in popularity owing to their low cost, perfect colour rendering properties, simple operation and similar appearance and dimensions to incandescent lamps."
					]
				},
				{
					subhead: "Quartz Capsule High Power",
					intros: [
						["Philips", "1000W", "Double Jacket High Efficacy - IODE", "1989"],
						["Wotan", "250W", "Halostar High Wattage - Original Glass Design", "1986"],
						["Osram", "250W", "Halostar High Wattage - Later Ceramic Design", "1990"]
					],
					pictures: [
						"/t TH DJ Q1000T38C-230 Philips.jpg",
						"/t TH DJ Q250T32CL-E27-245 Wotan.jpg",
						"/t TH DJ Q250T32CL-E27-245 Osram.jpg"
					]
				},
				{
					subhead: "Quartz Capsule Low Power",
					intros: [
						["Thorn", "100W", "Low Wattage Universal Burning - Ceramic type", "1989"],
						["Thorn", "100W", "Low Wattage Universal Burning - Glass type", "~1989"],
						["Thorn", "150W", "Low Wattage Universal Burning - Frosted type", "1989"],
						["Philips", "75W", "Halogèna Low Wattage Tubular Frosted", "1989"],
						["Philips", "75W", "Halogèna Low Wattage Bulged Tubular Clear", "1990"],
						["Philips", "100W", "Halogèna Low Wattage Bulged Tubular Opal", "1991"],
						["Philips", "60W", "Halogèna Low Wattage Bulged Tubular Miniature", "1991"],
						["Philips", "60W", "Halogèna Natural Light Plus Neodymium Glass", "2004"],
						["Osram", "60W", "Decorative with unsealed Hexagonal Candle bulb", "1994"],
						["Osram", "60W", "Halolux Classic Pear Shape GLS Retrofit", "2004"],
						["Radium", "60W", "Halogen Double Envelope with Oxygen Fuse", "2004"]
					],
					pictures: [
						"/t TH DJ Q100T28CL-E27-225 Thorn K16.jpg",
						"/t TH DJ Q100BT45CL-E27-245 Thorn.jpg",
						"/t TH DJ Q150BT45FR-E27-120 Thorn.jpg",
						"/t TH DJ Q75T32FR-E27-225 Philips.jpg",
						"/t TH DJ Q75BT45C-B22d-225 Philips.jpg",
						"/t TH DJ Q100BT45OP-B22d-245 Philips.jpg",
						"/t TH DJ Q60BT35CL-E14-225 Philips.jpg",
						"/t TH DJ Q60BT45ND-E26-120 Philips.jpg",
						"/t TH DJ Q60HX35CL-E14-230 Osram.jpg",
						"/t TH DJ Q60A60CL-B22d-240 Osram.jpg",
						"/t TH DJ Q60BT45CL-E26-120 Sylvania.jpg"
					]
				},
				{
					subhead: "Hardglass Capsule",
					intros: [
						["GE", "51W", "A-Line Performance Plus Hardglass Design", "1987"],
						["Sylvania", "72W", "Capsylite High Efficacy with Diode Rectifier", "1989"],
						["Sylvania", "50W", "Halogen DLX with Hardglass Capsule", "1994"]
					],
					pictures: [
						"/t TH DJ Q51TB19FR-E26-120 GE.jpg",
						"/t TH DJ Q72MB19FR-E26-120 Sylvania.jpg",
						"/t TH DJ Q50BT45CL-E27-230 Sylvania.jpg"
					]
				},
				{
					subhead: "Integrated Transformer",
					intros: [["Philips", "30W", "MasterClassic with 12V IRC Capsule & Transfo.", "2008"]],
					pictures: ["/t TH DJ QIR30A55CL-E27-230 Philips.jpg"]
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
					title: "钨丝卤素灯 - 双层外壳",
					description: [
						"双层外壳卤素灯由一个内层卤素灯泡密封在一个外层灯泡内。这种设计可能出于多种原因被采用——例如，防止石英灯泡意外沾染指纹，防止内层灯泡在寿命末期破裂对周围环境造成影响，过滤紫外线，降低灯外部部件的表面温度，或者仅仅作为一种方便的机械结构，便于替换传统白炽灯。",
						"它们最初被用于特殊应用，如摄影和工作室照明，但后来被设计用于替换普通白炽灯，用于普通照明服务。特别是在许多国家逐步淘汰低效率白炽灯后，双层外壳卤素灯因其低成本、完美的色彩还原特性、简单的操作以及与白炽灯相似的外观和尺寸而越来越受欢迎。"
					]
				},
				{
					subhead: "高功率石英胶囊",
					intros: [
						["Philips", "1000W", "Double Jacket High Efficacy - IODE", "1989"],
						["Wotan", "250W", "Halostar High Wattage - Original Glass Design", "1986"],
						["Osram", "250W", "Halostar High Wattage - Later Ceramic Design", "1990"]
					],
					pictures: [
						"/t TH DJ Q1000T38C-230 Philips.jpg",
						"/t TH DJ Q250T32CL-E27-245 Wotan.jpg",
						"/t TH DJ Q250T32CL-E27-245 Osram.jpg"
					]
				},
				{
					subhead: "低功率石英胶囊",
					intros: [
						["Thorn", "100W", "Low Wattage Universal Burning - Ceramic type", "1989"],
						["Thorn", "100W", "Low Wattage Universal Burning - Glass type", "~1989"],
						["Thorn", "150W", "Low Wattage Universal Burning - Frosted type", "1989"],
						["Philips", "75W", "Halogèna Low Wattage Tubular Frosted", "1989"],
						["Philips", "75W", "Halogèna Low Wattage Bulged Tubular Clear", "1990"],
						["Philips", "100W", "Halogèna Low Wattage Bulged Tubular Opal", "1991"],
						["Philips", "60W", "Halogèna Low Wattage Bulged Tubular Miniature", "1991"],
						["Philips", "60W", "Halogèna Natural Light Plus Neodymium Glass", "2004"],
						["Osram", "60W", "Decorative with unsealed Hexagonal Candle bulb", "1994"],
						["Osram", "60W", "Halolux Classic Pear Shape GLS Retrofit", "2004"],
						["Radium", "60W", "Halogen Double Envelope with Oxygen Fuse", "2004"]
					],
					pictures: [
						"/t TH DJ Q100T28CL-E27-225 Thorn K16.jpg",
						"/t TH DJ Q100BT45CL-E27-245 Thorn.jpg",
						"/t TH DJ Q150BT45FR-E27-120 Thorn.jpg",
						"/t TH DJ Q75T32FR-E27-225 Philips.jpg",
						"/t TH DJ Q75BT45C-B22d-225 Philips.jpg",
						"/t TH DJ Q100BT45OP-B22d-245 Philips.jpg",
						"/t TH DJ Q60BT35CL-E14-225 Philips.jpg",
						"/t TH DJ Q60BT45ND-E26-120 Philips.jpg",
						"/t TH DJ Q60HX35CL-E14-230 Osram.jpg",
						"/t TH DJ Q60A60CL-B22d-240 Osram.jpg",
						"/t TH DJ Q60BT45CL-E26-120 Sylvania.jpg"
					]
				},
				{
					subhead: "硬石英胶囊",
					intros: [
						["GE", "51W", "A-Line Performance Plus Hardglass Design", "1987"],
						["Sylvania", "72W", "Capsylite High Efficacy with Diode Rectifier", "1989"],
						["Sylvania", "50W", "Halogen DLX with Hardglass Capsule", "1994"]
					],
					pictures: [
						"/t TH DJ Q51TB19FR-E26-120 GE.jpg",
						"/t TH DJ Q72MB19FR-E26-120 Sylvania.jpg",
						"/t TH DJ Q50BT45CL-E27-230 Sylvania.jpg"
					]
				},
				{
					subhead: "集成变压器",
					intros: [["Philips", "30W", "MasterClassic with 12V IRC Capsule & Transfo.", "2008"]],
					pictures: ["/t TH DJ QIR30A55CL-E27-230 Philips.jpg"]
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
