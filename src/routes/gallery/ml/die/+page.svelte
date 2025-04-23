<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Dielectric Barrier Discharge",
					description: [
						"Dielectric Barrier lamps are discharge light sources having electrodes, but in which there is no direct contact between the discharge and the electrodes. They are separated, as the name implies, by a dielectric material and power is coupled capacitively into the discharge.",
						"One of the advantages of this technique is that the electrodes operate at much lower temperatures, and they are not exposed to reactive species which may lead to their degradation over time. As such the lifetime of dielectric barrier discharge lamps can be made extremely long, but the power density is typically lower than other discharge lamps. Another advantage is that since no time is required for the electrodes to heat up and for the lamp to stabilise, light is produced instantaneously. The different electrical characteristics of the discharge also enable the effective creation of mercury-free lamps, this toxic metal unfortunately being necessary in virtually all other discharge lamps.",
						"The complexity of the resulting lamps is however relatively high, and this results in rather high manufacturing costs. Efficacy is also somewhat lower than competitive discharge lamps, and despite several efforts the dielectric barrier lamps have struggled to gain a foothold in the market. Today they remain popular only in a few applications, such as instant-light photocopier and scanner lamps, and for the production of very short wavelength UV radiation."
					]
				},
				{
					intros: [["Osram", "68W", "Planon Dielectric Barrier Discharge Fluorescent", "2000"]],
					pictures: ["/t Osram Planon.jpg"]
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
					title: "介质阻挡放电",
					description: [
						"介质阻挡灯是一种具有电极的放电光源，但放电与电极之间没有直接接触。正如名称所示，它们被介质材料隔开，功率通过电容耦合的方式输入到放电中。",
						"这种技术的一个优点是电极的工作温度要低得多，而且它们不会接触到可能导致其随时间退化的活性物质。因此，介质阻挡放电灯的使用寿命可以做得非常长，但其功率密度通常低于其他放电灯。另一个优点是，由于不需要电极加热和灯稳定的时间，因此可以瞬间产生光。放电的不同电气特性还使得有效制造无汞灯成为可能，这种有毒金属几乎在所有其他放电灯中都是必需的。",
						"然而，由此产生的灯的复杂性相对较高，这导致了相当高的制造成本。其效率也略低于竞争性的放电灯，尽管经过多次努力，介质阻挡灯在市场上的立足仍然很困难。如今，它们仅在少数应用中仍然受欢迎，例如瞬间点亮的复印机和扫描仪灯，以及用于产生极短波长紫外线辐射。"
					]
				},
				{
					intros: [["Osram", "68W", "Planon Dielectric Barrier Discharge Fluorescent", "2000"]],
					pictures: ["/t Osram Planon.jpg"]
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
