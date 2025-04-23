<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "SLI/H Linear Low Pressure Sodium",
					description: [
						`The Linear Sodium concept was first conceived by BTH Mazda in the mid 1950's. It was an idea that came into existence following some co-operative work on fluorescent lamps of non-circular cross-section that took place between GE of America and BTH, its allied British operation. GE later launched its distinctive "Power-Groove" fluorescent tubes in the USA while BTH adapted the technology for the sodium lamp.`,
						"In all sodium lamps, it is unfortunate that the wavelength of yellow light created by the discharge is heavily absorbed by the hot sodium vapour itself. If a hot sodium lamp is switched off and it is viewed under the light of another sodium lamp, its vapour-filled discharge tube looks distinctly opaque. Therefore, tubes of narrow diameter would seem to be favourable to make it easier for sodium light to escape. However as always in lamp technology, another mechanism works against this - for the efficacy of the sodium discharge is always greatest at the lowest current density, and this of course calls for a tube of large diameter. In all standard lamps, the tube diameter has to be chosen as the best compromise between low current density and light absorption.",
						`What makes the linear sodium concept special is that the discharge tube has a non-circular cross section. Therefore the current density can be made lower while the light can escape more easily because from any given point where it is created, it has to travel a shorter distance through the opaque sodium vapour than it would have to in a circular tube. The greater efficacy allowed discharge tube length to be reduced for each wattage and the awkward U-shape was no longer required (U-bending a sodium discharge tube is a perennial nuisance and source of many problems in lamp production). The crescent-shaped "Power-Groove" section was the initial design, but Thorn Lighting, the successor of BTH Mazda, subsequently adopted a more advanced clover-leaf design in 1966. Various lamps of differing section and thermal insulation method are illustrated here.`
					]
				},
				{
					subhead: "Glass-Sleeved Lamps",
					intros: [
						["Mazda", "60W", "SO/H Linear with triple glass sleeved outer", "1962"],
						["Mazda", "60W", "SO/H Airfield with heated outer jacket", "~1960"]
					],
					pictures: ["/t D SLP Mazda SLI60.jpg", "/t D SLP Mazda SL60 Dimmable.jpg"]
				},
				{
					subhead: "Gold-Coated Lamps",
					intros: [
						["GEC", "175W", "SLI/H with gold film & crescent-shape arc tube", "1961-66"],
						["GEC", "60W", "SLI/H with gold film & German-style arc tube", "1961-66"]
					],
					pictures: ["/t D SLP GEC SLI175 Gold end.jpg", "/t D SLP GEC SLI60 Gold.jpg"]
				},
				{
					subhead: "Semiconductor-Coated Lamps",
					intros: [
						["GEC", "60W", "SLI/H with tin film & crescent-shape arc tube", "1985"],
						["GEC", "160W", "SLI/H with indium film & crescent-shape arc tube", "1984"],
						["GEC", "200W", "SLI/H with tin film & crescent-shape arc tube", "1984"],
						["Atlas", "60W", "SLI/H with indium film & 4-leaf clover arc tube", "1973"],
						["Atlas", "140W", "SLI/H with indium film & 4-leaf clover arc tube", "1971"],
						["Atlas", "200W", "SLI/H with tin film and 4-leaf clover arc tube", "1974"],
						["Thorn", "200W", "SLI-HO High Output with indium & 5-leaf arc tube", "1980"],
						["Osram", "200W", "Na T 200W-3 very high power German lamp", "1978"]
					],
					pictures: [
						"/t D SLP GEC SLI60.jpg",
						"/t D SLP GEC SLI160 end.jpg",
						"/t D SLP GEC SLI200 end.jpg",
						"/t D SLP Atlas SLI60.jpg",
						"/t D SLP Atlas SLI140 end.jpg",
						"/t D SLP Atlas SLI200 end.jpg",
						"/t D SLP Thorn SLI200HO end.jpg",
						"/t D SLP Osram NaT200W-3 end.jpg"
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
					title: "SLI/H 线性低压钠灯",
					description: [
						`线性钠灯的概念最初是由BTH Mazda在20世纪50年代中期构思的。这一想法是在美国通用电气（GE）与其英国关联企业BTH之间就非圆形截面荧光灯开展的一些合作研究之后产生的。后来，GE在美国推出了其独特的“Power-Groove”荧光管，而BTH则将该技术应用于钠灯。`,
						"在所有钠灯中，不幸的是，由放电产生的黄光的波长被炽热的钠蒸气本身大量吸收。如果将一盏炽热的钠灯关闭，并在另一盏钠灯的光线下观察，其充满蒸气的放电管看起来明显不透明。因此，细径管似乎更有利，以便让钠光更容易逸出。然而，正如在灯具技术中总是出现的情况一样，另一种机制与之相悖——因为钠放电的效率在电流密度最低时总是最高的，而这当然需要一个大直径的管子。在所有标准灯具中，管径必须选择为在低电流密度和光吸收之间的最佳折衷方案。",
						`线性钠灯概念的特殊之处在于，其放电管具有非圆形的截面。因此，可以在保持较低电流密度的同时，让光线更容易逸出，因为从其产生处的任意给定点来看，光线穿过不透明的钠蒸气需要经过的距离比在圆形管中要短。更高的效率使得每瓦功率的放电管长度得以缩短，而且不再需要笨拙的U形（在灯具生产中，钠放电管的U形弯曲一直是一个长期的麻烦和许多问题的根源）。最初的设计是新月形的“Power-Groove”截面，但BTH Mazda的继任者Thorn Lighting在1966年随后采用了一种更先进的三叶草形设计。这里展示了一些不同截面和隔热方法的各种灯具。`
					]
				},
				{
					subhead: "带玻璃袖的灯具",
					intros: [
						["Mazda", "60W", "SO/H Linear with triple glass sleeved outer", "1962"],
						["Mazda", "60W", "SO/H Airfield with heated outer jacket", "~1960"]
					],
					pictures: ["/t D SLP Mazda SLI60.jpg", "/t D SLP Mazda SL60 Dimmable.jpg"]
				},
				{
					subhead: "镀金灯具",
					intros: [
						["GEC", "175W", "SLI/H with gold film & crescent-shape arc tube", "1961-66"],
						["GEC", "60W", "SLI/H with gold film & German-style arc tube", "1961-66"]
					],
					pictures: ["/t D SLP GEC SLI175 Gold end.jpg", "/t D SLP GEC SLI60 Gold.jpg"]
				},
				{
					subhead: "半导体涂层灯具",
					intros: [
						["GEC", "60W", "SLI/H with tin film & crescent-shape arc tube", "1985"],
						["GEC", "160W", "SLI/H with indium film & crescent-shape arc tube", "1984"],
						["GEC", "200W", "SLI/H with tin film & crescent-shape arc tube", "1984"],
						["Atlas", "60W", "SLI/H with indium film & 4-leaf clover arc tube", "1973"],
						["Atlas", "140W", "SLI/H with indium film & 4-leaf clover arc tube", "1971"],
						["Atlas", "200W", "SLI/H with tin film and 4-leaf clover arc tube", "1974"],
						["Thorn", "200W", "SLI-HO High Output with indium & 5-leaf arc tube", "1980"],
						["Osram", "200W", "Na T 200W-3 very high power German lamp", "1978"]
					],
					pictures: [
						"/t D SLP GEC SLI60.jpg",
						"/t D SLP GEC SLI160 end.jpg",
						"/t D SLP GEC SLI200 end.jpg",
						"/t D SLP Atlas SLI60.jpg",
						"/t D SLP Atlas SLI140 end.jpg",
						"/t D SLP Atlas SLI200 end.jpg",
						"/t D SLP Thorn SLI200HO end.jpg",
						"/t D SLP Osram NaT200W-3 end.jpg"
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
