<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Early Sodium Lamp Designs",
					description: [
						"This page features some of the earliest designs of low pressure sodium lamps. The original versions were only made in small quantities and were often more laboratory curiosities than commercially significant products. As such a very broad variety of different types was created. By 1932 however, most of the worlds manufacturers had arrived at the optimum design for this category of lamp, and the below types were superseded by the SO/H lamps having a positive column discharge in a U-bent tube."
					]
				},
				{
					subhead: "Low Voltage DC",
					intros: [
						["Philips", "82W", "Philora DC 4000lm - First Sodium Lamp", "1932"],
						["Philips", "82W", "Philora DC 500lm - Small Polarimeter Lamp", "~1940"]
					],
					pictures: ["/t D SLP Philora 4000lm.jpg", "/t Philips Philora Sodium DC.jpg"]
				},
				{
					subhead: "Low Voltage AC",
					intros: [
						["GE", "190W", "NA-9 10,000lm - American-style Lamp", "1952"],
						["GE", "28W", "NA-1 650lm - Small AC Lab-Arc Sodium Lamp", "1960"]
					],
					pictures: ["/t D SLP GE NA9 with asbestos.jpg", "/t D SLP GE NA-1.jpg"]
				},
				{
					subhead: "High Voltage AC",
					intros: [
						["Philips", "80W", "Philora DO80 Positive Column Cold-Starting", "1932"],
						["Philips", "80W", "Philora SO500 Positive Column Self-Starting", "c. 1935-1940"]
					],
					pictures: ["/t D SLP Philora DO80.jpg", "/t Philips SO300.jpg"]
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
					title: "早期钠灯设计",
					description: [
						"本页面展示了一些最早的低压钠灯设计。最初版本的产量很小，通常更像是实验室的奇珍异品，而非具有商业意义的产品。因此，出现了各种各样的不同类型。然而到了1932年，世界上大多数制造商已经确定了此类灯具的最佳设计，以下类型被具有正柱放电的U形弯管的SO/H灯具所取代。"
					]
				},
				{
					subhead: "低压直流",
					intros: [
						["Philips", "82W", "Philora DC 4000lm - First Sodium Lamp", "1932"],
						["Philips", "82W", "Philora DC 500lm - Small Polarimeter Lamp", "~1940"]
					],
					pictures: ["/t D SLP Philora 4000lm.jpg", "/t Philips Philora Sodium DC.jpg"]
				},
				{
					subhead: "低压交流",
					intros: [
						["GE", "190W", "NA-9 10,000lm - American-style Lamp", "1952"],
						["GE", "28W", "NA-1 650lm - Small AC Lab-Arc Sodium Lamp", "1960"]
					],
					pictures: ["/t D SLP GE NA9 with asbestos.jpg", "/t D SLP GE NA-1.jpg"]
				},
				{
					subhead: "高压交流",
					intros: [
						["Philips", "80W", "Philora DO80 Positive Column Cold-Starting", "1932"],
						["Philips", "80W", "Philora SO500 Positive Column Self-Starting", "c. 1935-1940"]
					],
					pictures: ["/t D SLP Philora DO80.jpg", "/t Philips SO300.jpg"]
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
