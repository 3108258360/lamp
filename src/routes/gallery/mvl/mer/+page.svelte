<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Mercury Ultraviolet",
					description: [
						"In parallel with the invention of the first practical mercury vapour lamp in 1901, it was recognised that these sources provided a powerful emission of ultraviolet radiation in addition to the visible wavelengths. Since the earliest beginnings of the mercury lamp industry, developments have progressed in two parallel domains optimised at improving their properties as light sources, and also as ultraviolet radiation sources. This page is concerned with the latter category.",
						"Whereas the previous sections covering mercury lamp developments have classified the technological improvements in terms of the design and construction of mercury lamps, for the ultraviolet products it is considered more useful to group the different kinds of lamps according to their intended applications as detailed below."
					]
				},
				{
					subhead: "Ultraviolet Suntanning",
					intros: [
						["GE", "400W", "S-1 Ultraviolet Sunlamp, Thermionic discharge", "~1950"],
						["GE", "85W", "S-2 Ultraviolet Sunlamp, Thermionic discharge", "1939"],
						["Philips", "110W", "Ultrasol 5023 Self-Ballasted Sunlamp", "1935"],
						["Sperti", "45W?", "Mercolite Self-Starting Sunlamp type 45QZ", "c.1940"],
						["GE", "100W", "S-4 Sunlamp with Graded Glass Seals", "1940"],
						["Osram", "300W", "Ultra-Vitalux Sunlamp Blended Round", "1941"],
						["Osram", "300W", "Ultra-Vitalux Sunlamp Blended Reflector", "1957"],
						["GE", "275W", "RS Sunlamp Blended Reflector", "1947"],
						["Sylvania", "275W", "RS Sunlamp Blended Reflector", "1966"],
						["Philips", "500W", "Biosol MLU Sunlamp Blended Reflector", "1953"],
						["Philips", "300W", "Ultraphil MLU Sunlamp Blended Reflector", "1968"]
					],
					pictures: [
						"/t GE S1.jpg",
						"/t D MC GE S2.jpg",
						"/t D MC Philips Ultrasol 5023.jpg",
						"/t D MC Sperti Mercolite 45QZ.jpg",
						"/t GE S4.jpg",
						"/t D MBU Osram UltraVitalux-G.jpg",
						"/t D MBU Osram UltraVitalux-R.jpg",
						"/t D MBU GE RS.jpg",
						"/t D MBU Sylvania RS.jpg",
						"/t D MBU Philips MLU500.jpg",
						"/t D MBU Philips MLU300.jpg"
					]
				},
				{
					subhead: "Ultraviolet Germcidal & Ozone",
					intros: [
						["GE", "4W", "G4S11 Ozone Producing Thermionic discharge", "1959"],
						["Osram", "10W", "HNS 10W/U OFR U-Tube Germicidal Ozone Free", "1973"],
						["Philips", "6W", "TUV Germicidal lamp with internal resistance", "1992"]
					],
					pictures: ["/t GE G4S11.jpg", "/t D MC Osram HNS10.jpg", "/t D MC Philips TUV6.jpg"]
				},
				{
					subhead: "Ultraviolet Actinic",
					intros: [
						["Philips", "125W", "HPR Actinic Printing in Reflector Bulb", "1984"],
						["GE-Thorn", "5kW", "MB high wattage photo-printing lamp", "1991"]
					],
					pictures: ["/t Philips HPR125.jpg", "/t Thorn MB5000.jpg"]
				},
				{
					subhead: "Ultraviolet Blacklight",
					intros: [
						["Thorn", "4W", "M2 miniature ultraviolet source", "1975"],
						["Osram", "13W", "HgN miniature UV-A source", "1950"],
						["GE", "4W", "F5000 DC Discharge Fluorescent Blacklight", "1950 c."],
						["SPO Svet", "4W", "LUF-4 DC Discharge Fluorescent Blacklight", "1989"],
						["SELA Abadie", "4W", "Abadie 6002 DC Fluorescent Blacklight", "1992"]
					],
					pictures: [
						"/t D MC Thorn M2.jpg",
						"/t D MC Osram HgN13.jpg",
						"/t D MC GE F5000.jpg",
						"/t D MC Svetotekhnika LUF4.jpg",
						"/t D MC SELA Abadie 6002.jpg"
					]
				},
				{
					subhead: "Ultraviolet Blacklight-Blue",
					intros: [
						["Philips", "20W", "Woods Glass Blacklight Blue", "1941"],
						["Osram", "9W", "HNV miniature Woods' glass blacklight", "1943"],
						["Philips", "6W", "TW Blacklight lamp with internal resistance", "1983"],
						["GE", "100W", "H100-BL4 Purple-X Blacklight Woods Glass", "1971"],
						["Osram", "80W", "HQV Blacklight Woods Glass", "1964"],
						["Thorn", "125W", "MBW Blacklight Woods Glass", "1974"],
						["Philips", "125W", "HPW Blacklight Woods Glass", "1985"],
						["Philips", "125W", "HPW-TS Blacklight with UV-A Phosphor", "1991"],
						["Iwasaki", "400W", "H400BL Blacklight Woods Glass", "1994"],
						["SELZ", "125W", "DRUFZ 125-1 Blacklight Woods Glass Reflector", "1983"]
					],
					pictures: [
						"/t D FL UV Philips TL20W-08.jpg",
						"/t D MC Osram HNV9.jpg",
						"/t D MC Philips TW6.jpg",
						"/t D MBW GE Purple-X.jpg",
						"/t Osram HQV80.jpg",
						"/t Thorn MBW125.jpg",
						"/t Philips HPW125.jpg",
						"/t D MBW Philips HPWTS125.jpg",
						"/t Iwasaki H400BL.jpg",
						"/t D MBW SELZ DRUFZ125.jpg"
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
					title: "紫外线灯",
					description: [
						"与1901年第一盏实用汞蒸气灯的发明同时，人们认识到这些光源除了可见光波长外，还提供了强大的紫外线辐射发射。从汞灯行业最早开始，发展就在两个平行领域进行，分别优化其作为光源和紫外线辐射源的特性。本页面关注的是后者类别。",
						"与前面关于汞灯发展的各节不同，这些节是根据汞灯的设计和构造来分类技术改进的，对于紫外线产品，根据其预期应用将不同类型的灯分组被认为更有用，详细内容如下。"
					]
				},
				{
					subhead: "紫外线美黑",
					intros: [
						["GE", "400W", "S-1 Ultraviolet Sunlamp, Thermionic discharge", "~1950"],
						["GE", "85W", "S-2 Ultraviolet Sunlamp, Thermionic discharge", "1939"],
						["Philips", "110W", "Ultrasol 5023 Self-Ballasted Sunlamp", "1935"],
						["Sperti", "45W?", "Mercolite Self-Starting Sunlamp type 45QZ", "c.1940"],
						["GE", "100W", "S-4 Sunlamp with Graded Glass Seals", "1940"],
						["Osram", "300W", "Ultra-Vitalux Sunlamp Blended Round", "1941"],
						["Osram", "300W", "Ultra-Vitalux Sunlamp Blended Reflector", "1957"],
						["GE", "275W", "RS Sunlamp Blended Reflector", "1947"],
						["Sylvania", "275W", "RS Sunlamp Blended Reflector", "1966"],
						["Philips", "500W", "Biosol MLU Sunlamp Blended Reflector", "1953"],
						["Philips", "300W", "Ultraphil MLU Sunlamp Blended Reflector", "1968"]
					],
					pictures: [
						"/t GE S1.jpg",
						"/t D MC GE S2.jpg",
						"/t D MC Philips Ultrasol 5023.jpg",
						"/t D MC Sperti Mercolite 45QZ.jpg",
						"/t GE S4.jpg",
						"/t D MBU Osram UltraVitalux-G.jpg",
						"/t D MBU Osram UltraVitalux-R.jpg",
						"/t D MBU GE RS.jpg",
						"/t D MBU Sylvania RS.jpg",
						"/t D MBU Philips MLU500.jpg",
						"/t D MBU Philips MLU300.jpg"
					]
				},
				{
					subhead: "紫外线杀菌与臭氧",
					intros: [
						["GE", "4W", "G4S11 Ozone Producing Thermionic discharge", "1959"],
						["Osram", "10W", "HNS 10W/U OFR U-Tube Germicidal Ozone Free", "1973"],
						["Philips", "6W", "TUV Germicidal lamp with internal resistance", "1992"]
					],
					pictures: ["/t GE G4S11.jpg", "/t D MC Osram HNS10.jpg", "/t D MC Philips TUV6.jpg"]
				},
				{
					subhead: "紫外线感光",
					intros: [
						["Philips", "125W", "HPR Actinic Printing in Reflector Bulb", "1984"],
						["GE-Thorn", "5kW", "MB high wattage photo-printing lamp", "1991"]
					],
					pictures: ["/t Philips HPR125.jpg", "/t Thorn MB5000.jpg"]
				},
				{
					subhead: "紫外线黑光",
					intros: [
						["Thorn", "4W", "M2 miniature ultraviolet source", "1975"],
						["Osram", "13W", "HgN miniature UV-A source", "1950"],
						["GE", "4W", "F5000 DC Discharge Fluorescent Blacklight", "1950 c."],
						["SPO Svet", "4W", "LUF-4 DC Discharge Fluorescent Blacklight", "1989"],
						["SELA Abadie", "4W", "Abadie 6002 DC Fluorescent Blacklight", "1992"]
					],
					pictures: [
						"/t D MC Thorn M2.jpg",
						"/t D MC Osram HgN13.jpg",
						"/t D MC GE F5000.jpg",
						"/t D MC Svetotekhnika LUF4.jpg",
						"/t D MC SELA Abadie 6002.jpg"
					]
				},
				{
					subhead: "紫外线黑光-蓝",
					intros: [
						["Philips", "20W", "Woods Glass Blacklight Blue", "1941"],
						["Osram", "9W", "HNV miniature Woods' glass blacklight", "1943"],
						["Philips", "6W", "TW Blacklight lamp with internal resistance", "1983"],
						["GE", "100W", "H100-BL4 Purple-X Blacklight Woods Glass", "1971"],
						["Osram", "80W", "HQV Blacklight Woods Glass", "1964"],
						["Thorn", "125W", "MBW Blacklight Woods Glass", "1974"],
						["Philips", "125W", "HPW Blacklight Woods Glass", "1985"],
						["Philips", "125W", "HPW-TS Blacklight with UV-A Phosphor", "1991"],
						["Iwasaki", "400W", "H400BL Blacklight Woods Glass", "1994"],
						["SELZ", "125W", "DRUFZ 125-1 Blacklight Woods Glass Reflector", "1983"]
					],
					pictures: [
						"/t D FL UV Philips TL20W-08.jpg",
						"/t D MC Osram HNV9.jpg",
						"/t D MC Philips TW6.jpg",
						"/t D MBW GE Purple-X.jpg",
						"/t Osram HQV80.jpg",
						"/t Thorn MBW125.jpg",
						"/t Philips HPW125.jpg",
						"/t D MBW Philips HPWTS125.jpg",
						"/t Iwasaki H400BL.jpg",
						"/t D MBW SELZ DRUFZ125.jpg"
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
