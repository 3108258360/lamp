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
						"The possibility of employing ceramic arc tubes for metal halide lamps is not a new idea - indeed their use was proposed in the earliest patents on metal halide lamps back in the 1960's. Their potential advantages were recognised even at that time, in that they are more resistant than quartz to the corrosive nature of the metal halide salts within the arc tube. In addition they can operate at temperatures beyond which quartz begins to soften. Ceramics thus offer the possibility to increase the loading in the arc tube, bringing about an increase in wall temperature, which in turn increases colour rendering properties and luminous efficacy.",
						"However while the ceramic arc tube itself is more resistant to halide corrosion, the same cannot be said of the end seals where the metal lead wires pass through the ceramic. The end seals must be kept at low enough temperatures to reduce the rate of corrosion, and traditional metals known for ceramic to metal seals cannot be exposed to the halides.",
						"The first practical solution to this problem was developed by Thorn Lighting in England during the early 1980s, and in 1981 that company exhibited the world's first Ceramic Metal Halide lamp at the Hannover World Light Fair. This so-called 'TSH' lamp is illustrated below, and employs electrically conductive cermet caps to close the ends of the arc tube and make a halide-resistant seal. The unique molecular spectrum of the tin chloride dose also resulted in rather good colour properties for its time. But the marketing division did not take the idea further, since this lamp required a special kind ballast that was not available.",
						"The commercial introduction of ceramic lamps had to wait until 1994 when Philips unveiled its 'CDM' range having the 'Protruding Plug' kind of end seal. In this approach the seal is displaced some distance away from the heat of the arc tube, thus bringing its temperature down to safe limits. An ingenious arrangement of different metallic conductors is contained within the seal both to ensure halide resistance and prevent cracking of these delicate seals. All subsequent lamps are based on this and later variants of the protruding plug seal."
					]
				},
				{
					subhead: "Early Prototypes and Experimental Lamps",
					intros: [
						["Thorn", "250W", "Very early experimental sapphire metal halide", "~1975"],
						["Thorn", "150W", "TSH Tin Sodium Halide with Cermet seals", "~1981"],
						["Thorn", "150W", "TSH Tin Sodium Halide with Corstar arc tube", "~1981"],
						["Thorn", "70W", "CMH Ceramic Metal Halide with cermet seals", "~1983"],
						["Toto", "70W", "CMI-T with Transparent YAG ceramic arc tube", "~1999"]
					],
					pictures: [
						"/t D MHC Thorn MBIT250 Corstar.jpg",
						"/t D MHC Thorn TSH150.jpg",
						"/t Thorn TSH150 Corstar.jpg",
						"/t Thorn CMH70.jpg",
						"/t Toto YAG70.jpg"
					]
				},
				{
					subhead: "Compact Single-Ended Lamps",
					intros: [
						["Philips", "35W", "CDM-T Mastercolour5pc extruded arc tube", "1994"],
						["GE", "70W", "CMH-T ConstantColor5pc extruded arc tube", "1997"],
						["Osram", "35W", "HCI-T Powerstar5pc pressed arc tube", "1997"],
						["Sylvania", "70W", "CMI-T Metalarc1pc slip-cast arc tube", "1997"],
						["GE", "150W", "CMH-T ConstantColor3pc injection-moulded", "1999"],
						["GE", "20W", "CMH-TC first 20W lamp3pc thin-wall arc tube", "2001"],
						["Osram", "150W", "HCI-T Powerball2pc injection-moulded", "2003"],
						["Philips", "70W", "CDM-T Elite Dimmable5pc extruded arc tube", "2005"],
						["Osram", "70W", "HCI-TC Powerball Shoplight high CRI", "2007"],
						["Philips", "35W", "CDM-TC Elite2pc cylindrical arc tube", "2007"],
						["Philips", "100W", "CDM-T Elite 100W2pc ellipsoidal arc tube", "2010"],
						["Philips", "70W", "CDM-T Elite LightboostUnsaturated Dimmable", "2011"],
						["Osram", "70W", "HCI-T Powerball non-radioactive design", "2011"],
						["Philips", "70W", "CDM-T EvolutionUltra high efficacy", "2017"]
					],
					pictures: [
						"/t Philips CDMT35.jpg",
						"/t D MHC GE CMHT70-830 5pc.jpg",
						"/t D MHC Osram HCIT35-WDL 5pc.jpg",
						"/t D MHC Sylvania CMIT70WDL 1pc-cylindrical.jpg",
						"/t D MHC GE CMHT150-830 3pc.jpg",
						"/t GE CMHTC20.jpg",
						"/t D MHC Osram HCIT150WDL Powerball.jpg",
						"/t D MHC Philips CDMT70-930 Elite 5pc.jpg",
						"/t D MHC Osram HCITC70-930 Powerball Shoplight.jpg",
						"/t D MHC Philips CDMTC35-930 Elite 2pc.jpg",
						"/t D MHC Philips CDMT100-930 Elite 2pc.jpg",
						"/t D MHC Philips CDMT70-930 ELB.jpg",
						"/t D MHC Osram HCIT70-WDL Powerball RF.jpg",
						"/t D MHC Philips CDMT70-930 Evo.jpg"
					]
				},
				{
					subhead: "Double-Ended Lamps",
					intros: [
						["Philips", "150W", "CDM-TD Mastercolour double-ended", "1997"],
						["KK Light", "150W", "First Chinese Ceramic Metal Halide", "2002"]
					],
					pictures: ["/t Philips CDMTD150.jpg", "/t KK CDMTD150.jpg"]
				},
				{
					subhead: "Screwbase Lamps",
					intros: [
						["Philips", "70W", "CDM-E Ellipsoidal Fluorescent for U.S.A.", "1994"],
						["Iwasaki", "150W", "Ceralux MT150-CEW with Cermet end seals", "2002"],
						["G.S.", "230W", "Lamp of Japan Storage Battery Company", "2001"],
						["Philips", "400W", "HPS Retro-White High Wattage CDM", "2001"],
						["Osram", "250W", "HCI-T Poweball 2-Part elliptical arc tube", "2002"],
						["GE", "250W", "CMH-TT 250W / 830 Single Piece Arc Tube", "2003"],
						["Sylvania", "85W", "Relumina 85W Retrofit for 125W Mercury", "2015"]
					],
					pictures: [
						"/t Philips CDME70.jpg",
						"/t Iwasaki MT150CEW with box.jpg",
						"/t GS CMH230.jpg",
						"/t Philips CDM400.jpg",
						"/t Osram Powerball HCI-T250.jpg",
						"/t GE CMH-TT 250W.jpg",
						"/t D MHC Sylvania Relumina 85W.jpg"
					]
				},
				{
					subhead: "Reflector Lamps",
					intros: [
						["Philips", "35W", "Mastercolour CDM-R PAR30 Reflector", "1997"],
						["Philips", "35W", "Mastercolour CDM-R111 Aluminium Reflector", "2003"],
						["GE", "20W", "CMH ConstantColour MR16 Spot Reflector", "2005"],
						["Philips", "25W", "CDMR-i Self Ballasted Reflector Format", "2005"]
					],
					pictures: [
						"/t Philips CDMR30.jpg",
						"/t Philips CDMR111.jpg",
						"/t GE CMH20 MR16SP.jpg",
						"/t Philips CDMRi 25W.jpg"
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
					title: "金属卤化物 - 陶瓷",
					description: [
						"使用陶瓷弧光管制造金属卤化物灯并非新想法 — 实际上早在20世纪60年代金属卤化物灯的最早专利中就提出了这种用法。当时就已认识到其潜在优势，即陶瓷比石英更具耐腐蚀性，能够抵御弧光管内金属卤化物盐的腐蚀。此外，陶瓷可以在超过石英开始软化的温度下运行。因此，陶瓷提供了提高弧光管负荷的可能性，进而提高管壁温度，这反过来又提升了显色性能和发光效率。",
						"尽管陶瓷弧光管本身对卤化物腐蚀具有更强的抵抗力，但引线穿过陶瓷的端部密封却并非如此。必须将端部密封的温度保持在足够低的水平，以减缓腐蚀速率，而且用于陶瓷与金属密封的传统金属不能暴露在卤化物中。",
						"英国的Thorn Lighting公司在20世纪80年代初率先提出了这一问题的实际解决方案，并于1981年在汉诺威世界照明博览会上展出了世界上第一盏陶瓷金属卤化物灯。这种所谓的“TSH”灯如图所示，采用导电陶瓷金属复合材料帽封闭弧光管的两端，并形成一种耐卤化物的密封。独特的氯化锡分子光谱也使其在当时具有相当不错的色彩特性。但由于这种灯需要一种当时无法获得的特殊镇流器，市场部门并未进一步推广这一理念。",
						"陶瓷灯的商业推出一直等到1994年，当时飞利浦公司推出了其“CDM”系列，采用“突出插头”式的端部密封。在这种设计中，密封部分被移至距离弧光管热量较远的地方，从而使其温度降至安全范围。密封部分内含不同金属导体的独特排列，既能确保耐卤化物腐蚀，又能防止这些脆弱的密封部分开裂。此后所有的灯都基于这种突出插头密封及其后续变体。"
					]
				},
				{
					subhead: "早期原型和实验灯",
					intros: [
						["Thorn", "250W", "Very early experimental sapphire metal halide", "~1975"],
						["Thorn", "150W", "TSH Tin Sodium Halide with Cermet seals", "~1981"],
						["Thorn", "150W", "TSH Tin Sodium Halide with Corstar arc tube", "~1981"],
						["Thorn", "70W", "CMH Ceramic Metal Halide with cermet seals", "~1983"],
						["Toto", "70W", "CMI-T with Transparent YAG ceramic arc tube", "~1999"]
					],
					pictures: [
						"/t D MHC Thorn MBIT250 Corstar.jpg",
						"/t D MHC Thorn TSH150.jpg",
						"/t Thorn TSH150 Corstar.jpg",
						"/t Thorn CMH70.jpg",
						"/t Toto YAG70.jpg"
					]
				},
				{
					subhead: "紧凑型单端灯",
					intros: [
						["Philips", "35W", "CDM-T Mastercolour5pc extruded arc tube", "1994"],
						["GE", "70W", "CMH-T ConstantColor5pc extruded arc tube", "1997"],
						["Osram", "35W", "HCI-T Powerstar5pc pressed arc tube", "1997"],
						["Sylvania", "70W", "CMI-T Metalarc1pc slip-cast arc tube", "1997"],
						["GE", "150W", "CMH-T ConstantColor3pc injection-moulded", "1999"],
						["GE", "20W", "CMH-TC first 20W lamp3pc thin-wall arc tube", "2001"],
						["Osram", "150W", "HCI-T Powerball2pc injection-moulded", "2003"],
						["Philips", "70W", "CDM-T Elite Dimmable5pc extruded arc tube", "2005"],
						["Osram", "70W", "HCI-TC Powerball Shoplight high CRI", "2007"],
						["Philips", "35W", "CDM-TC Elite2pc cylindrical arc tube", "2007"],
						["Philips", "100W", "CDM-T Elite 100W2pc ellipsoidal arc tube", "2010"],
						["Philips", "70W", "CDM-T Elite LightboostUnsaturated Dimmable", "2011"],
						["Osram", "70W", "HCI-T Powerball non-radioactive design", "2011"],
						["Philips", "70W", "CDM-T EvolutionUltra high efficacy", "2017"]
					],
					pictures: [
						"/t Philips CDMT35.jpg",
						"/t D MHC GE CMHT70-830 5pc.jpg",
						"/t D MHC Osram HCIT35-WDL 5pc.jpg",
						"/t D MHC Sylvania CMIT70WDL 1pc-cylindrical.jpg",
						"/t D MHC GE CMHT150-830 3pc.jpg",
						"/t GE CMHTC20.jpg",
						"/t D MHC Osram HCIT150WDL Powerball.jpg",
						"/t D MHC Philips CDMT70-930 Elite 5pc.jpg",
						"/t D MHC Osram HCITC70-930 Powerball Shoplight.jpg",
						"/t D MHC Philips CDMTC35-930 Elite 2pc.jpg",
						"/t D MHC Philips CDMT100-930 Elite 2pc.jpg",
						"/t D MHC Philips CDMT70-930 ELB.jpg",
						"/t D MHC Osram HCIT70-WDL Powerball RF.jpg",
						"/t D MHC Philips CDMT70-930 Evo.jpg"
					]
				},
				{
					subhead: "双端灯",
					intros: [
						["Philips", "150W", "CDM-TD Mastercolour double-ended", "1997"],
						["KK Light", "150W", "First Chinese Ceramic Metal Halide", "2002"]
					],
					pictures: ["/t Philips CDMTD150.jpg", "/t KK CDMTD150.jpg"]
				},
				{
					subhead: "螺口灯",
					intros: [
						["Philips", "70W", "CDM-E Ellipsoidal Fluorescent for U.S.A.", "1994"],
						["Iwasaki", "150W", "Ceralux MT150-CEW with Cermet end seals", "2002"],
						["G.S.", "230W", "Lamp of Japan Storage Battery Company", "2001"],
						["Philips", "400W", "HPS Retro-White High Wattage CDM", "2001"],
						["Osram", "250W", "HCI-T Poweball 2-Part elliptical arc tube", "2002"],
						["GE", "250W", "CMH-TT 250W / 830 Single Piece Arc Tube", "2003"],
						["Sylvania", "85W", "Relumina 85W Retrofit for 125W Mercury", "2015"]
					],
					pictures: [
						"/t Philips CDME70.jpg",
						"/t Iwasaki MT150CEW with box.jpg",
						"/t GS CMH230.jpg",
						"/t Philips CDM400.jpg",
						"/t Osram Powerball HCI-T250.jpg",
						"/t GE CMH-TT 250W.jpg",
						"/t D MHC Sylvania Relumina 85W.jpg"
					]
				},
				{
					subhead: "反射灯",
					intros: [
						["Philips", "35W", "Mastercolour CDM-R PAR30 Reflector", "1997"],
						["Philips", "35W", "Mastercolour CDM-R111 Aluminium Reflector", "2003"],
						["GE", "20W", "CMH ConstantColour MR16 Spot Reflector", "2005"],
						["Philips", "25W", "CDMR-i Self Ballasted Reflector Format", "2005"]
					],
					pictures: [
						"/t Philips CDMR30.jpg",
						"/t Philips CDMR111.jpg",
						"/t GE CMH20 MR16SP.jpg",
						"/t Philips CDMRi 25W.jpg"
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
