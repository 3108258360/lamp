<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Carbon Filament lamp",
					description: [
						"The carbon filament lamp was the first practical form of incandescent lamp, this material originally being favoured because of the possibility to operate it at temperatures higher than any other electrical conductor that could be produced in filamentary forms at the time. Higher temperature is the continual goal of the incandescent lamp engineer, owing to the fact that the efficiency of conversion of electrical energy into visible light increases under such conditions.",
						"For more than two decades carbon held court as the filament material of choice, but at the beginning of the twentieth century developments in metallurgy enabled the production of metal wires that could be driven at higher temperatures. This resulted in the near-total disappearance of the carbon lamp by 1910. Due to its superior resistance to mechanical shocks than the brittle metallic filaments, it took a little longer to displace in some industrial and vibration-service applications, and its advantages as an infra-red source saw its limited manufacture for some heating appliances. Most curiously its popularity began to rise again after the 1990s, as a light source for decorative applications thanks to its warm glow with a colour similar to candlelight."
					]
				},
				{
					subhead: "American Lamps",
					intros: [
						[
							"Edison",
							"~16CP",
							"First Commercial Lamp, Bristol Board Filament",
							"1879-1880  /  1928-30"
						],
						["Edison", "16CP", "Bamboo Filament with Copper Clamps", "1884-1886"],
						["BrushSwan", "16CP", "Original stem design with Swan Bayonet Cap", "1885-93"],
						["BrushSwan", "16CP", "Later stem design with Thomson-Houston Cap", "1893-95"],
						["Edison", "16CP", "New Type with Cellulose Filament", "1893-1899"],
						["Packard?", "16CP", "Pollard non-infringing lamp with silver film seal", "1892-1894"],
						["Novak", "16CP", "Bromine-Filled Carbon Filament Lamp", "1893-1894"],
						["Ft.Wayne", "16CP", "Adams-Bagnall Style Tipless Lamp", "1897-1898"]
					],
					pictures: [
						"t IN C Edison 1879.jpg",
						"t IN C Edison 1884.jpg",
						"t IN C Brush-Swan BC.jpg",
						"t IN C Brush-Swan TH.jpg",
						"t IN C Edison New Type.jpg",
						"t IN C Pollard TH.jpg",
						"t IN C Novak.jpg",
						"t IN C FtWayne A-B.jpg"
					]
				},
				{
					subhead: "British Lamps",
					intros: [
						["Lane-Fox", "20CP", "Lane-Fox Carbon Lamp with Mercury Seals", "1882"],
						["Maxim", "~5CP", "Maxim Carbon Lamp of suspected British Origin", "1883-90"],
						["Robertson", "8CP", "2nd Generation of Vitrite Cap with Brass Ring", "1901-1902"]
					],
					pictures: ["t IN C Lane-Fox.jpg", "t IN C Maxim.jpg", "t IN C Robertson Vitrite Mk2.jpg"]
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
					title: "碳丝灯",
					description: [
						"碳丝灯是第一种实用的白炽灯形式，这种材料最初受到青睐是因为它可以在比当时任何其他能制成灯丝形状的导体更高的温度下工作。更高的温度一直是白炽灯工程师的持续目标，因为在这种情况下，电能转化为可见光的效率会提高。",
						"二十多年来，碳一直是首选的灯丝材料，但在二十世纪初，冶金技术的发展使得能够生产出可以在更高温度下工作的金属丝。这导致碳丝灯在1910年几乎完全消失。由于其比易碎的金属灯丝更具抗机械冲击性，它在一些工业和振动服务应用中被取代的时间稍长一些，其作为红外线源的优势也使其在一些加热器具中有限地生产。最奇怪的是，20世纪90年代后，它的受欢迎程度又开始上升，作为一种装饰性光源，其温暖的光芒颜色类似于烛光。"
					]
				},
				{
					subhead: "美国灯",
					intros: [
						[
							"Edison",
							"~16CP",
							"First Commercial Lamp, Bristol Board Filament",
							"1879-1880  /  1928-30"
						],
						["Edison", "16CP", "Bamboo Filament with Copper Clamps", "1884-1886"],
						["BrushSwan", "16CP", "Original stem design with Swan Bayonet Cap", "1885-93"],
						["BrushSwan", "16CP", "Later stem design with Thomson-Houston Cap", "1893-95"],
						["Edison", "16CP", "New Type with Cellulose Filament", "1893-1899"],
						["Packard?", "16CP", "Pollard non-infringing lamp with silver film seal", "1892-1894"],
						["Novak", "16CP", "Bromine-Filled Carbon Filament Lamp", "1893-1894"],
						["Ft.Wayne", "16CP", "Adams-Bagnall Style Tipless Lamp", "1897-1898"]
					],
					pictures: [
						"t IN C Edison 1879.jpg",
						"t IN C Edison 1884.jpg",
						"t IN C Brush-Swan BC.jpg",
						"t IN C Brush-Swan TH.jpg",
						"t IN C Edison New Type.jpg",
						"t IN C Pollard TH.jpg",
						"t IN C Novak.jpg",
						"t IN C FtWayne A-B.jpg"
					]
				},
				{
					subhead: "英国灯",
					intros: [
						["Lane-Fox", "20CP", "Lane-Fox Carbon Lamp with Mercury Seals", "1882"],
						["Maxim", "~5CP", "Maxim Carbon Lamp of suspected British Origin", "1883-90"],
						["Robertson", "8CP", "2nd Generation of Vitrite Cap with Brass Ring", "1901-1902"]
					],
					pictures: ["t IN C Lane-Fox.jpg", "t IN C Maxim.jpg", "t IN C Robertson Vitrite Mk2.jpg"]
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
