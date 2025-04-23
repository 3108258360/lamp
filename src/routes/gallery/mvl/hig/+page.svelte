<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "High Pressure Mercury Vapour",
					description: [
						"High pressure mercury lamps are classified as the MB type. They operate at a vapour pressure of about ten atmospheres, the discharge dissipates between 10 and 100 watts per centimetre of arc length, and their arc tubes are made of extremely refactory fused silica (quartz), which can withstand higher temperatures and pressures.",
						"The high pressure MB lamps solved a problem with the earlier medium pressure MA lamps in that the efficacy of mercury lamps always decreases at lower powers, which prevented the successful development of low wattage MA lamps. However, the higher pressures that can be achieved with quartz arc tubes causes an increase in efficacy which is most pronounced in the smaller lamps.",
						"The technology was introduced in 1936 by Philips of the Netherlands, by combining its deep understanding of discharge physics with a new kind of tungsten-to-quartz graded seal that facilitated the use of the new arc tube material. The following year high pressure lamps were adopted by most manufacturers around the world, but some chose an alternative molybdenum foil seal developed in Britain.",
						"The first lamps were in the low power range from 80-125W, and although MB lamps are more efficient than MA types in the higher wattages, the efficacy benefit is somewhat reduced. The quartz material for the arc tubes as well as the labour-intensive seals made these lamps extremely expensive, and it took a further three decades of cost reduction before the higher power MA types were finally displaced. Improved variants of the high pressure lamps were made in the form of the MBF Fluorescent and MBT self-ballasted designs, as well as a wide variety of projection and ultraviolet variants. Detailed information on the development and fundamentals of high pressure mercury lamps can be found at the MB Technical Section."
					]
				},
				{
					subhead: "Graded-Seal Lamps",
					intros: [
						["GE", "85W", "H-3 early model with graded seals to tungsten", "1937"],
						["GE-Mazda", "100W", "H-4 early model with graded seals to tungsten", "1938"],
						["GE-Mazda", "250W", "H-5 early model with graded seals to tungsten", "1943"]
					],
					pictures: ["/t GE H3.jpg", "/t D MB GE H4.jpg", "/t GE A-H5.jpg"]
				},
				{
					subhead: "Shrink-Seal Lamps",
					intros: [
						["GEC", "125W", "Osira MB/V first model with moly shrink-seals", "1944"],
						["Siemens", "125W", "Sieray Type QH with Siemens Foil Seals", "1944"],
						["Mazda", "80W", "MB/V with earliest mechanised seal design", "1947"],
						["Mazda", "80W", "MB/V first model with moly shrink-seals", "1947"]
					],
					pictures: [
						"/t D MB Osira MBV125.jpg",
						"/t D MB Siemens MBV125.jpg",
						"/t D MB Mazda MB80 Clear.jpg",
						"/t Mazda MB80.jpg"
					]
				},
				{
					subhead: "Pinch-Seal Lamps",
					intros: [
						["Crompton", "80W", "MB/U in pear shaped pearl bulb", "~1955"],
						["GEC", "125W", "MB/U in pear shaped pearl bulb", "1978"],
						["Mazda", "125W", "MB/U in ellipsoidal shaped pearl bulb", "1969"],
						["Sylvania", "40W", "H45-AZ Low Wattage Mercury Discharge", "~1965"],
						["Osram", "125W", "HQA with new emitter to reduced blackening", "1965"],
						["Narva", "125W", "NF125-00 with sintered emitter pellet electrodes", "1972"],
						["GE", "100W", "H100/A23 for retrofit into GLS luminaires", "1979"],
						["Philips", "400W", "MB/V Long tubular style to replace MA size lamp", "1964"],
						["Atlas", "400W", "MB/V Long tubular style to replace MA size lamp", "1970"],
						["GEC", "250W", "MB/U short tubular style for new applications", "1974"],
						["Sylvania", "400W", "H33-1CD Rough Service lamp with girder frame", "1968"],
						["Iwasaki", "2000W", "H2000B High Wattage", "1997"]
					],
					pictures: [
						"/t Crompton MB80.jpg",
						"/t GEC MB125.jpg",
						"/t Mazda MB125.jpg",
						"/t Sylvania H45AZ.jpg",
						"/t Osram HQA125.jpg",
						"/t Narva NF125.jpg",
						"/t D MB GE H100A23.jpg",
						"/t Philips MB400.jpg",
						"/t Atlas MB400.jpg",
						"/t GEC MB250.jpg",
						"/t Sylvania H400.jpg",
						"/t Iwasaki MB2000.jpg"
					]
				},
				{
					subhead: "Reflector Lamps",
					intros: [
						["Sylvania", "100W", "H44GS-100 Mercury Sealed Beam Reflector", "2003"],
						["Iwasaki", "50W", "HR50W/S Mercury Spot Reflector Lamp", "2001"]
					],
					pictures: ["/t Sylvania H44.jpg", "/t Iwasaki H50R20.jpg"]
				},
				{
					subhead: "Special Lamps",
					intros: [
						["BTH Mazda", "40W", "MBM Coal Mine lamp for compressed air system", "1947"],
						["Thorn EMI", "40W", "MBM Coal Mine lamp for compressed air system", "1988"]
					],
					pictures: ["/t Mazda MBM40.jpg", "/t D MB Thorn MBM40.jpg"]
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
					title: "高压汞蒸气",
					description: [
						"高压汞灯被归类为MB型。它们在大约十个大气压的蒸气压力下工作，放电在每厘米弧长之间耗散10到100瓦的功率，它们的弧光管由极其耐火的熔融石英制成，能够承受更高的温度和压力。",
						"高压MB灯解决了早期中压MA灯的一个问题，即汞灯的效率总是随着功率的降低而下降，这阻碍了低功率MA灯的成功开发。然而，使用石英弧光管可以实现更高的压力，这使得效率增加，特别是在较小的灯具中更为明显。",
						"这项技术是由荷兰的飞利浦公司在1936年引入的，它结合了对放电物理的深刻理解以及一种新的钨-石英渐变密封技术，这种技术便于使用新的弧光管材料。第二年，大多数全球制造商都采用了高压灯，但有些选择了在英国开发的替代钼箔密封技术。",
						"最初的灯具功率较低，范围在80-125瓦之间。尽管在更高功率下，MB型灯比MA型灯更高效，但这种效率优势在一定程度上有所减少。弧光管的石英材料以及劳动密集型的密封工艺使得这些灯具极其昂贵，又花了三十年的时间降低成本，才最终取代了高功率的MA型灯。高压灯的改进型包括MBF荧光灯和MBT自镇流设计，以及各种投影和紫外线变体。关于高压汞灯的发展和基本原理的详细信息可以在MB技术部分找到。"
					]
				},
				{
					subhead: "分级密封灯",
					intros: [
						["GE", "85W", "H-3 early model with graded seals to tungsten", "1937"],
						["GE-Mazda", "100W", "H-4 early model with graded seals to tungsten", "1938"],
						["GE-Mazda", "250W", "H-5 early model with graded seals to tungsten", "1943"]
					],
					pictures: ["/t GE H3.jpg", "/t D MB GE H4.jpg", "/t GE A-H5.jpg"]
				},
				{
					subhead: "收缩密封灯",
					intros: [
						["GEC", "125W", "Osira MB/V first model with moly shrink-seals", "1944"],
						["Siemens", "125W", "Sieray Type QH with Siemens Foil Seals", "1944"],
						["Mazda", "80W", "MB/V with earliest mechanised seal design", "1947"],
						["Mazda", "80W", "MB/V first model with moly shrink-seals", "1947"]
					],
					pictures: [
						"/t D MB Osira MBV125.jpg",
						"/t D MB Siemens MBV125.jpg",
						"/t D MB Mazda MB80 Clear.jpg",
						"/t Mazda MB80.jpg"
					]
				},
				{
					subhead: "夹封灯",
					intros: [
						["Crompton", "80W", "MB/U in pear shaped pearl bulb", "~1955"],
						["GEC", "125W", "MB/U in pear shaped pearl bulb", "1978"],
						["Mazda", "125W", "MB/U in ellipsoidal shaped pearl bulb", "1969"],
						["Sylvania", "40W", "H45-AZ Low Wattage Mercury Discharge", "~1965"],
						["Osram", "125W", "HQA with new emitter to reduced blackening", "1965"],
						["Narva", "125W", "NF125-00 with sintered emitter pellet electrodes", "1972"],
						["GE", "100W", "H100/A23 for retrofit into GLS luminaires", "1979"],
						["Philips", "400W", "MB/V Long tubular style to replace MA size lamp", "1964"],
						["Atlas", "400W", "MB/V Long tubular style to replace MA size lamp", "1970"],
						["GEC", "250W", "MB/U short tubular style for new applications", "1974"],
						["Sylvania", "400W", "H33-1CD Rough Service lamp with girder frame", "1968"],
						["Iwasaki", "2000W", "H2000B High Wattage", "1997"]
					],
					pictures: [
						"/t Crompton MB80.jpg",
						"/t GEC MB125.jpg",
						"/t Mazda MB125.jpg",
						"/t Sylvania H45AZ.jpg",
						"/t Osram HQA125.jpg",
						"/t Narva NF125.jpg",
						"/t D MB GE H100A23.jpg",
						"/t Philips MB400.jpg",
						"/t Atlas MB400.jpg",
						"/t GEC MB250.jpg",
						"/t Sylvania H400.jpg",
						"/t Iwasaki MB2000.jpg"
					]
				},
				{
					subhead: "反射灯",
					intros: [
						["Sylvania", "100W", "H44GS-100 Mercury Sealed Beam Reflector", "2003"],
						["Iwasaki", "50W", "HR50W/S Mercury Spot Reflector Lamp", "2001"]
					],
					pictures: ["/t Sylvania H44.jpg", "/t Iwasaki H50R20.jpg"]
				},
				{
					subhead: "特殊灯",
					intros: [
						["BTH Mazda", "40W", "MBM Coal Mine lamp for compressed air system", "1947"],
						["Thorn EMI", "40W", "MBM Coal Mine lamp for compressed air system", "1988"]
					],
					pictures: ["/t Mazda MBM40.jpg", "/t D MB Thorn MBM40.jpg"]
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
