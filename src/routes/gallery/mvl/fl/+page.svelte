<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Mercury Fluorescent",
					description: [
						"High pressure mercury lamps are rich in blue, green and yellow wavelengths but almost entirely devoid of red radiation, which produces a cool white light colour having very poor colour rendering properties. One of the most succesful mechanisms to counter this was by the application of fluorescent phosphors to the outer bulb, in an attempt to convert some of the ultraviolet radiation from the discharge into more useful red wavelengths.",
						"The first successful lamp was achieved by Osram-GEC of England in 1937, with the application of a copper-activated zinc cadmium sulphide phosphor. Subsequent decades saw the development of dozens of different phosphors, each offering progressive improvements in terms of lowering the colour temperature of the light, improving colour rendering, and where possible also improving the luminous efficacy of mercury fluorescent lamps. Several of the principle developments are illustrated below, grouped according to the type of phosphor chemistry or the intended application."
					]
				},
				{
					subhead: "Sulphide Phosphors",
					intros: [
						["GEC", "400W", "MAF/V Mercury Cadmium Fluorescent", "1952"],
						["Mazda", "400W", "MAF/V Mercury Cadmium Fluorescent", "1945"],
						["Philips", "75W", "Philora HPL300 with Sulphide phosphor", "1938"]
					],
					pictures: [
						"/t Osram MAF400.jpg",
						"/t D MAF Mazda MAF400.jpg",
						"/t Philips Philora HPL300 75W.jpg"
					]
				},
				{
					subhead: "Germanate & Arsenate Phosphors",
					intros: [
						["GEC", "    125W", "MBF/V with Magnesium Fluoro-germanate", "1961"],
						["Sylvania", "100W", "H100/C with Magnesium Fluoro-germanate", "1961"],
						["Philips", "250W", "HPL with Magnesium Arsenate", "1965"],
						["Narva", "400W", "HQL-G Goldweiss with Mg Fluoro-germanate", "1971"],
						["Osram", "50W", "HQL half coated demonstration lamp", "1964"]
					],
					pictures: [
						"/t Osram MBF125.jpg",
						"/t Sylvania H100-C.jpg",
						"/t Philips HPL250.jpg",
						"/t Narva HQLG400.jpg",
						"/t D MB Osram HQL50 Halfcoat.jpg"
					]
				},
				{
					subhead: "Orhophosphate Phosphors",
					intros: [
						["GE", "175W", "Bonus Line H175-39/W Impregnated electrodes", "1963"],
						["Westinghouse", "400W", "H400/W with strontium zinc orthophosphate", "1968"],
						["Narva", "250W", "HQL-S Silberweiss with orthphosphate coating", "1969"],
						["Osram", "400W", "HQL-S Silberweiss with orthphosphate coating", "1969"]
					],
					pictures: [
						"/t GE Bonus Line 175.jpg",
						"/t Westinghouse H33.jpg",
						"/t Narva HQLS250.jpg",
						"/t Osram HQLS400.jpg"
					]
				},
				{
					subhead: "Halophosphate Phosphors",
					intros: [["Tesla", "125W", "RVL-B with calcium halophsophate coating", "1971"]],
					pictures: ["/t Tesla RVLB125.jpg"]
				},
				{
					subhead: "Vanadate Phosphors",
					intros: [
						["Polam", "125W", "LRF with Vanadate and Orthophosphate coating", "1976"],
						["Sylvania", "175W", "H175/DX with Yttrium Vanadate coating", "1979"],
						["GEC", "1000W", "MBF/U with Yttrium Vanadate coating", "1977"],
						["Westinghouse", "100W", "H100/DX with Yttrium Phosphate Vanadate", "1983"],
						["Toshiba", "200W", "HFX 200 Japanese style fluorescent mercury", "1990"],
						["DuroTest", "175W", "Safe-T-Vapor lamp with internal oxygen fuse", "c. 1980"],
						["Westinghouse", "400W", "Safety Lifeguard with internal cut-out device", "1981"],
						["Thorn", "125W", "MBF half coated demonstration lamp", "1986"]
					],
					pictures: [
						"/t Polam LRF125.jpg",
						"/t Sylvania H175-DX.jpg",
						"/t GEC MBF1000.jpg",
						"/t Westinghouse H100.jpg",
						"/t Toshiba HF200.jpg",
						"/t Durotest HT175.jpg",
						"/t Westinghouse HT400.jpg",
						"/t Thorn MBF125 half coat.jpg"
					]
				},
				{
					subhead: "Vanadate-Deluxe Phopshors",
					intros: [
						["Sylvania", "400W", "H33-1-GL/WDX Warm Deluxe colour", "1973"],
						["Sylvania", "100W", "H100/N Warmtone with Vanadate + YAG + dye", "1982"],
						["Westinghouse", "400W", "H400/R Beauty Lite with high red ratio", "1982"],
						["Philips", "400W", "HPL Deluxe with Coarse Grain Vanadate coating", "1983"],
						["Philips", "80W", "HPL Comfort with Coarse Vanadate + YAG coating", "1993"],
						["Osram", "50W", "HQL-B Super Deluxe with Vanadate + Gold Laquer", "1993"]
					],
					pictures: [
						"/t D MBF Sylvania H33-1-GL-WDX.jpg",
						"/t Sylvania H38JA100N.jpg",
						"/t Westinghouse H33-R.jpg",
						"/t HID MBF Philips HPLD 400.jpg",
						"/t Philips HPLC80.jpg",
						"/t Osram HQLB50.jpg"
					]
				},
				{
					subhead: "Filtered Yellow Lamps",
					intros: [
						["Westinghouse", "400W", "H400/Y Caution Yellow with external lacquer", "1969"],
						["Osram", "250W", "HQL/5 Caution Yellow with external lacquer", "~1965"]
					],
					pictures: ["/t Westinghouse H33-Y.jpg", "/t Osram Gelb.jpg"]
				},
				{
					subhead: "Fluorescent Reflector Lamps",
					intros: [
						["Philips", "125W", "HPLR E40 Cap Reflector with Arsenate Phosphor", "1969"],
						["GEC", "125W", "MBFR/U Mercury with Ellipsoidal Reflector", "1977"],
						["Thorn", "400W", "MBFR/U Mercury Fluorescent Reflector", "1988"],
						["Meda", "250W", "HML250-PR Side Reflector Streetlighting", "c. 1960s"],
						["Narva", "125W", "NF125-21 Street lighting with ellipsoidal reflector", "1979"],
						["Philips", "400W", "HLRG Horticultural with ellipsoidal reflector", "1975"],
						["SELZ", "400W", "DRLF400-1 Horticultural with ellipsoidal reflector", "1983"]
					],
					pictures: [
						"/t D MBR Philips HPLR125-E40.jpg",
						"/t D MB GEC MBFR125.jpg",
						"/t Thorn MBFR400.jpg",
						"/t D MBR Meda HML250PR.jpg",
						"/t Narva NF125-21.jpg",
						"/t D MBR Philips HLRG400.jpg",
						"/t D MBR SELZ DRLF400-1.jpg"
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
					title: "汞荧光灯",
					description: [
						"高压汞灯富含蓝光、绿光和黄光波长，但几乎完全缺乏红光辐射，这产生了一种冷白色光，其显色性能非常差。最成功的解决方法之一是在外罩上涂覆荧光磷光体，试图将放电产生的部分紫外线转换为更有用的红光波长。",
						"1937年，英国的欧司朗-通用电气（Osram-GEC）成功地应用了铜激活的硫化镉锌磷光体，制造出了第一盏成功的灯具。随后的几十年里，开发出了几十种不同的磷光体，每一种都在降低光的色温、提高显色性以及尽可能提高汞荧光灯的光效方面提供了逐步改进。下面展示了其中一些主要的发展，按磷光体化学类型或预期用途进行分组。"
					]
				},
				{
					subhead: "硫化物荧光粉",
					intros: [
						["GEC", "400W", "MAF/V Mercury Cadmium Fluorescent", "1952"],
						["Mazda", "400W", "MAF/V Mercury Cadmium Fluorescent", "1945"],
						["Philips", "75W", "Philora HPL300 with Sulphide phosphor", "1938"]
					],
					pictures: [
						"/t Osram MAF400.jpg",
						"/t D MAF Mazda MAF400.jpg",
						"/t Philips Philora HPL300 75W.jpg"
					]
				},
				{
					subhead: "锗酸盐与砷酸盐荧光粉",
					intros: [
						["GEC", "    125W", "MBF/V with Magnesium Fluoro-germanate", "1961"],
						["Sylvania", "100W", "H100/C with Magnesium Fluoro-germanate", "1961"],
						["Philips", "250W", "HPL with Magnesium Arsenate", "1965"],
						["Narva", "400W", "HQL-G Goldweiss with Mg Fluoro-germanate", "1971"],
						["Osram", "50W", "HQL half coated demonstration lamp", "1964"]
					],
					pictures: [
						"/t Osram MBF125.jpg",
						"/t Sylvania H100-C.jpg",
						"/t Philips HPL250.jpg",
						"/t Narva HQLG400.jpg",
						"/t D MB Osram HQL50 Halfcoat.jpg"
					]
				},
				{
					subhead: "磷酸盐荧光粉",
					intros: [
						["GE", "175W", "Bonus Line H175-39/W Impregnated electrodes", "1963"],
						["Westinghouse", "400W", "H400/W with strontium zinc orthophosphate", "1968"],
						["Narva", "250W", "HQL-S Silberweiss with orthphosphate coating", "1969"],
						["Osram", "400W", "HQL-S Silberweiss with orthphosphate coating", "1969"]
					],
					pictures: [
						"/t GE Bonus Line 175.jpg",
						"/t Westinghouse H33.jpg",
						"/t Narva HQLS250.jpg",
						"/t Osram HQLS400.jpg"
					]
				},
				{
					subhead: "卤磷酸盐荧光粉",
					intros: [["Tesla", "125W", "RVL-B with calcium halophsophate coating", "1971"]],
					pictures: ["/t Tesla RVLB125.jpg"]
				},
				{
					subhead: "钒酸盐荧光粉",
					intros: [
						["Polam", "125W", "LRF with Vanadate and Orthophosphate coating", "1976"],
						["Sylvania", "175W", "H175/DX with Yttrium Vanadate coating", "1979"],
						["GEC", "1000W", "MBF/U with Yttrium Vanadate coating", "1977"],
						["Westinghouse", "100W", "H100/DX with Yttrium Phosphate Vanadate", "1983"],
						["Toshiba", "200W", "HFX 200 Japanese style fluorescent mercury", "1990"],
						["DuroTest", "175W", "Safe-T-Vapor lamp with internal oxygen fuse", "c. 1980"],
						["Westinghouse", "400W", "Safety Lifeguard with internal cut-out device", "1981"],
						["Thorn", "125W", "MBF half coated demonstration lamp", "1986"]
					],
					pictures: [
						"/t Polam LRF125.jpg",
						"/t Sylvania H175-DX.jpg",
						"/t GEC MBF1000.jpg",
						"/t Westinghouse H100.jpg",
						"/t Toshiba HF200.jpg",
						"/t Durotest HT175.jpg",
						"/t Westinghouse HT400.jpg",
						"/t Thorn MBF125 half coat.jpg"
					]
				},
				{
					subhead: "钒酸盐豪华型荧光粉",
					intros: [
						["Sylvania", "400W", "H33-1-GL/WDX Warm Deluxe colour", "1973"],
						["Sylvania", "100W", "H100/N Warmtone with Vanadate + YAG + dye", "1982"],
						["Westinghouse", "400W", "H400/R Beauty Lite with high red ratio", "1982"],
						["Philips", "400W", "HPL Deluxe with Coarse Grain Vanadate coating", "1983"],
						["Philips", "80W", "HPL Comfort with Coarse Vanadate + YAG coating", "1993"],
						["Osram", "50W", "HQL-B Super Deluxe with Vanadate + Gold Laquer", "1993"]
					],
					pictures: [
						"/t D MBF Sylvania H33-1-GL-WDX.jpg",
						"/t Sylvania H38JA100N.jpg",
						"/t Westinghouse H33-R.jpg",
						"/t HID MBF Philips HPLD 400.jpg",
						"/t Philips HPLC80.jpg",
						"/t Osram HQLB50.jpg"
					]
				},
				{
					subhead: "滤光黄灯",
					intros: [
						["Westinghouse", "400W", "H400/Y Caution Yellow with external lacquer", "1969"],
						["Osram", "250W", "HQL/5 Caution Yellow with external lacquer", "~1965"]
					],
					pictures: ["/t Westinghouse H33-Y.jpg", "/t Osram Gelb.jpg"]
				},
				{
					subhead: "荧光反射灯",
					intros: [
						["Philips", "125W", "HPLR E40 Cap Reflector with Arsenate Phosphor", "1969"],
						["GEC", "125W", "MBFR/U Mercury with Ellipsoidal Reflector", "1977"],
						["Thorn", "400W", "MBFR/U Mercury Fluorescent Reflector", "1988"],
						["Meda", "250W", "HML250-PR Side Reflector Streetlighting", "c. 1960s"],
						["Narva", "125W", "NF125-21 Street lighting with ellipsoidal reflector", "1979"],
						["Philips", "400W", "HLRG Horticultural with ellipsoidal reflector", "1975"],
						["SELZ", "400W", "DRLF400-1 Horticultural with ellipsoidal reflector", "1983"]
					],
					pictures: [
						"/t D MBR Philips HPLR125-E40.jpg",
						"/t D MB GEC MBFR125.jpg",
						"/t Thorn MBFR400.jpg",
						"/t D MBR Meda HML250PR.jpg",
						"/t Narva NF125-21.jpg",
						"/t D MBR Philips HLRG400.jpg",
						"/t D MBR SELZ DRLF400-1.jpg"
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
