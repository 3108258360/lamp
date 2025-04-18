<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Tungsten Halogen - Double Ended",
					description: [
						"The original and oldest category of halogen lamps is the Double-Ended design, in which a quartz tube is sealed at both ends around a tungsten filament. The linear filament has optical advantageous for certain applications, but the length of these lamps is not always convenient from the mechanical and optical point of view. Also in terms of cost, two seals have to be made, and two lampholders are required. For this reason the original double ended halogen lamps on this page have, in many applications, gradually been superseded by the more compact and lower cost Single-Ended halogen lamps.",
						"In a few cases however, the double-ended design continues to offer advantages over single ended lamps. For high power floodlighting the small diameter and linear filament design is optically preferable. Additionally, double ended capsules are frequently embodied within other lamp envelopes. For instance in the case of high-efficacy lamps having infra-red reflective coatings, it is found that the double-ended design allows greater precision in focussing the filament at the optimum position."
					]
				},
				{
					intros: [
						["GE", "500W", "First Generation Iodine Quartzline Q500T3/CL", "1964"],
						["GE", "420W", '2⅝" Type FAL (A1/227) First Halogen for O.H.P.', "1966"],
						["Philips", "300W", "Linear Halogen K/9 with Fuse Chambers", "1985"],
						["Thorn EMI", "100W", "Linear Halogen K/14 for Universal Burning", "1989"]
					],
					pictures: [
						"/t TH DE GE Q500T3CL.jpg",
						"/t TH DE P Q420T4C-120 FAL GE.jpg",
						"/t TH DE Q300T10C-245 Fuse Chamber Philips.jpg",
						"/t TH DE Thorn Q100T10CL-245 K14.jpg"
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
					title: "钨丝卤素-双端",
					description: [
						"最原始且最早的卤素灯类别是双端设计，即在钨丝的两端密封一个石英管。这种线性灯丝在某些应用中具有光学优势，但这些灯的长度从机械和光学角度来看并不总是方便的。从成本角度来看，需要制作两个密封，并且需要两个灯座。因此，本页面上的原始双端卤素灯在许多应用中逐渐被更紧凑且成本更低的单端卤素灯所取代。",
						"然而，在某些情况下，双端设计仍然比单端灯具有优势。对于高功率泛光照明，较小的直径和线性灯丝设计在光学上更为优越。此外，双端灯泡经常被嵌入其他灯的外壳中。例如，在具有红外反射涂层的高效率灯中，发现双端设计可以更精确地将灯丝定位在最佳位置。"
					]
				},
				{
					intros: [
						["GE", "500W", "First Generation Iodine Quartzline Q500T3/CL", "1964"],
						["GE", "420W", '2⅝" Type FAL (A1/227) First Halogen for O.H.P.', "1966"],
						["Philips", "300W", "Linear Halogen K/9 with Fuse Chambers", "1985"],
						["Thorn EMI", "100W", "Linear Halogen K/14 for Universal Burning", "1989"]
					],
					pictures: [
						"/t TH DE GE Q500T3CL.jpg",
						"/t TH DE P Q420T4C-120 FAL GE.jpg",
						"/t TH DE Q300T10C-245 Fuse Chamber Philips.jpg",
						"/t TH DE Thorn Q100T10CL-245 K14.jpg"
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
