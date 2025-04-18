<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent - Tungsten Filament lamp",
					description: [
						"Although the tungsten filament lamp offered a higher efficacy than its tantalum predecessor from the outset, it was not able to immediately replace the former filament material. This was owing to the very brittle nature of the original tungsten filaments - which were made from powdered tungsten particles sintered together to produce a fine wire. The difficult manufacturing process led to high costs and filament breakages in service were commonplace.",
						"The problem was not overcome until the 1910 development of drawn-tungsten wire, this ductile material being much more robust and eminently more suitable for lampmaking. From this point onwards, practically all of the former filament materials were abandoned.",
						"A third development in tungsten lamps was the important change from vacuum to gas-filled designs, and the parallel change from straight wire to coiled filaments. This gave a further significant boost in lamp efficacy combined with a reduction in costs. Lamps of all three tungsten technologies are featured on this page."
					]
				},
				{
					subhead: "Squirted & Sintered Tungsten Filament",
					intros: [
						["Auer", "50CP", "'Osram' lamp with sintered metal filament", "~1908-10"],
						["Pintsch", "25CP", "'Sirius' lamp with colloidal filament", "~1908-09"],
						["Graetzin", "16CP", "Sintered Tungsten with pasted filaments", "~1908-10"],
						["Henrion", "16CP", "'Osmine' French Sintered Metal Filament", "~1909-10"],
						["Osram", "25B", "French Osram sintered tungsten lamp", "~1909-12"],
						["Osram-GEC", "17W", "GEC British Sintered tungsten filament", "1908"],
						["Osram-GEC", "17W", "German Auer lamp made for British GEC", "1910"],
						["Ediswan", "17W", "Royal Ediswan Tubular Sintered Tungsten", "1908"],
						["GE", "40W", "GE American Sintered Tungsten Filament", "1909"],
						["Sunbeam", "100W", "National Mazda Sintered Tungsten Filament", "1909"],
						["Pope", "8 CP", "Miniature low voltage sintered tungsten", "~1908-12"]
					],
					pictures: [
						"/t IN WS Osram 225-50G90CL-E27.jpg",
						"/t IN WS Pintsch 125-25S55CL-E27.jpg",
						"/t IN WS Graetzin 25-18SA55CL-B22d.jpg",
						"/t IN WS Osmine 110-16SA55CL-B22.jpg",
						"/t IN WS Osram 125-25S60CL-B22d.jpg",
						"/t IN WS GEC 50-17G75CL-B22d.jpg",
						"/t IN WS GEC 100-17SA55CL-B22d.jpg",
						"/t IN WS Ediswan 105-17T25CL-B15d.jpg",
						"/t IN WS GE 117-40SA19FC-E26.jpg",
						"/t IN WS National-Sunbeam 110-100S30CL-E26.jpg",
						"/t IN WS Pope 4-8G35CL-B15d.jpg"
					]
				},
				{
					subhead: "Drawn Tungsten Filament",
					intros: [
						["GE-National", "40W", "Crinkled Filament and Eldred Glass-Metal Seals", "1912"],
						["GE-Edison", "40W", "Pasted Filament Clamps & Dumet Seals", "c.1915"],
						["GEC", "40W", 'Osram Drawn Tungsten "Angle" Type', "1911"],
						["S.F. Auer", "30CP", "O.R. Omnidirectional Radiation Spiral Filament", "~1910-15"]
					],
					pictures: [
						"/t IN WD National-Columbia 108-40S67CL-E27 Crinkled.jpg",
						"/t IN WD GE 110-40S18-E26 Pasted Clamps.jpg",
						"/t IN W GEC 240-40SA62CL-BC-S1.jpg",
						"/t IN WD Auer OR 30K 115V.jpg"
					]
				},
				{
					subhead: "Coiled Tungsten Filament",
					intros: [
						["GE-Edison", "500W", "Mazda 'C' Early Style 500W Gasfilled", "1915"],
						["Philips", "100W", "Tungsten Gasfilled HalfWatt", "1919"],
						["GEC", "60W", "First Coiled-Coil Tungsten Filament GLS", "1934"],
						["GEC", "100W", "Swan Centenary GLS with Single Support Wire", "1979"],
						["GEC", "100W", "Experimental GLS with Plastic Cap", "c.1980"],
						["GE", "150W", "Rough Service with Tuff-Skin coating", "1979"]
					],
					pictures: [
						"/t IN WC GE 112-500SA40CL-E39.jpg",
						"/t IN WC Philips Halfwatt 100W.jpg",
						"/t IN WC GEC 240-60PS65CL-B22d CC.jpg",
						"/t IN WC GEC 240-100PS60CL-BC Single Support.jpg",
						"/t IN WC GEC 240-100PS60FR-BC Plastic.jpg",
						"/t IN WC GE 120-150A25TS-E26.jpg"
					]
				},
				{
					subhead: "Infrared Recylcing Coating",
					intros: [["Duro-Test", "65W", "Tungsten Gasfilled with IRC Coating", "c. 1980"]],
					pictures: ["/t IN WC DuroTest 120-65G30IRC-E26.jpg"]
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
					title: "钨丝白炽灯",
					description: [
						"虽然钨丝灯从一开始效率就比其钽丝前身高，但未能立即取代前者。这是由于最初的钨丝非常脆——它们是由粉末状钨颗粒烧结在一起制成的细丝。复杂的制造工艺导致成本高昂，而且在使用过程中灯丝断裂的情况很常见。",
						"直到1910年拉制钨丝的发明，这一问题才得以解决。这种韧性材料更加坚固，更适合用于灯泡制造。从那时起，几乎所有以前的灯丝材料都被放弃了。",
						"钨灯的第三个发展是从真空设计改为充气设计，以及从直丝改为螺旋灯丝的并行变化。这进一步显著提高了灯泡的效率，并降低了成本。本页面展示了所有三种钨灯技术的灯泡。"
					]
				},
				{
					subhead: "喷射与烧结钨丝",
					intros: [
						["Auer", "50CP", "'Osram' lamp with sintered metal filament", "~1908-10"],
						["Pintsch", "25CP", "'Sirius' lamp with colloidal filament", "~1908-09"],
						["Graetzin", "16CP", "Sintered Tungsten with pasted filaments", "~1908-10"],
						["Henrion", "16CP", "'Osmine' French Sintered Metal Filament", "~1909-10"],
						["Osram", "25B", "French Osram sintered tungsten lamp", "~1909-12"],
						["Osram-GEC", "17W", "GEC British Sintered tungsten filament", "1908"],
						["Osram-GEC", "17W", "German Auer lamp made for British GEC", "1910"],
						["Ediswan", "17W", "Royal Ediswan Tubular Sintered Tungsten", "1908"],
						["GE", "40W", "GE American Sintered Tungsten Filament", "1909"],
						["Sunbeam", "100W", "National Mazda Sintered Tungsten Filament", "1909"],
						["Pope", "8 CP", "Miniature low voltage sintered tungsten", "~1908-12"]
					],
					pictures: [
						"/t IN WS Osram 225-50G90CL-E27.jpg",
						"/t IN WS Pintsch 125-25S55CL-E27.jpg",
						"/t IN WS Graetzin 25-18SA55CL-B22d.jpg",
						"/t IN WS Osmine 110-16SA55CL-B22.jpg",
						"/t IN WS Osram 125-25S60CL-B22d.jpg",
						"/t IN WS GEC 50-17G75CL-B22d.jpg",
						"/t IN WS GEC 100-17SA55CL-B22d.jpg",
						"/t IN WS Ediswan 105-17T25CL-B15d.jpg",
						"/t IN WS GE 117-40SA19FC-E26.jpg",
						"/t IN WS National-Sunbeam 110-100S30CL-E26.jpg",
						"/t IN WS Pope 4-8G35CL-B15d.jpg"
					]
				},
				{
					subhead: "拉制钨丝",
					intros: [
						["GE-National", "40W", "Crinkled Filament and Eldred Glass-Metal Seals", "1912"],
						["GE-Edison", "40W", "Pasted Filament Clamps & Dumet Seals", "c.1915"],
						["GEC", "40W", 'Osram Drawn Tungsten "Angle" Type', "1911"],
						["S.F. Auer", "30CP", "O.R. Omnidirectional Radiation Spiral Filament", "~1910-15"]
					],
					pictures: [
						"/t IN WD National-Columbia 108-40S67CL-E27 Crinkled.jpg",
						"/t IN WD GE 110-40S18-E26 Pasted Clamps.jpg",
						"/t IN W GEC 240-40SA62CL-BC-S1.jpg",
						"/t IN WD Auer OR 30K 115V.jpg"
					]
				},
				{
					subhead: "螺旋钨丝",
					intros: [
						["GE-Edison", "500W", "Mazda 'C' Early Style 500W Gasfilled", "1915"],
						["Philips", "100W", "Tungsten Gasfilled HalfWatt", "1919"],
						["GEC", "60W", "First Coiled-Coil Tungsten Filament GLS", "1934"],
						["GEC", "100W", "Swan Centenary GLS with Single Support Wire", "1979"],
						["GEC", "100W", "Experimental GLS with Plastic Cap", "c.1980"],
						["GE", "150W", "Rough Service with Tuff-Skin coating", "1979"]
					],
					pictures: [
						"/t IN WC GE 112-500SA40CL-E39.jpg",
						"/t IN WC Philips Halfwatt 100W.jpg",
						"/t IN WC GEC 240-60PS65CL-B22d CC.jpg",
						"/t IN WC GEC 240-100PS60CL-BC Single Support.jpg",
						"/t IN WC GEC 240-100PS60FR-BC Plastic.jpg",
						"/t IN WC GE 120-150A25TS-E26.jpg"
					]
				},
				{
					subhead: "红外反射涂层",
					intros: [["Duro-Test", "65W", "Tungsten Gasfilled with IRC Coating", "c. 1980"]],
					pictures: ["/t IN WC DuroTest 120-65G30IRC-E26.jpg"]
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
