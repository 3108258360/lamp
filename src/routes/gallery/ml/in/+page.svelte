<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent Point-Source Lamps",
					description: [
						"Incandescent point-source lamps contain a tiny body which is brought to incandescence by methods other than the passage of an electrical current through a filament. The incandescent target may be heated either by arranging it as the electrode of an electrical discharge, or by radio-frequency induction. As such they combine the advantages of the good colour rendering properties of incandescent lamps, with the small source size of short-arc discharge lamps. The original electrode material was tungsten, but this was later superseded in the higher power lamps by zirconium oxide, which can be operated at higher colour temperature and produces a whiter light. Tungsten continued to be used however in the smaller power lamps, owing to the difficulty of making sufficiently small diameter zirconia electrodes. A later development saw the use of even more refactory tantalum carbide, this being heated by RF induction.",
						"Being based on the incandescence of a heated body, their efficacy is rather low. The temperature can be raised only slightly higher than that in an incandescent lamp due to the problems of electrode evaporation, and blackening of the bulb envelope. This also limits the surface brightness of the electrodes. This category of lamps was rendered completely obsolete following the development of short arc xenon discharge lamps, which offer higher brightness with only very minor sacrifices in colour quality."
					]
				},
				{
					subhead: "Tungsten Incandescent Arc",
					intros: [
						["Ediswan", "150CP", "Point o'lite Tungsten Arc Projection lamp", "~1950"],
						["GE", "330W", "Photo-micrographic Tungsten Arc source", "1958"],
						["Philips", "58W", "Tungsten-Neon Incandescent Arc", "1963"]
					],
					pictures: [
						"/t Ediswan Pointolite.jpg",
						"/t GE Photomicrographic.jpg",
						"/t D IN Philips 408E.jpg"
					]
				},
				{
					subhead: "Zirconium Incandescent Arc",
					intros: [
						["Sylvania", "25W", "B25 Zirconium oxide incandescent arc", "~1960"],
						["Sylvania", "300W", "K300 Zirconium oxide incandescent arc", "~1965"]
					],
					pictures: ["/t Sylvania Zirconia B25.jpg", "/t Sylvania K300.jpg"]
				},
				{
					subhead: "Tantalum Carbide Induction",
					intros: [["Sylvania", "", "AN-2 Radio Frequency Induction Incandescent", "~1955"]],
					pictures: ["/t IN SP P Sylvania RF.jpg"]
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
					title: "白炽点光源灯",
					description: [
						"白炽点光源灯包含一个微小的物体，通过除电流通过灯丝以外的其他方法使其达到白炽状态。白炽目标可以通过将其设置为电弧放电的电极，或者通过射频感应来加热。因此，它们结合了白炽灯良好的显色性能和短弧放电灯的小光源尺寸的优点。最初的电极材料是钨，但在更高功率的灯中，后来被二氧化锆取代，后者可以在更高的色温下工作，并产生更白的光。然而，由于制造足够小直径的氧化锆电极的困难，钨仍在较小功率的灯中继续使用。后来的发展中，使用了更耐高温的碳化钽，通过射频感应加热。",
						"由于基于加热物体的白炽发光，它们的效率相当低。由于电极蒸发和灯泡外壳变黑的问题，温度只能略微提高到略高于白炽灯的温度。这也限制了电极的表面亮度。随着短弧氙气放电灯的发展，这种类型的灯完全被取代，短弧氙气放电灯提供了更高的亮度，而对色彩质量的牺牲非常小。"
					]
				},
				{
					subhead: "钨白炽电弧",
					intros: [
						["Ediswan", "150CP", "Point o'lite Tungsten Arc Projection lamp", "~1950"],
						["GE", "330W", "Photo-micrographic Tungsten Arc source", "1958"],
						["Philips", "58W", "Tungsten-Neon Incandescent Arc", "1963"]
					],
					pictures: [
						"/t Ediswan Pointolite.jpg",
						"/t GE Photomicrographic.jpg",
						"/t D IN Philips 408E.jpg"
					]
				},
				{
					subhead: "二氧化锆白炽电弧",
					intros: [
						["Sylvania", "25W", "B25 Zirconium oxide incandescent arc", "~1960"],
						["Sylvania", "300W", "K300 Zirconium oxide incandescent arc", "~1965"]
					],
					pictures: ["/t Sylvania Zirconia B25.jpg", "/t Sylvania K300.jpg"]
				},
				{
					subhead: "碳化钽感应",
					intros: [["Sylvania", "", "AN-2 Radio Frequency Induction Incandescent", "~1955"]],
					pictures: ["/t IN SP P Sylvania RF.jpg"]
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
