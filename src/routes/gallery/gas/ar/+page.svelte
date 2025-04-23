<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Argon Discharge Lamps",
					description: [
						"Argon discharge lamps exist primarily in the negative glow format, and are a spin-off from the popular series of neon glow versions.  They once enjoyed some popularity in the USA, and for many years GE manufactured a number of argon-filled equivalents of its broad range of standard neon glow lamps.",
						"The principal application of the argon discharge is as a small source of ultraviolet radiation.  On account of the very small amount of radiation that can be produced by this method, their applications were of course limited and rather specialised.  In nearly all cases the mercury discharge is a much more efficient source of UV radiation.  But mercury lamps are rather difficult to manufacture in extremely low power ratings of less than about one watt, and below that limit the argon lamp was favoured.  They found a number of niches in special military service, but one version, the AR-1 was sold in large numbers for the identification of fluorescent rocks and minerals."
					]
				},
				{
					intros: [["GE", "2W", "AR-1 Argon mild ultra-violet source", "~1960"]],
					pictures: ["/t GE AR1.jpg"]
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
					title: "氩放电灯",
					description: [
						"氩放电灯主要以负辉光形式存在，是从流行的氖负辉光灯系列衍生出来的。它们曾经在美国享有一些知名度，多年来，通用电气公司制造了许多其广泛的标准氖负辉光灯的氩填充等效产品。",
						"氩放电的主要应用是作为紫外线辐射的小型来源。由于通过这种方法产生的辐射量非常小，因此其应用当然有限且相当专业。在几乎所有情况下，汞放电是紫外线辐射的更有效来源。但汞灯在制造功率极低（小于约1瓦）的灯时相当困难，在这种情况下，氩灯更受青睐。它们在特殊军事服务中找到了一些利基市场，但其中一种型号，AR-1，因用于识别荧光岩石和矿物而大量销售。"
					]
				},
				{
					intros: [["GE", "2W", "AR-1 Argon mild ultra-violet source", "~1960"]],
					pictures: ["/t GE AR1.jpg"]
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
