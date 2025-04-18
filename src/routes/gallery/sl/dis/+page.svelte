<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "LED - Discrete Devices",
					description: [
						"This page features the category of Discrete LED lamps - in other words an individual LED Emitter on its own, consisting of a single semiconductor die or multiple dice encapsulated in the necessary packaging materials. Owing to the typically low output of discrete LED emitters, multiple such devices are often combined in a single lamp. They may additionally require other optical, thermal, mechanical and electronic components for their satisfactory operation. Lamps that contain a plurality of LED emitters, or consist of LEDs combined with other functional components can be found under the separate section of Integrated LED Lamps."
					]
				},
				{
					intros: [
						["GE", "SSL-1", "Silicon Carbide Yellow LED", "~1967-69"],
						["GE", "SSL-6", "Silicon Carbide Yellow LED", "~1968-69"],
						["Monsanto", "MV1", "First Commercial Solid State Lamp", "~1968-75"],
						["GE", "SSL-5A", "GaAs Silicon-doped Infrared LED", "~1970"],
						["Thorn", "49-1101", "GaAsP Red with Mesa-type Die Construction", "~1972-75"],
						["Thorn", "49-1121", "GaAsP Yellow with Mesa-type Die Construction", "~1973-75"],
						["Philips ?", "", "Large Junction Red device of early design", "~1975"],
						["NIIPP", "AL360B", "Green LED using Anti-Stokes Phosphor", "1993"],
						["Fairchild", "FLV102", "High Contrast Diffuse Red Ceramic Base", "~1970s"],
						["HP", "5082-4403", "Early T-1� Package with Metal Flange", "~1971-76"]
					],
					pictures: [
						"/t LED GE SSL-1 front.jpg",
						"/t LED GE SSL-6 front.jpg",
						"/t LED Monsanto MV1.jpg",
						"/t LED GE SSL-5.jpg",
						"/t LED Thorn TO-18 Red.jpg",
						"/t LED Thorn TO-18 Yellow.jpg",
						"/t LED Philips TO-46.jpg",
						"/t LED Soviet AL360B.jpg",
						"/t LED Fairchild FLV102.jpg",
						"/t LED HP 5082-4403.jpg"
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
					title: "LED - 分立器件",
					description: [
						"本页面介绍的是分立式LED灯具类别，即单独的LED发射器，由单个半导体芯片或多个芯片封装在必要的包装材料中组成。由于分立式LED发射器的输出功率通常较低，因此通常会在单个灯具中组合多个这样的设备。它们可能还需要其他光学、热学、机械和电子元件才能正常工作。包含多个LED发射器的灯具，或者由LED与其他功能组件组合而成的灯具，可以在单独的集成式LED灯具部分找到。"
					]
				},
				{
					intros: [
						["GE", "SSL-1", "Silicon Carbide Yellow LED", "~1967-69"],
						["GE", "SSL-6", "Silicon Carbide Yellow LED", "~1968-69"],
						["Monsanto", "MV1", "First Commercial Solid State Lamp", "~1968-75"],
						["GE", "SSL-5A", "GaAs Silicon-doped Infrared LED", "~1970"],
						["Thorn", "49-1101", "GaAsP Red with Mesa-type Die Construction", "~1972-75"],
						["Thorn", "49-1121", "GaAsP Yellow with Mesa-type Die Construction", "~1973-75"],
						["Philips ?", "", "Large Junction Red device of early design", "~1975"],
						["NIIPP", "AL360B", "Green LED using Anti-Stokes Phosphor", "1993"],
						["Fairchild", "FLV102", "High Contrast Diffuse Red Ceramic Base", "~1970s"],
						["HP", "5082-4403", "Early T-1� Package with Metal Flange", "~1971-76"]
					],
					pictures: [
						"/t LED GE SSL-1 front.jpg",
						"/t LED GE SSL-6 front.jpg",
						"/t LED Monsanto MV1.jpg",
						"/t LED GE SSL-5.jpg",
						"/t LED Thorn TO-18 Red.jpg",
						"/t LED Thorn TO-18 Yellow.jpg",
						"/t LED Philips TO-46.jpg",
						"/t LED Soviet AL360B.jpg",
						"/t LED Fairchild FLV102.jpg",
						"/t LED HP 5082-4403.jpg"
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
