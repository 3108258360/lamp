<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Spectral Line Sources",
					description: [
						"Spectral lamps find a home in special laboratory applications where they are commonly employed as stable, high quality sources of discrete spectral lines. Atomic spectra were originally produced either by creating an arc between electrodes fabricated of the metal to be studied, or by sprinkling a powdered salt into an ordinary gas flame. Both methods produce somewhat unstable results and require constant attention. In the 1940s a range of electric discharge lamps was therefore developed to supersede these crude methods, and could guarantee superior results by virtue of the high purity of the metals contained within the discharge tube."
					]
				},
				{
					subhead: "Osram Spectral Series",
					intros: [
						["Osram", "He", "Noble Gas Lamp Helium discharge", "~1960"],
						["Osram", "Ne", "Noble Gas Lamp Neon discharge", "~1960"],
						["Osram", "Na", "Alkali Metal Lamp Sodium Vapour", "~1960"],
						["Osram", "K", "Alkali Metal Lamp Potassium Vapour", "~1960"],
						["Osram", "Rb", "Alkali Metal Lamp Rubidium Vapour", "~1960"],
						["Osram", "Cs", "Alkali Metal Lamp Caesium Vapour", "~1960"],
						["Osram", "Hg", "Bivalent Metal Lamp Mercury High Pressure", "~1960"],
						["Osram", "HgS", "Bivalent Metal Lamp UV Mercury High Pressure", "~1960"],
						["Osram", "Cd", "Bivalent Metal Lamp Cadmium Vapour", "~1960"],
						["Osram", "Zn", "Bivalent Metal Lamp Zinc Vapour", "~1960"],
						["Osram", "Tl", "Trivalent Metal Lamp Thallium Vapour", "~1960"],
						["Osram", "Hg-Cd", "Mixed Metal Lamp Mercury-Cadmium", "~1960"]
					],
					pictures: [
						"/t Osram Spectral He lit.jpg",
						"/t Osram Spectral Ne lit.jpg",
						"/t Osram Spectral Na lit.jpg",
						"/t Osram Spectral K lit.jpg",
						"/t Osram Spectral Rb lit.jpg",
						"/t Osram Spectral Cs lit.jpg",
						"/t Osram Spectral Hg lit.jpg",
						"/t Osram Spectral HgS lit.jpg",
						"/t Osram Spectral Cd lit.jpg",
						"/t Osram Spectral Zn lit.jpg",
						"/t Osram Spectral Tl lit.jpg",
						"/t Osram Spectral HgCd lit.jpg"
					]
				},
				{
					subhead: "Philips Spectral Series",
					intros: [
						["Philips", "He", "Noble Gas Lamp Helium discharge", "1985"],
						["Philips", "Ne", "Noble Gas Lamp Neon discharge", "1985"],
						["Philips", "Ar", "Noble Gas Lamp Argon discharge", "1975"],
						["Philips", "Kr", "Noble Gas Lamp Krypton discharge", "1984"],
						["Philips", "Xe", "Noble Gas Lamp Xenon discharge", "1984"],
						["Philips", "Na", "Alkali Metal Lamp Sodium Vapour", "1986"],
						["Philips", "Rb", "Alkali Metal Lamp Rubidium Vapour", "1987"],
						["Philips", "Hg", "Bivalent Metal Lamp Mercury Low Pressure", "1987"],
						["Philips", "Hg", "Bivalent Metal Lamp Mercury High Pressure", "1982"],
						["Philips", "Cd", "Bivalent Metal Lamp Cadmium Vapour", "1976"],
						["Philips", "Zn", "Bivalent Metal Lamp Zinc Vapour", "1959"],
						["Philips", "Hg", "Quartz Jacketed Lamp Mercury Low Pressure", "1985"],
						["Philips", "Zn", "Quartz Jacketed Lamp Zinc Vapour", "1960"],
						["Philips", "HgCdZn", "Quartz Jacketed Lamp Mercury-Cadmium-Zinc", "1960"],
						["Philips", "Na", "Miniature 4-watt sodium polarimetry lamp", "1981"]
					],
					pictures: [
						"/t Philips LL He.jpg",
						"/t Philips LL Ne.jpg",
						"/t Philips LL Ar.jpg",
						"/t Philips LL Kr.jpg",
						"/t Philips LL Xe.jpg",
						"/t Philips LL Na.jpg",
						"/t Philips LL Rb.jpg",
						"/t Philips LL HgL.jpg",
						"/t Philips LL HgH.jpg",
						"/t Philips LL Cd.jpg",
						"/t Philips LL Zn.jpg",
						"/t Philips LL QHgL.jpg",
						"/t Philips LL QZn.jpg",
						"/t Philips LL QHgCdZn.jpg",
						"/t Philips Polarimeter.jpg"
					]
				},
				{
					subhead: "GEC 'Osira' Spectral Series",
					intros: [
						["Osram-GEC", "", "SL/D 1.3 Sodium Spectral Source", "1961"],
						["Osram-GEC", "", "ML/D 2.0 Mercury Spectral Source", "1964"],
						["Osram-GEC", "", "CL/D 2.0 Cadmium Spectral Source", "~1955"],
						["Osram-GEC", "", "CML/D 2.0 Cadmium & Mercury Spectral Source", "1962"]
					],
					pictures: ["/t GEC SLD1.jpg", "/t GEC MLD2.jpg", "/t Osram CLD2.jpg", "/t GEC CMLD2.jpg"]
				},
				{
					subhead: "GE American Lab-Arc Series",
					intros: [
						["GE", "", "NA-1 Sodium Lab-Arc Spectral Source", "1960"],
						["GE", "85W", "H85A3/UV Lab-Arc Ultraviolet Source", "1952"]
					],
					pictures: ["/t GE NA1.jpg", "/t GE H85UV.jpg"]
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
					title: "光谱线光源",
					description: [
						"光谱灯在特殊的实验室应用中找到了用武之地，它们通常被用作稳定、高质量的离散光谱线光源。原子光谱最初是通过在由待研究金属制成的电极之间产生电弧，或者将粉末状盐撒入普通气体火焰中产生的。这两种方法产生的结果都有些不稳定，需要持续关注。因此，在20世纪40年代开发了一系列电弧放电灯，以取代这些粗糙的方法，并且由于放电管内所含金属的高纯度，能够保证更优越的结果。"
					]
				},
				{
					subhead: "欧司朗光谱系列",
					intros: [
						["Osram", "He", "Noble Gas Lamp Helium discharge", "~1960"],
						["Osram", "Ne", "Noble Gas Lamp Neon discharge", "~1960"],
						["Osram", "Na", "Alkali Metal Lamp Sodium Vapour", "~1960"],
						["Osram", "K", "Alkali Metal Lamp Potassium Vapour", "~1960"],
						["Osram", "Rb", "Alkali Metal Lamp Rubidium Vapour", "~1960"],
						["Osram", "Cs", "Alkali Metal Lamp Caesium Vapour", "~1960"],
						["Osram", "Hg", "Bivalent Metal Lamp Mercury High Pressure", "~1960"],
						["Osram", "HgS", "Bivalent Metal Lamp UV Mercury High Pressure", "~1960"],
						["Osram", "Cd", "Bivalent Metal Lamp Cadmium Vapour", "~1960"],
						["Osram", "Zn", "Bivalent Metal Lamp Zinc Vapour", "~1960"],
						["Osram", "Tl", "Trivalent Metal Lamp Thallium Vapour", "~1960"],
						["Osram", "Hg-Cd", "Mixed Metal Lamp Mercury-Cadmium", "~1960"]
					],
					pictures: [
						"/t Osram Spectral He lit.jpg",
						"/t Osram Spectral Ne lit.jpg",
						"/t Osram Spectral Na lit.jpg",
						"/t Osram Spectral K lit.jpg",
						"/t Osram Spectral Rb lit.jpg",
						"/t Osram Spectral Cs lit.jpg",
						"/t Osram Spectral Hg lit.jpg",
						"/t Osram Spectral HgS lit.jpg",
						"/t Osram Spectral Cd lit.jpg",
						"/t Osram Spectral Zn lit.jpg",
						"/t Osram Spectral Tl lit.jpg",
						"/t Osram Spectral HgCd lit.jpg"
					]
				},
				{
					subhead: "飞利浦光谱系列",
					intros: [
						["Philips", "He", "Noble Gas Lamp Helium discharge", "1985"],
						["Philips", "Ne", "Noble Gas Lamp Neon discharge", "1985"],
						["Philips", "Ar", "Noble Gas Lamp Argon discharge", "1975"],
						["Philips", "Kr", "Noble Gas Lamp Krypton discharge", "1984"],
						["Philips", "Xe", "Noble Gas Lamp Xenon discharge", "1984"],
						["Philips", "Na", "Alkali Metal Lamp Sodium Vapour", "1986"],
						["Philips", "Rb", "Alkali Metal Lamp Rubidium Vapour", "1987"],
						["Philips", "Hg", "Bivalent Metal Lamp Mercury Low Pressure", "1987"],
						["Philips", "Hg", "Bivalent Metal Lamp Mercury High Pressure", "1982"],
						["Philips", "Cd", "Bivalent Metal Lamp Cadmium Vapour", "1976"],
						["Philips", "Zn", "Bivalent Metal Lamp Zinc Vapour", "1959"],
						["Philips", "Hg", "Quartz Jacketed Lamp Mercury Low Pressure", "1985"],
						["Philips", "Zn", "Quartz Jacketed Lamp Zinc Vapour", "1960"],
						["Philips", "HgCdZn", "Quartz Jacketed Lamp Mercury-Cadmium-Zinc", "1960"],
						["Philips", "Na", "Miniature 4-watt sodium polarimetry lamp", "1981"]
					],
					pictures: [
						"/t Philips LL He.jpg",
						"/t Philips LL Ne.jpg",
						"/t Philips LL Ar.jpg",
						"/t Philips LL Kr.jpg",
						"/t Philips LL Xe.jpg",
						"/t Philips LL Na.jpg",
						"/t Philips LL Rb.jpg",
						"/t Philips LL HgL.jpg",
						"/t Philips LL HgH.jpg",
						"/t Philips LL Cd.jpg",
						"/t Philips LL Zn.jpg",
						"/t Philips LL QHgL.jpg",
						"/t Philips LL QZn.jpg",
						"/t Philips LL QHgCdZn.jpg",
						"/t Philips Polarimeter.jpg"
					]
				},
				{
					subhead: "GEC 'Osira' 光谱系列",
					intros: [
						["Osram-GEC", "", "SL/D 1.3 Sodium Spectral Source", "1961"],
						["Osram-GEC", "", "ML/D 2.0 Mercury Spectral Source", "1964"],
						["Osram-GEC", "", "CL/D 2.0 Cadmium Spectral Source", "~1955"],
						["Osram-GEC", "", "CML/D 2.0 Cadmium & Mercury Spectral Source", "1962"]
					],
					pictures: ["/t GEC SLD1.jpg", "/t GEC MLD2.jpg", "/t Osram CLD2.jpg", "/t GEC CMLD2.jpg"]
				},
				{
					subhead: "GE美国 Lab-Arc 系列",
					intros: [
						["GE", "", "NA-1 Sodium Lab-Arc Spectral Source", "1960"],
						["GE", "85W", "H85A3/UV Lab-Arc Ultraviolet Source", "1952"]
					],
					pictures: ["/t GE NA1.jpg", "/t GE H85UV.jpg"]
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
