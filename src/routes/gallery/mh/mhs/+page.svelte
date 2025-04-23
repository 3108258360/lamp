<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Metal Halide - Special Application",
					description: [
						"Metal halide lamps have applications ranging far beyond the limits of general lighting, and over the past few decades this technology has been adapted into numerous other formats to suit the specific requirements of certain special niches.",
						"One of the principal fields to embrace this lamp technology is the film and studio business, where very large amounts of high colour temperature light are required. Traditionally that light was provided on film sets by the carbon arc lamp until the 1970s, when short arc metal halide lamps began to take over. They offer higher luminous efficacy, improved colour rendering and longer lifetime than the carbon arc lamp. In recent years the metal halide lamp has also been adapted to vehicle lighting, and a new family of ultra compact lamp has been developed to suit that requirement.",
						"New halide chemistries based on the rare earths were developed to mimic natural daylight as closely as possible, and arc tube developments were explored in both single and double ended designs. A number of lamps having integrated optical control have also been developed over the years, and also featured on this page are types having special arc tube chemistries, for instance to suit certain ultraviolet applications in the photoprinting and photopolymerisation businesses."
					]
				},
				{
					subhead: "Short Arc (Projection)",
					intros: [
						["Philips", "250W", "CSI Compact Source Iodine projection lamp", "~1970"],
						["GEC", "575W", "MEI Coolseal with sandblasted end seals", "1988"],
						["GEC", "2500W", "MEI Coolseal with Supercool style leads", "1988"],
						["Sylvania", "12000W", "BriteArc Double Ended High Power version", "2000"],
						["Thorn", "1000W", "CSI Compact Source Iodide", "1972"],
						["Thorn", "200W", "CID Compact Iodide Daylight (Hot Restrike)", "1988"],
						["Thorn", "2500W", "CID Compact Iodide Daylight", "1983"],
						["Philips", "220W", "SN 250 Tin Halide Molecular Discharge", "1989"],
						["Philips", "1200W", "MSR Medium Source Rare Earth", "1992"],
						["Osram", "200W", "HMI200W / SE Single Ended Compact", "1995"],
						["GE", "300W", "Gemini 300W for 16mm Movie Projectors", "~1980"],
						["GE", "350W", "MARC 350T / 16 for 16mm Movie Projectors", "~1980"],
						["Sylvania", "200W", "BriteBeam 200W/PAR36 for television filming", "1988"],
						["Osram", "400W", "HTI 400W for Stage / Studio Applications", "1993"],
						["Osram", "150W", "HQIR 150 / FO for Fibre Optic applications", "1997"]
					],
					pictures: [
						"/t Philips CSI250.jpg",
						"/t GEC MEI575.jpg",
						"/t GEC MEI2500 Supercool.jpg",
						"/t Sylvania BA12000.jpg",
						"/t Thorn CSI1000.jpg",
						"/t Thorn CID200.jpg",
						"/t Thorn CID2500.jpg",
						"/t Philips SN250.jpg",
						"/t Philips MSR1200HR.jpg",
						"/t Osram HMI200SE.jpg",
						"/t GE GEMINI300.jpg",
						"/t GE MARC350.jpg",
						"/t Sylvania BB200.jpg",
						"/t Osram HTI400.jpg",
						"/t Osram HQIR150.jpg"
					]
				},
				{
					subhead: "Short Arc (Miniature & Automotive)",
					intros: [
						["GE", "60W", "Light Engine LE60 Xenon Metal Halide", "1992"],
						["WelchAllyn", "3W", "Sõlarc Miniature 3 watt metal halide arc tube", "1990"],
						["WelchAllyn", "10W", "Sõlarc Miniature 10 watt metal halide reflector", "2002"],
						["Philips", "35W", "VeDiLiS Automotive Headlamp Prototype", "1987"],
						["Philips", "35W", "D2S Micro Power Xenon Light MPXL (automotive)", "1998"],
						["Philips", "35W", "D2S Ultinon 6000K Automotive Headlight", "2002"]
					],
					pictures: [
						"/t GE LE60.jpg",
						"/t Welch Allyn 3W.jpg",
						"/t WA MR11 10W.jpg",
						"/t Philips Vedilis H4.jpg",
						"/t Philips D2S.jpg",
						"/t Philips D2S Ultinon.jpg"
					]
				},
				{
					subhead: "Long Arc (Ultra-Violet)",
					intros: [
						["Philips", "400W", "HP/AB 400W Early design UV metal halide", "1980"],
						["Philips", "400W", "Cleo HPA400/S Mercury Sun tanning lamp", "2003"],
						["GE-Thorn", "1000W", "Graph-X Universal Sealed Beam", "1993"],
						["GE-Thorn", "2000W", "Graph-X Calmat SBL4 Sealed Beam Dichroic", "1998"]
					],
					pictures: [
						"/t Philips HP-AB 400.jpg",
						"/t Philips HPA400S.jpg",
						"/t Thorn GraphX.jpg",
						"/t D MHS Thorn Calmat SBL4.jpg"
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
					title: "特殊金卤灯",
					description: [
						"金属卤化物灯的应用范围远远超出了普通照明的范畴，在过去的几十年中，这种技术已经被改造成许多其他形式，以满足某些特殊领域的特定需求。",
						"采用这种灯技术的主要领域之一是电影和演播室行业，那里需要大量的高色温光线。传统上，这种光线是由碳弧灯在电影片场提供的，直到20世纪70年代，短弧金属卤化物灯开始逐渐取代它。与碳弧灯相比，短弧金属卤化物灯具有更高的发光效率、更好的显色性以及更长的使用寿命。近年来，金属卤化物灯还被应用于汽车照明领域，并且开发出了一系列超紧凑型灯具，以满足该领域的特殊需求。",
						"为了尽可能地模拟自然日光，人们开发出了基于稀土元素的新型卤化物化学配方，并且在单端和双端设计的弧光管方面也进行了探索。多年来，人们还开发出了许多带有集成光学控制的灯具，此外，本页面还介绍了一些具有特殊弧光管化学配方的灯型，例如，适用于光刻和光聚合行业的某些紫外线应用的灯型。"
					]
				},
				{
					subhead: "短弧(投影)",
					intros: [
						["Philips", "250W", "CSI Compact Source Iodine projection lamp", "~1970"],
						["GEC", "575W", "MEI Coolseal with sandblasted end seals", "1988"],
						["GEC", "2500W", "MEI Coolseal with Supercool style leads", "1988"],
						["Sylvania", "12000W", "BriteArc Double Ended High Power version", "2000"],
						["Thorn", "1000W", "CSI Compact Source Iodide", "1972"],
						["Thorn", "200W", "CID Compact Iodide Daylight (Hot Restrike)", "1988"],
						["Thorn", "2500W", "CID Compact Iodide Daylight", "1983"],
						["Philips", "220W", "SN 250 Tin Halide Molecular Discharge", "1989"],
						["Philips", "1200W", "MSR Medium Source Rare Earth", "1992"],
						["Osram", "200W", "HMI200W / SE Single Ended Compact", "1995"],
						["GE", "300W", "Gemini 300W for 16mm Movie Projectors", "~1980"],
						["GE", "350W", "MARC 350T / 16 for 16mm Movie Projectors", "~1980"],
						["Sylvania", "200W", "BriteBeam 200W/PAR36 for television filming", "1988"],
						["Osram", "400W", "HTI 400W for Stage / Studio Applications", "1993"],
						["Osram", "150W", "HQIR 150 / FO for Fibre Optic applications", "1997"]
					],
					pictures: [
						"/t Philips CSI250.jpg",
						"/t GEC MEI575.jpg",
						"/t GEC MEI2500 Supercool.jpg",
						"/t Sylvania BA12000.jpg",
						"/t Thorn CSI1000.jpg",
						"/t Thorn CID200.jpg",
						"/t Thorn CID2500.jpg",
						"/t Philips SN250.jpg",
						"/t Philips MSR1200HR.jpg",
						"/t Osram HMI200SE.jpg",
						"/t GE GEMINI300.jpg",
						"/t GE MARC350.jpg",
						"/t Sylvania BB200.jpg",
						"/t Osram HTI400.jpg",
						"/t Osram HQIR150.jpg"
					]
				},
				{
					subhead: "短弧(微型)",
					intros: [
						["GE", "60W", "Light Engine LE60 Xenon Metal Halide", "1992"],
						["WelchAllyn", "3W", "Sõlarc Miniature 3 watt metal halide arc tube", "1990"],
						["WelchAllyn", "10W", "Sõlarc Miniature 10 watt metal halide reflector", "2002"],
						["Philips", "35W", "VeDiLiS Automotive Headlamp Prototype", "1987"],
						["Philips", "35W", "D2S Micro Power Xenon Light MPXL (automotive)", "1998"],
						["Philips", "35W", "D2S Ultinon 6000K Automotive Headlight", "2002"]
					],
					pictures: [
						"/t GE LE60.jpg",
						"/t Welch Allyn 3W.jpg",
						"/t WA MR11 10W.jpg",
						"/t Philips Vedilis H4.jpg",
						"/t Philips D2S.jpg",
						"/t Philips D2S Ultinon.jpg"
					]
				},
				{
					subhead: "长弧(紫外线)",
					intros: [
						["Philips", "400W", "HP/AB 400W Early design UV metal halide", "1980"],
						["Philips", "400W", "Cleo HPA400/S Mercury Sun tanning lamp", "2003"],
						["GE-Thorn", "1000W", "Graph-X Universal Sealed Beam", "1993"],
						["GE-Thorn", "2000W", "Graph-X Calmat SBL4 Sealed Beam Dichroic", "1998"]
					],
					pictures: [
						"/t Philips HP-AB 400.jpg",
						"/t Philips HPA400S.jpg",
						"/t Thorn GraphX.jpg",
						"/t D MHS Thorn Calmat SBL4.jpg"
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
