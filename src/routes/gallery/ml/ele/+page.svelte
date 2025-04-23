<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Electrodeless Induction Lamps",
					description: [
						"Ever since the great scientist Nikola Tesla stunned his audiences with fabulous demonstrations of induction lighting more than a century ago, lighting firms worldwide have tried to master the technology in an efficient and commercially viable format. There was some activity on the subject in the USA in the late 1970s, but intgrated electronic ballasts and the subject of radio frequency emissions prevented a commercial launch.",
						"In the 1980s the subject of a low-wattage incandescent retrofit lamp was being extensively researched in the labs of Philips and Thorn Lighting, both of whom created advanced prototypes that came very close to a market launch. But the high price of the technology remained a barrier to production. Sylvania in USA meanwhile experimented with large high efficiency tubular sources that offered greater potential for energy savings.",
						"It was not until the early 1990s that Panasonic, then Philips, GE-Thorn and Osram-Sylvania all placed practical lamps on the market. More recent years have seen impressive Chinese dabblings in the art, some of whose lamps are also illustrated below."
					]
				},
				{
					subhead: "Remote Ballasted Lamps",
					intros: [
						["Philips", "85W", "QL Electrodeless Half Coated Demonstration", "1992"],
						["Philips", "85W", "QL Electrodeless Induction System", "2001"],
						["Osram", "100W", "Endura Inductively Coupled Electrodeless", "2002"],
						["Tungda", "85W", "TL85 - First Chinese electrodeless lamp", "2001"],
						["TUE", "1000W", "Electrodeless Sulphur Microwave lamp", "1999"],
						["Stella", "3000W", "Electrodeless Xenon Water-Cooled FB-3000", "1983"]
					],
					pictures: [
						"/t D ED Philips QL85 Halfcoat.jpg",
						"/t Philips QL85 system.jpg",
						"/t Osram Endura100.jpg",
						"/t Tungda TL85.jpg",
						"/t Sulphur.jpg",
						"/t D ED Stella FB-3000.jpg"
					]
				},
				{
					subhead: "Self Ballasted Lamps",
					intros: [
						["Philips", "20W", "XL 20W Advanced Prototype Retrofit Lamp", "1985"],
						["GE-Thorn", "23W", "Advanced prototype self-ballasted electrodeless", "1991"],
						["GE Lighting", "23W", "Genura Self-ballasted electrodeless reflector", "1994"],
						["National", "12W", "Matsushita Electrodeless Pa-Look Ball YOU", "2003"],
						["Hongyuan", "60W", "Saturn 2 Self-ballasted Chinese electrodeless", "2003"],
						["Sylvania", "20W", "Dura-One Self-ballasted Electrodeless A-shape", "2008"]
					],
					pictures: [
						"/t Philips XL20.jpg",
						"/t GE Proto2.jpg",
						"/t GE Genura.jpg",
						"/t National PFA15.jpg",
						"/t Hongyuan Saturn 40.jpg",
						"/t D ED Sylvania DuraOne.jpg"
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
					title: "无极感应灯",
					description: [
						"自伟大的科学家尼古拉·特斯拉一个多世纪前以精彩的感应照明演示令观众惊叹不已以来，全球的照明公司一直在努力将这项技术以高效且商业可行的形式掌握下来。20世纪70年代末，美国在这方面曾有一些活动，但集成电子镇流器以及射频辐射的问题阻碍了商业推广。",
						"在20世纪80年代，飞利浦和索恩照明的实验室对低功率白炽灯替代灯进行了广泛的研究，他们都制造出了接近推向市场的先进原型。但技术的高成本仍然是生产的障碍。与此同时，美国的西凡尼亚公司试验了大型高效率管状光源，这种光源在节能方面具有更大的潜力。",
						"直到20世纪90年代初，松下、飞利浦、GE-索恩和欧司朗-西凡尼亚才将实用的灯具推向市场。近年来，中国在这一领域也有所尝试，并取得了令人瞩目的成绩，下面也展示了一些中国的灯具。"
					]
				},
				{
					subhead: "外置镇流灯",
					intros: [
						["Philips", "85W", "QL Electrodeless Half Coated Demonstration", "1992"],
						["Philips", "85W", "QL Electrodeless Induction System", "2001"],
						["Osram", "100W", "Endura Inductively Coupled Electrodeless", "2002"],
						["Tungda", "85W", "TL85 - First Chinese electrodeless lamp", "2001"],
						["TUE", "1000W", "Electrodeless Sulphur Microwave lamp", "1999"],
						["Stella", "3000W", "Electrodeless Xenon Water-Cooled FB-3000", "1983"]
					],
					pictures: [
						"/t D ED Philips QL85 Halfcoat.jpg",
						"/t Philips QL85 system.jpg",
						"/t Osram Endura100.jpg",
						"/t Tungda TL85.jpg",
						"/t Sulphur.jpg",
						"/t D ED Stella FB-3000.jpg"
					]
				},
				{
					subhead: "自镇流灯",
					intros: [
						["Philips", "20W", "XL 20W Advanced Prototype Retrofit Lamp", "1985"],
						["GE-Thorn", "23W", "Advanced prototype self-ballasted electrodeless", "1991"],
						["GE Lighting", "23W", "Genura Self-ballasted electrodeless reflector", "1994"],
						["National", "12W", "Matsushita Electrodeless Pa-Look Ball YOU", "2003"],
						["Hongyuan", "60W", "Saturn 2 Self-ballasted Chinese electrodeless", "2003"],
						["Sylvania", "20W", "Dura-One Self-ballasted Electrodeless A-shape", "2008"]
					],
					pictures: [
						"/t Philips XL20.jpg",
						"/t GE Proto2.jpg",
						"/t GE Genura.jpg",
						"/t National PFA15.jpg",
						"/t Hongyuan Saturn 40.jpg",
						"/t D ED Sylvania DuraOne.jpg"
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
