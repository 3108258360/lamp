<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Non-Linear Fluorescent",
					description: [
						"While the long, slender proportions of the original Linear Fluorescent lamps makes them ideal for many applications, it can be a hindrance in others. A decade after the commercialisation of fluorescent technology and the refinement of the basic range, efforts were diverted into reducing the size of the light source. At first this was achieved by folding the standard tubes into various planar geometries - such as the circular, U-tube and W-shaped patterns featured on this page. Later still, improvements in phosphor technology permitted a considerable reduction in the diameter of the discharge tube, and that spurred the development of the third category of this lamp technology - the Compact Fluorescent lamps."
					]
				},
				{
					subhead: "O-Shape",
					intros: [
						["GE", "40W", "FC16T10CW T10 with Rapid Start cathodes", "1956"],
						["Philips", "40W", "TL-EM T9 with stripe for Tungsten Ballast", "1956"],
						["Sylvania", "32W", "FC12T10WW T10 with Rapid Start cathodes", "1970"],
						["Toshiba", "30W", "FCL30ELC-28PDLN with Side Reflector", "2015"],
						["National", "40W", "FHD40EL Twin-Tube Circline", "2012"],
						["Philips", "32W", "Coloured Circline Lamp, TLE 32W Yellow", "c. 1960"],
						["Philips", "32W", "Coloured Circline Lamp, TLE 32W Pink", "c. 1960"]
					],
					pictures: [
						"/t D FLO GE FC16T10CW.jpg",
						"/t D FLO Philips TLEM40-32.jpg",
						"/t D FLO Sylvania FC12T10WW.jpg",
						"/t D FLO Toshiba FCL30ELC-28PDLN.jpg",
						"/t D FLO National FHD40EL.jpg",
						"/t D FLO Philips TLE32 Yellow lit.jpg",
						"/t D FLO Philips TLE32 Pink lit.jpg"
					]
				},
				{
					subhead: "U-Shape",
					intros: [
						["Osram", "16W", "HNW72 T8 U-Shape fluorescent", "1950"],
						["Osram", "65W", "L65W-25U T12 U-Shape fluorescent", "1965"],
						["Philips", "20W", "TL-U T12 U-shape fluorescent", "1971"],
						["Thorn", "40W", "T8 U-shape fluorescent for metric ceilings", "1981"],
						["Sylvania", "34W", "FB34/941/6/SS/ECO USA energy-saving lamp", "2012"]
					],
					pictures: [
						"/t D FLU Osram HNW72-16.jpg",
						"/t D FLU Osram L65W-25U.jpg",
						"/t D FLU Philips TLU20-33.jpg",
						"/t D FLU Thorn F40UT8-535.jpg",
						"/t D FLU Sylvania FB34-941-6-SS-ECO.jpg"
					]
				},
				{
					subhead: "W-Shape",
					intros: [
						["Philips", "25W", "TL-W T8¼ W-shaped fluorescent", "1967"],
						["GE", "50/80W", "Panel 'F' Square moulded fluorescent", "1965"]
					],
					pictures: ["/t D FLW Philips TLW25-32.jpg", "/t D FLW GE FP12S-DX front.jpg"]
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
					title: "非线性荧光灯",
					description: [
						"虽然最初线性荧光灯的长而细的形状使其适用于许多应用，但在其他一些情况下可能会成为阻碍。在荧光技术商业化和基本系列完善后的十年里，人们开始努力缩小光源的尺寸。最初，这是通过将标准灯管折叠成各种平面几何形状来实现的，例如本页面上展示的圆形、U形管和W形图案。后来，随着荧光粉技术的进步，灯管直径得以大幅缩小，这也推动了这种灯具技术的第三个类别——紧凑型荧光灯的开发。"
					]
				},
				{
					subhead: "O形",
					intros: [
						["GE", "40W", "FC16T10CW T10 with Rapid Start cathodes", "1956"],
						["Philips", "40W", "TL-EM T9 with stripe for Tungsten Ballast", "1956"],
						["Sylvania", "32W", "FC12T10WW T10 with Rapid Start cathodes", "1970"],
						["Toshiba", "30W", "FCL30ELC-28PDLN with Side Reflector", "2015"],
						["National", "40W", "FHD40EL Twin-Tube Circline", "2012"],
						["Philips", "32W", "Coloured Circline Lamp, TLE 32W Yellow", "c. 1960"],
						["Philips", "32W", "Coloured Circline Lamp, TLE 32W Pink", "c. 1960"]
					],
					pictures: [
						"/t D FLO GE FC16T10CW.jpg",
						"/t D FLO Philips TLEM40-32.jpg",
						"/t D FLO Sylvania FC12T10WW.jpg",
						"/t D FLO Toshiba FCL30ELC-28PDLN.jpg",
						"/t D FLO National FHD40EL.jpg",
						"/t D FLO Philips TLE32 Yellow lit.jpg",
						"/t D FLO Philips TLE32 Pink lit.jpg"
					]
				},
				{
					subhead: "U形",
					intros: [
						["Osram", "16W", "HNW72 T8 U-Shape fluorescent", "1950"],
						["Osram", "65W", "L65W-25U T12 U-Shape fluorescent", "1965"],
						["Philips", "20W", "TL-U T12 U-shape fluorescent", "1971"],
						["Thorn", "40W", "T8 U-shape fluorescent for metric ceilings", "1981"],
						["Sylvania", "34W", "FB34/941/6/SS/ECO USA energy-saving lamp", "2012"]
					],
					pictures: [
						"/t D FLU Osram HNW72-16.jpg",
						"/t D FLU Osram L65W-25U.jpg",
						"/t D FLU Philips TLU20-33.jpg",
						"/t D FLU Thorn F40UT8-535.jpg",
						"/t D FLU Sylvania FB34-941-6-SS-ECO.jpg"
					]
				},
				{
					subhead: "W形",
					intros: [
						["Philips", "25W", "TL-W T8¼ W-shaped fluorescent", "1967"],
						["GE", "50/80W", "Panel 'F' Square moulded fluorescent", "1965"]
					],
					pictures: ["/t D FLW Philips TLW25-32.jpg", "/t D FLW GE FP12S-DX front.jpg"]
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
