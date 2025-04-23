<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Metal Halide - Quartz",
					description: [
						"Although the origins of the metal halide lamp can be traced back to a 1912 patent taken out by GE's Charles Steinmetz, the practical lamps based on current technologies first appeared in the labs of many of the world's leading lamp companies in the late 1950s. It was not until the mid 1960s that commercial products appeared, the first being commercialised by GE of America.",
						"The technology is a development of the high pressure mercury lamp, to which trace additions of various other metals are added in the form of their halide compounds. These are vaporised into the discharge and contribute their spectral output, and materials are selected which fill in the gaps in the mercury spectrum to deliver a light source having considerably improved colour properties. The luminous efficacy of the lamps is also increased owing to a reduction in the generation of invisible ultraviolet radiation.",
						"It is necessary to add the metals in the form of halides because the metals themselves usually have too low a vapour pressure to participate in the discharge, but the halides are vaporised very much more readily. In addition the additive metals are rather corrosive towards the quartz discharge tube wall, but when halides are employed, they generally exist in compound form on the quartz surface, in which state they are very much less reactive, thus minimising corrosion problems."
					]
				},
				{
					subhead: "Multi-Band Halides",
					intros: [
						["Philips", "2000W", "HPI/T 1st Generation shrink-sealed arc tube", "1968"],
						["Philips", "375W", "HPI/T 2nd Generation pinch-sealed arc tube", "1974"],
						["Philips", "400W", "HPI/T 3rd Generation with hydrogen getter", "1981"],
						["Philips", "400W", "HPI/T 4th Generation with improved arc tube", "1986"],
						["Philips", "400W", "HPI-T 5th Generation with blown arc tube", "1996"],
						["Philips", "400W", "HPI-T 7th Generation with small arc tube", "2012"],
						["Philips", "400W", "HPI-T Plus for Vertical operation", "2008"],
						["Philips", "400W", "HPI-BUS Self-Starting Mercury Lamp Retrofit", "1987"],
						["Philips", "250W", "HPI Plus with Daylight colour phosphor", "2012"],
						["Philips", "10,000W", "HPI/TD Double Ended Stadium Floodlight", "1971"],
						["Mazda", "2000W", "MAIH 2000 B 380V of French design", "1978"],
						["Mazda", "1000W", "MAIH 1000 TP 220V of unusual French design", "1979"],
						["Claude", "1000W", "MI 1000W-380V of unusual French design", "~1985"],
						["GEC", "2000W", "MBI/H 2000W Stadium Floodlight", "1984"],
						["Narva", "400W", "Nachroma NC400-00 with Na-In-Tl chemistry", "1984"],
						["Thorn", "250W", "Kolorarc MBI-T 250W tri-band high output", "1991"],
						["Iwasaki", "400W", "Mutli-Super Ace 5-band Mercury Lamp Retrofit", "2002"]
					],
					pictures: [
						"/t HID MHQ Philips HPIT 2000HV.jpg",
						"/t D MHQ Philips HPIT375.jpg",
						"/t D MHQ Philips HPIT400 Mk3.jpg",
						"/t D MHQ Philips HPIT400 Mk4.jpg",
						"/t D MHQ Philips HPIT400 Mk5.jpg",
						"/t D MHQ Philips HPIT+400 Mk7.jpg",
						"/t D MHQ Philips HPIT400BU.jpg",
						"/t D MHQ Philips HPI400BUS.jpg",
						"/t D MHQ Philips HPI+250BUD.jpg",
						"/t D MHQ Philips HPITD10000.jpg",
						"/t D MHQ CdL MAIH2000B.jpg",
						"/t D MHQ CdL MAIH1000TP.jpg",
						"/t D MHQ Claude MI1000-380V.jpg",
						"/t D MHQ GEC MBI2000.jpg",
						"/t Narva NC400-00.jpg",
						"/t Thorn MBIT250.jpg",
						"/t Iwasaki MF400LSH.jpg"
					]
				},
				{
					subhead: "Sodium-Scandium Halides",
					intros: [
						["Sylvania", "400W", "Metalarc Thorium-Scandium prototype", "1965"],
						["Sylvania", "400W", "MetalArc Coated with Barium Peroxide Getter", "1979"],
						["Sylvania", "400W", "Super MetalArc Horiz. with curved arc tube", "1986"],
						["Sylvania", "1000W", "Super MetalArc Vertical with fattened arc tube", "1984"],
						["GE", "400W", "Multi-Vapor MV-400/BD with Na-Sc chemistry", "1973"],
						["Westinghouse", "400W", "MH400/BU/4 with glass-sleeved frame", "1980"],
						["Thorn", "375W", "KolorArc MBI/BD 400W with etched arc tube", "1979"],
						["Thorn", "250W", "MBIF/H/S Lithium for Marks & Spencer", "1982"],
						["Saransk", "175W", "DRI 175W warm white of Russian design", "1987"],
						["GE", "175W", "Multi-Vapor II (Halarc) high-lumen electronic", "1989"],
						["Philips", "1500W", "Z-Lamp with offset arc tube for sports lighting", "2003"],
						["Venture", "400W", "Glare-Guard with crown silvered outer bulb", "1992"],
						["Thorn", "1500W", "MBIL/H High Wattage Double Ended Linear", "1988"],
						["Sylvania", "100W", "MetalArc Protected for open fixtures", "1986"],
						["GE", "32W", "Halarc MXR low wattage for open fixtures", "1990"],
						["GE", "350W", "PulseArc for use with electronic starters", "2000"],
						["GE", "55W", "Halarc Electronic'First Light' Clear", "1980-81"],
						["GE", "55W", "Halarc ElectronicMiser Maxi-Light", "1981-83"]
					],
					pictures: [
						"/t D MHQ Sylvania M400.jpg",
						"/t D MHQ Sylvania M400C-BUH.jpg",
						"/t D MHQ Sylvania MS400HOR.jpg",
						"/t Sylvania MS1000V.jpg",
						"/t HID MHQ GE MV400-BD.jpg",
						"/t D MHQ Westinghouse MH400-BU-4.jpg",
						"/t D MHQ Thorn MBI400BD.jpg",
						"/t Thorn MBIFHS250.jpg",
						"/t D MHQ Svetotekhnika DRI175.jpg",
						"/t GE Halarc175.jpg",
						"/t Musco MH1500Z.jpg",
						"/t Venture Glareguard.jpg",
						"/t Thorn MBIL1500.jpg",
						"/t Sylvania Metalarc100.jpg",
						"/t GE Halarc32.jpg",
						"/t D MHQ GE MVR350-VBU-PA.jpg",
						"/t D MHQ GE Halarc Electronic Clear.jpg",
						"/t D MHQ GE Halarc Electronic.jpg"
					]
				},
				{
					subhead: "Rare Earth Halides",
					intros: [
						["Osram", "350W", "HQIL 400W Rare Earth with Fluorescent bulb", "1968"],
						["Osram", "360W", "HQI-T 400W-71 Rare Earth of 2nd Generation", "1973"],
						["Osram", "360W", "HQI-T 400W/DH Rare Earth of 3rd Generation", "1982"],
						["Wotan", "360W", "HQI-T 400W/DV Rare Earth of 4th Generation", "1988"],
						["Osram", "400W", "HQI-T 400W/D Rare Earth of 5th Generation", "1991"],
						["Osram", "400W", "HQI-BT 400W/D Rare Earth of 6th Generation", "2001"],
						["Wotan", "250W", "Powerstar HQI-R with integral reflector", "1987"],
						["Tungsram", "360W", "HgMIF 400/DH Rare Earth Horizontal", "1992"],
						["Polam", "360W", "LRJD Dysprosium-Thallium Indium lamp", "1997"],
						["Osram", "150W", "HQI-TS 150W/NDL Double Ended Compact", "1989"],
						["Philips", "75W", 'MHN "Thulium Lamp" High-CRI Prototype', "1985"],
						["Philips", "70W", "MHN-T Open Fixture Single Ended", "1996"],
						["Philips", "35W", "MHN-TC Experimental Single Ended Compact", "1993"],
						["Iwasaki", "150W", "ColorArc 3500K with exceptionally high Ra 96", "1988"],
						["Iwasaki", "70W", "ColorArc 6500K PAR36 High-CRI Metal Halide", "1999"],
						["Sylvania", "35W", "BriteSpot ES50 Compact Metal Halide Reflector", "2003"]
					],
					pictures: [
						"/t D MHQ Osram HQIL400.jpg",
						"/t D MHQ Osram HQIT400-71.jpg",
						"/t D MHQ Osram HQIT400DH.jpg",
						"/t Wotan HQIT400DV.jpg",
						"/t D MHQ Osram HQIT400D.jpg",
						"/t Osram HQI-BT400.jpg",
						"/t Wotan HQIR250.jpg",
						"/t Tungsram HgMIF400.jpg",
						"/t D MHQ Polam-COBR LRJD400.jpg",
						"/t Osram HQITS150.jpg",
						"/t Philips MHN70.jpg",
						"/t Philips MHNT70.jpg",
						"/t Philips MHNTC35.jpg",
						"/t Iwasaki MT150SDW.jpg",
						"/t Iwasaki M70P36.jpg",
						"/t Sylvania BriteSpot ES50.jpg"
					]
				},
				{
					subhead: "Molecular Halides",
					intros: [
						["Thorn", "200W", "Arcstream MBI-T Single Ended Prototype", "1985"],
						["Osram", "70W", "HQI-T 70W/WDL Single Ended Compact", "1987"]
					],
					pictures: ["/t Thorn Arcstream 200.jpg", "/t Osram HQIT70.jpg"]
				},
				{
					subhead: "Coloured Halides",
					intros: [
						["Tesla", "400W", "RVIZ Thallium Iodide Green colour lamp", "1975"],
						["GEC", "400W", "MBI/U Indium Iodide Blue colour lamp", "1986"],
						["YaMing", "250W", "JLC250 Sodium-Lithium-Indium Red colour lamp", "2004"],
						["Narva", "400W", "NC400-04 Bilirubinaemia Gallium-Indium lamp", "1981"]
					],
					pictures: [
						"/t Tesla RVIZ400.jpg",
						"/t GEC MBI400 Blue.jpg",
						"/t YaMing JLC250R.jpg",
						"/t Narva NC400-04.jpg"
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
					title: "金属卤化物 - 石英",
					description: [
						"尽管金属卤化物灯的起源可以追溯到1912年通用电气公司查尔斯·斯坦梅茨申请的专利，但基于当前技术的实用灯具直到20世纪50年代末才出现在世界上许多领先灯具公司的实验室中。直到20世纪60年代中期，商业产品才出现，第一个由美国通用电气公司商业化。",
						"这种技术是高压汞灯的发展，通过添加各种其他金属的微量卤化物化合物来实现。这些化合物被蒸发到放电中，并贡献了它们的光谱输出，选择的材料填补了汞光谱中的空白，从而提供了一个具有显著改善的色彩特性的光源。由于减少了不可见紫外线辐射的产生，灯的发光效率也得到了提高。",
						"有必要以卤化物的形式添加金属，因为金属本身的蒸汽压通常过低，无法参与放电，但卤化物则更容易被蒸发。此外，添加的金属对石英放电管壁具有相当的腐蚀性，但当使用卤化物时，它们通常以化合物形式存在于石英表面，在这种状态下，它们的反应性要小得多，从而最大限度地减少了腐蚀问题。"
					]
				},
				{
					subhead: "多波段卤化物",
					intros: [
						["Philips", "2000W", "HPI/T 1st Generation shrink-sealed arc tube", "1968"],
						["Philips", "375W", "HPI/T 2nd Generation pinch-sealed arc tube", "1974"],
						["Philips", "400W", "HPI/T 3rd Generation with hydrogen getter", "1981"],
						["Philips", "400W", "HPI/T 4th Generation with improved arc tube", "1986"],
						["Philips", "400W", "HPI-T 5th Generation with blown arc tube", "1996"],
						["Philips", "400W", "HPI-T 7th Generation with small arc tube", "2012"],
						["Philips", "400W", "HPI-T Plus for Vertical operation", "2008"],
						["Philips", "400W", "HPI-BUS Self-Starting Mercury Lamp Retrofit", "1987"],
						["Philips", "250W", "HPI Plus with Daylight colour phosphor", "2012"],
						["Philips", "10,000W", "HPI/TD Double Ended Stadium Floodlight", "1971"],
						["Mazda", "2000W", "MAIH 2000 B 380V of French design", "1978"],
						["Mazda", "1000W", "MAIH 1000 TP 220V of unusual French design", "1979"],
						["Claude", "1000W", "MI 1000W-380V of unusual French design", "~1985"],
						["GEC", "2000W", "MBI/H 2000W Stadium Floodlight", "1984"],
						["Narva", "400W", "Nachroma NC400-00 with Na-In-Tl chemistry", "1984"],
						["Thorn", "250W", "Kolorarc MBI-T 250W tri-band high output", "1991"],
						["Iwasaki", "400W", "Mutli-Super Ace 5-band Mercury Lamp Retrofit", "2002"]
					],
					pictures: [
						"/t HID MHQ Philips HPIT 2000HV.jpg",
						"/t D MHQ Philips HPIT375.jpg",
						"/t D MHQ Philips HPIT400 Mk3.jpg",
						"/t D MHQ Philips HPIT400 Mk4.jpg",
						"/t D MHQ Philips HPIT400 Mk5.jpg",
						"/t D MHQ Philips HPIT+400 Mk7.jpg",
						"/t D MHQ Philips HPIT400BU.jpg",
						"/t D MHQ Philips HPI400BUS.jpg",
						"/t D MHQ Philips HPI+250BUD.jpg",
						"/t D MHQ Philips HPITD10000.jpg",
						"/t D MHQ CdL MAIH2000B.jpg",
						"/t D MHQ CdL MAIH1000TP.jpg",
						"/t D MHQ Claude MI1000-380V.jpg",
						"/t D MHQ GEC MBI2000.jpg",
						"/t Narva NC400-00.jpg",
						"/t Thorn MBIT250.jpg",
						"/t Iwasaki MF400LSH.jpg"
					]
				},
				{
					subhead: "钠钪卤化物",
					intros: [
						["Sylvania", "400W", "Metalarc Thorium-Scandium prototype", "1965"],
						["Sylvania", "400W", "MetalArc Coated with Barium Peroxide Getter", "1979"],
						["Sylvania", "400W", "Super MetalArc Horiz. with curved arc tube", "1986"],
						["Sylvania", "1000W", "Super MetalArc Vertical with fattened arc tube", "1984"],
						["GE", "400W", "Multi-Vapor MV-400/BD with Na-Sc chemistry", "1973"],
						["Westinghouse", "400W", "MH400/BU/4 with glass-sleeved frame", "1980"],
						["Thorn", "375W", "KolorArc MBI/BD 400W with etched arc tube", "1979"],
						["Thorn", "250W", "MBIF/H/S Lithium for Marks & Spencer", "1982"],
						["Saransk", "175W", "DRI 175W warm white of Russian design", "1987"],
						["GE", "175W", "Multi-Vapor II (Halarc) high-lumen electronic", "1989"],
						["Philips", "1500W", "Z-Lamp with offset arc tube for sports lighting", "2003"],
						["Venture", "400W", "Glare-Guard with crown silvered outer bulb", "1992"],
						["Thorn", "1500W", "MBIL/H High Wattage Double Ended Linear", "1988"],
						["Sylvania", "100W", "MetalArc Protected for open fixtures", "1986"],
						["GE", "32W", "Halarc MXR low wattage for open fixtures", "1990"],
						["GE", "350W", "PulseArc for use with electronic starters", "2000"],
						["GE", "55W", "Halarc Electronic'First Light' Clear", "1980-81"],
						["GE", "55W", "Halarc ElectronicMiser Maxi-Light", "1981-83"]
					],
					pictures: [
						"/t D MHQ Sylvania M400.jpg",
						"/t D MHQ Sylvania M400C-BUH.jpg",
						"/t D MHQ Sylvania MS400HOR.jpg",
						"/t Sylvania MS1000V.jpg",
						"/t HID MHQ GE MV400-BD.jpg",
						"/t D MHQ Westinghouse MH400-BU-4.jpg",
						"/t D MHQ Thorn MBI400BD.jpg",
						"/t Thorn MBIFHS250.jpg",
						"/t D MHQ Svetotekhnika DRI175.jpg",
						"/t GE Halarc175.jpg",
						"/t Musco MH1500Z.jpg",
						"/t Venture Glareguard.jpg",
						"/t Thorn MBIL1500.jpg",
						"/t Sylvania Metalarc100.jpg",
						"/t GE Halarc32.jpg",
						"/t D MHQ GE MVR350-VBU-PA.jpg",
						"/t D MHQ GE Halarc Electronic Clear.jpg",
						"/t D MHQ GE Halarc Electronic.jpg"
					]
				},
				{
					subhead: "稀土卤化物",
					intros: [
						["Osram", "350W", "HQIL 400W Rare Earth with Fluorescent bulb", "1968"],
						["Osram", "360W", "HQI-T 400W-71 Rare Earth of 2nd Generation", "1973"],
						["Osram", "360W", "HQI-T 400W/DH Rare Earth of 3rd Generation", "1982"],
						["Wotan", "360W", "HQI-T 400W/DV Rare Earth of 4th Generation", "1988"],
						["Osram", "400W", "HQI-T 400W/D Rare Earth of 5th Generation", "1991"],
						["Osram", "400W", "HQI-BT 400W/D Rare Earth of 6th Generation", "2001"],
						["Wotan", "250W", "Powerstar HQI-R with integral reflector", "1987"],
						["Tungsram", "360W", "HgMIF 400/DH Rare Earth Horizontal", "1992"],
						["Polam", "360W", "LRJD Dysprosium-Thallium Indium lamp", "1997"],
						["Osram", "150W", "HQI-TS 150W/NDL Double Ended Compact", "1989"],
						["Philips", "75W", 'MHN "Thulium Lamp" High-CRI Prototype', "1985"],
						["Philips", "70W", "MHN-T Open Fixture Single Ended", "1996"],
						["Philips", "35W", "MHN-TC Experimental Single Ended Compact", "1993"],
						["Iwasaki", "150W", "ColorArc 3500K with exceptionally high Ra 96", "1988"],
						["Iwasaki", "70W", "ColorArc 6500K PAR36 High-CRI Metal Halide", "1999"],
						["Sylvania", "35W", "BriteSpot ES50 Compact Metal Halide Reflector", "2003"]
					],
					pictures: [
						"/t D MHQ Osram HQIL400.jpg",
						"/t D MHQ Osram HQIT400-71.jpg",
						"/t D MHQ Osram HQIT400DH.jpg",
						"/t Wotan HQIT400DV.jpg",
						"/t D MHQ Osram HQIT400D.jpg",
						"/t Osram HQI-BT400.jpg",
						"/t Wotan HQIR250.jpg",
						"/t Tungsram HgMIF400.jpg",
						"/t D MHQ Polam-COBR LRJD400.jpg",
						"/t Osram HQITS150.jpg",
						"/t Philips MHN70.jpg",
						"/t Philips MHNT70.jpg",
						"/t Philips MHNTC35.jpg",
						"/t Iwasaki MT150SDW.jpg",
						"/t Iwasaki M70P36.jpg",
						"/t Sylvania BriteSpot ES50.jpg"
					]
				},
				{
					subhead: "分子卤化物",
					intros: [
						["Thorn", "200W", "Arcstream MBI-T Single Ended Prototype", "1985"],
						["Osram", "70W", "HQI-T 70W/WDL Single Ended Compact", "1987"]
					],
					pictures: ["/t Thorn Arcstream 200.jpg", "/t Osram HQIT70.jpg"]
				},
				{
					subhead: "彩色卤化物",
					intros: [
						["Tesla", "400W", "RVIZ Thallium Iodide Green colour lamp", "1975"],
						["GEC", "400W", "MBI/U Indium Iodide Blue colour lamp", "1986"],
						["YaMing", "250W", "JLC250 Sodium-Lithium-Indium Red colour lamp", "2004"],
						["Narva", "400W", "NC400-04 Bilirubinaemia Gallium-Indium lamp", "1981"]
					],
					pictures: [
						"/t Tesla RVIZ400.jpg",
						"/t GEC MBI400 Blue.jpg",
						"/t YaMing JLC250R.jpg",
						"/t Narva NC400-04.jpg"
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
