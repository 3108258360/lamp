<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent - Tantalum Filament lamp",
					description: [
						"The tantalum filament lamp was the first widely successful replacement for its carbon predecessors. Its invention is credited to Drs. Werner von Bolton and Otto Feuerlein of the Siemens & Halske laboratories at Berlin-Moabit, Germany. Although their first lamp was created in December 1902, it was not until 1905 that production commenced. The reduced vapour pressure of tantalum, by contrast with carbon, permits higher temperature operation for the same lamp life. This yields an efficacy of about 6 lm/W, double that of the carbon filament, together with a much whiter colour light.",
						"The mechanical properties of metal filaments are quite different than carbon, and do not show the same degree of rigidity and elasticity. Whereas carbon filaments can be formed into a given shape and this does not change when they are brought to incandescent temperatures, metallic filaments quickly sag under the influence of gravity. A complex mount structure which supports the filament at frequent intervals is required, and the classic 'squirrel-cage' construction was first introduced with the commercialisation of tantalum lamps.",
						"One of the primary limitations of tantalum lamps is their unsuitability for operation on AC circuits. The rapid expansion and contraction of the filament as it follows the sinusoidal current flow leads to structural changes within the filament. The wire increases in length, becomes strongly facetted, and shows a tendency to twist which can lead to short-circuiting of adjacent pieces of filament and premature failure. Nevertheless, their advantage in efficacy over the carbon lamp was so profound that in many cases they were still employed on AC circuits, with a consequent reduction in useful life.",
						"The success of tantalum lamps was relatively short-lived, because in the same decade as their invention they were usurped by the still more efficient tungsten filament. Siemens & Halske at first denied the superiority of the tungsten lamp and persisted with the manufacture of tantalum models until about 1913, but elsewhere, tantalum lamps were made obsolete around 1910. On account of their brief period of manufacture, there are very few surviving examples of tantalum lamps."
					]
				},
				{
					intros: [
						["Siemens", "32CP", "British-made with spherical shape bulb", "1908-1913"],
						["Siemens", "50CP", "British-made with double cage filament mount", "1913?"],
						["Westinghouse", "50W", "American-made for use in Mirroscope", "1907-1910"],
						["GE", "25W", "American-made with unusual filament mount", "1909"],
						["Siemens", "25HC", 'German-made with "Focus" type filament', "1912?"]
					],
					pictures: [
						"/t IN TA Siemens Globe 32CP.jpg",
						"/t IN TA Siemens Double Cage.jpg",
						"/t IN TA Westinghouse 50W.jpg",
						"/t IN TA GE 25W.jpg",
						"/t IN TA Siemens Globe Focus.jpg"
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
					title: "钽丝白炽灯",
					description: [
						"钽丝灯是碳丝灯的首个广泛成功的替代品。它的发明归功于德国柏林莫阿比特西门子与哈尔斯克实验室的Werner von Bolton博士和Otto Feuerlein博士。尽管他们的第一盏灯是在1902年12月制造的，但直到1905年才开始生产。与碳相比，钽的蒸气压较低，这使得灯丝可以在相同的使用寿命下以更高的温度运行。这使得其效率约为6 lm/W，是碳丝灯的两倍，同时发出更白的光。",
						"金属灯丝的机械性能与碳丝有很大不同，不具备相同的刚性和弹性。碳丝可以被制成特定的形状，并且在被加热到白炽温度时形状不会改变，而金属灯丝在重力的影响下会迅速下垂。需要一个复杂的支撑结构来在频繁的间隔处支撑灯丝，经典的“松鼠笼”结构就是随着钽丝灯的商业化首次引入的。",
						"钽丝灯的一个主要限制是它们不适合在交流电路中使用。灯丝随着正弦电流流动而快速膨胀和收缩，导致灯丝内部结构发生变化。灯丝会变长，变得严重分面，并且有扭曲的倾向，这可能导致相邻灯丝部分短路，从而提前失效。然而，它们与碳丝灯相比在效率上的优势如此显著，以至于在许多情况下，它们仍然被用于交流电路，尽管这会降低其使用寿命。",
						"钽丝灯的成功是相对短暂的，因为在其发明的同十年代，它们就被更高效的钨丝灯取代了。西门子与哈尔斯克最初否认钨丝灯的优越性，并一直生产钽丝灯，直到大约1913年，但在其他地方，钽丝灯在1910年左右就已经过时了。由于其生产时间短暂，现存的钽丝灯非常稀少。"
					]
				},
				{
					intros: [
						["Siemens", "32CP", "British-made with spherical shape bulb", "1908-1913"],
						["Siemens", "50CP", "British-made with double cage filament mount", "1913?"],
						["Westinghouse", "50W", "American-made for use in Mirroscope", "1907-1910"],
						["GE", "25W", "American-made with unusual filament mount", "1909"],
						["Siemens", "25HC", 'German-made with "Focus" type filament', "1912?"]
					],
					pictures: [
						"/t IN TA Siemens Globe 32CP.jpg",
						"/t IN TA Siemens Double Cage.jpg",
						"/t IN TA Westinghouse 50W.jpg",
						"/t IN TA GE 25W.jpg",
						"/t IN TA Siemens Globe Focus.jpg"
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
