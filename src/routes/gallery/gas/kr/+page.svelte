<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Krypton Discharge Lamps",
					description: [
						"Krypton discharge lamps exist primarily only in the high wattage long arc format. It is a lamp that evolved out of the laser science business, and they have only one application - the optical pumping of Neodymium : YAG lasers. Their strong shortwave infra-red radiation between 750 and 900nm is perfectly suited to this application in which the Nd:YAG crystals are strongly absorbing.",
						"As a light source the krypton discharge is rather inefficient, achieving only some 30 lumens per watt. Like xenon, its emission spectrum is fairly well balanced over the visible 380-780nm range, thus the light has a whiteish appearance and the colour rendering properties are good by comparison with other pure gas discharge lamps."
					]
				},
				{
					intros: [["Osram", "2500W", "KBF long arc lamp for pumping Nd:YAG lasers", ""]],
					pictures: ["/t Osram KBF.jpg"]
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
					title: "氪放电灯",
					description: [
						"氪放电灯主要仅存在于高功率长弧形式。这种灯是从激光科学业务中演变而来的，它们只有一个应用——光学激励掺钕钇铝石榴石（Nd:YAG）激光器。其在750到900纳米之间的强短波红外辐射非常适合这一应用，因为Nd:YAG晶体在这一波段有很强的吸收。",
						"作为光源，氪放电灯的效率相当低，每瓦特仅能达到约30流明。与氙气类似，其发射光谱在可见光380-780纳米范围内分布较为平衡，因此光呈现出白色，并且与其它纯气体放电灯相比，其显色性能较好。"
					]
				},
				{
					intros: [["Osram", "2500W", "KBF long arc lamp for pumping Nd:YAG lasers", ""]],
					pictures: ["/t Osram KBF.jpg"]
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
