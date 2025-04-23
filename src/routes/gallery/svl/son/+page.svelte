<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "SON High Pressure Sodium",
					description: [
						"The High Pressure Sodium lamp is the invention of General Electric USA, although Osram-GEC and Associated Electrical Industries of Britain were also key players in the race to be first to create this lamp. The fundamental principle behind the lamp is that the narrow, monochromatic sodium resonance lines can be considerably broadened if the sodium vapour pressure is increased. However, higher wall temperatures are required to achieve this and the advanced glasses which can just about withstand sodium attack in the low pressure lamp become blackened in a matter of minutes at higher temperature.",
						"The key to the success of the high pressure sodium lamp is an arc tube fabricated of translucent ceramic, since there is no known glass which withstands the corrosion of sodium at high temperature. Aluminium oxide (alumina) is the chosen ceramic since, when combined with minute traces of dopants to control the grain structure, it can be made translucent by a process which is suited to mass production.",
						"Once the ceramic tube is made, the problem of sealing an electrical conductor through it must then be faced. It is standard practice to use special sealing glasses, but these still represent a weak point in the lamp design. Other designs are liable to cracking or may leak over time. The lamps on this page highlight many of the different sealing techniques which have been tried, while also representing a broad selection of the different lamp styles that have been made available over the years."
					]
				},
				{
					subhead: "Standard Lamps",
					intros: [
						["GE", "500W", "Early Prototype of First Lucalox Lamp", "~1965"],
						["GE", "400W", "LU400/BD with external amalgam reservoir", "1971"],
						["GE", "1000W", "LU1000/BD with auxiliary electrode", "~1971"],
						["GE", "250W", "LU250 Universal with butterfly crimp reservoir", "1983"],
						["GE", "125W?", "LU125/BD low power experimental lamp", "~1970"],
						["GE", "70W", "First 70W-LV lamp, with Molybdenum heat pipe", "1976"],
						["GE", "50W", "LU50 Early low wattage with niobium wire seals", "1980"],
						["GE", "70W", "LU70/90/T10/27 Compact Tubular", "1992"],
						["GE", "1000W", "LU1000 with voltage fuse in outer jacket", "1980"],
						["GE Mexico", "150W", "LU150 55-Volt of Mexican Design", "~1985"],
						["Tesla", "400W", "Early Czech lamp with metal end seals", "1967"],
						["Atlas", "250W", "Early British KolorSON with metal end seals", "1969"],
						["Philips", "400W", "SON-T 400W with monolithic ceramic seals", "1971"],
						["Westinghouse", "150W", "C150S56 Canadian lamp with niobium cup seals", "1974"],
						["Tungsram", "400W", "TC 400 with unusual large end seals", "c. 1975"],
						["Thorn", "70W", "First 70W-HV lamp, with wide bore arc tube", "1976"],
						["Thorn", "70W", "Early low wattage lamp with large bore arc tube", "1983"],
						["Thorn", "50W", "Early low wattage lamp with large bore arc tube", "1987"],
						["Polamp", "400W", "WLS 400 with early Niobium cup seals", "1978"],
						["Philips", "250W", "SON-T with scraped-tip electrode assembly", "1980"],
						["Norleco", "250W", "SON-T of Philips American design", "1980"],
						["Sylvania", "200W", "Lumalux LU200 of unusual power rating", "1982"],
						["Thorn", "400W", "SON-T with prototype Cermet arc tube seal", "1983"],
						["Tungsram", "250W", "TC 250W with double niobium wire seals", "1985"],
						["PZGRL", "400W", "DNaT 400-4 of early Ukranian design", "1985"],
						["Tesla", "70W", "SHC with Monolithic 2-Piece PCA design", "1987"],
						["Thorn", "1000W", "SON-T 1000W with narrow bore Nb seals", "1988"],
						["Thorn", "70W", "SON-T with cermet arc tube seals", "c. 1991"],
						["Osram", "70W", "SON-Plus with side arm to measure vacuum", "1991"]
					],
					pictures: [
						"/t D SHP GE LU500.jpg",
						"/t D SHP GE LU400BD.jpg",
						"/t D SHP GE LU1000BD.jpg",
						"/t D SHP GE LU250.jpg",
						"/t D SHP GE LU125BD.jpg",
						"/t D SHP GE LU70BU.jpg",
						"/t D SHP GE LU50A.jpg",
						"/t D SHP GE LU70-90-T10-27.jpg",
						"/t D SHP GE LU1000.jpg",
						"/t D SHP GE LU150-55 Mexico.jpg",
						"/t D SHP Tesla SHC400 Nb-cup.jpg",
						"/t Atlas SONT250.jpg",
						"/t D SHP Philips SONT400.jpg",
						"/t Westinghouse C150S56.jpg",
						"/t D SHP Orion TC400.jpg",
						"/t D SHP Thorn SONE70.jpg",
						"/t Thorn SONT70.jpg",
						"/t D SHP Thorn SONT50.jpg",
						"/t D SHP Polamp WLS400.jpg",
						"/t Philips SONT250.jpg",
						"/t Philips SON-USA 250W.jpg",
						"/t Sylvania LU200.jpg",
						"/t D SHP Thorn SONT400 Cermet.jpg",
						"/t Tungsram LU250.jpg",
						"/t D SHP GRL DNaT400-4.jpg",
						"/t Tesla SHC70 Monolithic.jpg",
						"/t D SHP Thorn SONT1000.jpg",
						"/t Thorn SON70 Cermet.jpg",
						"/t Osram SONPT70 Test.jpg"
					]
				},
				{
					subhead: "Diffuse Outer Bulb",
					intros: [
						["Philips", "400W", "SON-E 400W with diffuse outer envelope", "1971"],
						["Atlas", "400W", "KolorSON 400W with diffuse outer envelope", "1974"],
						["Thorn", "40W", "SON-E Experimental low wattage lamp", "~1983"],
						["GE-Thorn", "50W", "SON-E with pearl glass outer envelope", "1992"],
						["Philips", "250W", "Tubular SON with Coated Outer Bulb", "~1985"],
						["GE", "50W", "LU50/90/D/27 with diffuse outer envelope", "1987"],
						["Osram", "70W", "NAV-E 70W/NB low voltage for Leipzig City", "1993"]
					],
					pictures: [
						"/t D SHP Philips SONE400.jpg",
						"/t D SHP Atlas SONE400.jpg",
						"/t D SHP Thorn SONE40 Pearl.jpg",
						"/t D SHP Thorn SONE50 Pearl.jpg",
						"/t D SHP Philips SONT250 Coated.jpg",
						"/t D SHP GE LU50D.jpg",
						"/t D SHP Osram NAVE70NB.jpg"
					]
				},
				{
					subhead: "Transparent Arc Tube",
					intros: [
						["GE", "100W", "Flux polished polycrystalline arc tube", "1976"],
						["Westinghouse", "400W", "Corstar single crystal sapphire arc tube", "1977"],
						["Thorn", "400W", "Corstar single crystal sapphire arc tube", "1981"],
						["Thorn", "70W", "Corstar single crystal sapphire arc tube", "~1983"]
					],
					pictures: [
						"/t D SHP GE LU100BD.jpg",
						"/t Westinghouse Corstar 400.jpg",
						"/t D SHP Thorn SONT400 Corstar.jpg",
						"/t Thorn SON70 Corstar.jpg"
					]
				},
				{
					subhead: "Instant-Restrike Twin Arc Designs",
					intros: [["Sylvania", "400W", "SHP-Standby twin arc tubes for hot restrike", "1989"]],
					pictures: ["/t Sylvania SON2T400.jpg"]
				},
				{
					subhead: "Self-Starting & Mercury Retrofit Designs",
					intros: [
						["OsramGEC", "310W", "Solarcolour Plug-In Mercury lamp retrofit", "1969"],
						["OsramGEC", "120W", "SON-I with internal snap-switch starter", "1976"],
						["Sylvania", "360W", "Unalux Penning-Start Mercury lamp retrofit", "1982"],
						["GE", "215W", "E-Z Lux Penning-Start Mercury lamp retrofit", "1988"],
						["Philips", "70W", "SON/I with internal glowbottle starter", "1980"],
						["GE", "70W", "LU70/90/D/I/27 internal electronic ignitor", "1990"],
						["Iwasaki", "150W", "Ignitron NHT150-I with internal FEC ignitor", "1997"],
						["Iwasaki", "150W", "SunluxUltra NH150CE Unsaturated Vapour", "2000"],
						["Sylvania", "69/108W", "SPX EcoArc Unsaturated Mercury Retrofit", "2009"]
					],
					pictures: [
						"/t D SHP GEC SONI310.jpg",
						"/t GEC SONI120.jpg",
						"/t D HPS Sylvania ULX360.jpg",
						"/t D SHP GE LUH215.jpg",
						"/t D SHP Philips SON70I.jpg",
						"/t D SHP GE LU70-90-D-I-27.jpg",
						"/t Iwasaki Ignitron T150.jpg",
						"/t Iwasaki NH150CE.jpg",
						"/t D SHP Sylvania SPX69-108.jpg"
					]
				},
				{
					subhead: "Enhanced Efficacy Designs",
					intros: [
						["GE", "250W", "LU250/BD/S with Superior Performance", "1977"],
						["OsramGEC", "310W", "Solarcolour Plus early high efficacy lamp", "1987"],
						["GE-Thorn", "70W", "SON XL-T with Cermet arc tube seals", "1991"],
						["GE-Thorn", "400W", "SON XL-T with sintered moly antenna on tube", "1991"],
						["Sylvania", "100W", "SHP-MF Mercury-Free high pressure sodium", "1996"],
						["GE", "70W", "Lucalox XO with monolithic arc tube", "2008"]
					],
					pictures: [
						"/t D SHP GE LU250-BD-S.jpg",
						"/t D SHP GEC SONPT310.jpg",
						"/t D SHP Thorn SONXLT70 Cermet.jpg",
						"/t Thorn SONXL400.jpg",
						"/t Sylvania SHP-MF100.jpg",
						"/t D SHP GE LU70XO.jpg"
					]
				},
				{
					subhead: "Deluxe Colour",
					intros: [
						["Westinghouse", "250W", "Ceramalux-4 first deluxe HPS C250S50/DX4", "1982"],
						["OsramGEC", "400W", "Solarcolour SONDL-T Deluxe Colour", "1985"],
						["Thorn", "400W", "SONDL-T Deluxe Colour", "1988"],
						["Philips", "250W", "SON-T Comfort Deluxe Colour", "1989"],
						["GE", "400W", "Lucalox LU400/DX/40 Deluxe Colour", "1998"],
						["Thorn", "400W", "SON-Deluxe with dichroic filter sleeve", "~1983"]
					],
					pictures: [
						"/t D SHP Westinghouse C250S50DX4.jpg",
						"/t D SHP GEC SONDLT400.jpg",
						"/t D SHP Thorn SONDLT400.jpg",
						"/t D SHP Philips SONT250 Comfort.jpg",
						"/t D SHP GE LU400DX.jpg",
						"/t Thorn SONDL400 IR.jpg"
					]
				},
				{
					subhead: "White Light",
					intros: [
						["Matsushita", "50W", "K-HICA-Light White with elliptical arc tube", "~1985"],
						["Iwasaki", "50W", "NHT50 SDX White SON High Colour Rendering", "~1985"],
						["Philips", "50W", "SDW-T White SON with high CRI", "1991"],
						["Philips", "50W", "SDW-R White SON Blown Reflector", "Early 1980s"],
						["Philips", "22W", "SDW-AR White SON Crown Silver Replica", "1986 + 2018"],
						["GE", "95W", "White Lucalox for Pulsed Operation", "1990"],
						["Philips", "150W", "SON-T Deco for City Beatification projects", "1995"],
						["Philips", "100W", "SDW-TG Reduced size Mini WhiteSON", "2002"],
						["Osram", "80W", "ColorStar DSX-T with Variable Colour Output", "1998"]
					],
					pictures: [
						"/t National SON50.jpg",
						"/t Iwasaki NHT50SDX.jpg",
						"/t Philips SDWT50.jpg",
						"/t D SHP Philips SDWR50.jpg",
						"/t D SHP Philips SDW-AR22.jpg",
						"/t D SHP GE LU95.jpg",
						"/t Philips SONTDeco150.jpg",
						"/t Philips SDWTG100.jpg",
						"/t HID HPS Osram DSX-T.jpg"
					]
				},
				{
					subhead: "Reflector Style",
					intros: [
						["Westinghouse", "70W", "Ceramalux C70S62/PAR Dichroic for Coal Mines", "1970s"],
						["Osram", "310/360W", "SON-R Mercury-Retrofit high pressure sodium", "1998"],
						["Thorn", "70W", "SON-R Reflector style high pressure sodium", "1982"],
						["Reflux", "250W", "Reflux lamp with special side reflector", "2003"]
					],
					pictures: [
						"/t D SHP Westinghouse C70S62PAR.jpg",
						"/t D SHP Osram SONR310.jpg",
						"/t D SHP Thorn SONR70.jpg",
						"/t Reflux250.jpg"
					]
				},
				{
					subhead: "Linear Style",
					intros: [
						["Thorn", "250W", "SON-TD Quartzray Gas-filled Linear style", "1981"],
						["Thorn", "400W", "SON-TD Quartzray Gas-filled Linear style", "1987"],
						["Thorn", "1000W", "SON-TD Quartzray Gas-filled Linear style", "~1990"],
						["GEC", "250W", "SON-L SolarStream Gas-filled Linear style", "1996"],
						["Osram", "400W", "NAV-TS Vialox Standard Gas-filled Linear style", "1989"],
						["Osram", "150W", "SON-TS Super double ended design", "2000"],
						["COBR", "400W", "WLS-TC Double ended quartz prototype", "~2000"],
						["Philips", "1000W", "Master GreenPower Horticultural Linear", "2005"]
					],
					pictures: [
						"/t D SHP Thorn SONTD250.jpg",
						"/t Thorn SONTD400.jpg",
						"/t D SHP Thorn SONTD1000.jpg",
						"/t%20Osram%20SONL250.jpg",
						"/t Osram NAVTS400.jpg",
						"/t Osram SONTS150.jpg",
						"/t D SHP COBR WLSTC400.jpg",
						"/t Philips SONTD Greenpower 1000.jpg"
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
					title: "SON 高压钠灯",
					description: [
						"高压钠灯是美国通用电气（General Electric USA）的发明，尽管欧司朗-通用电气（Osram-GEC）和英国的联合电气工业公司（Associated Electrical Industries）也是在创造这种灯具的竞赛中率先取得突破的关键参与者。该灯具的基本原理是，如果提高钠蒸气压力，狭窄的单色钠共振线可以显著加宽。然而，要实现这一点需要更高的壁温，而在低压灯中勉强能够承受钠侵蚀的高级玻璃在更高温度下几分钟内就会变黑。",
						"高压钠灯成功的关键在于使用半透明陶瓷制成的弧光管，因为没有已知的玻璃能够在高温下承受钠的腐蚀。选择氧化铝（刚玉）作为陶瓷材料，因为当与微量掺杂剂结合以控制晶粒结构时，它可以通过一种适合大规模生产的工艺制成半透明。",
						"一旦制成陶瓷管，接下来必须面对的问题是如何将电导体密封穿过它。使用特殊的密封玻璃是标准做法，但这些仍然是灯具设计中的薄弱环节。其他设计可能会开裂，或者随着时间的推移可能会泄漏。这一页上的灯具展示了多年来尝试过的许多不同的密封技术，同时也代表了多年来推出的不同灯具风格的广泛选择。"
					]
				},
				{
					subhead: "标准灯具",
					intros: [
						["GE", "500W", "Early Prototype of First Lucalox Lamp", "~1965"],
						["GE", "400W", "LU400/BD with external amalgam reservoir", "1971"],
						["GE", "1000W", "LU1000/BD with auxiliary electrode", "~1971"],
						["GE", "250W", "LU250 Universal with butterfly crimp reservoir", "1983"],
						["GE", "125W?", "LU125/BD low power experimental lamp", "~1970"],
						["GE", "70W", "First 70W-LV lamp, with Molybdenum heat pipe", "1976"],
						["GE", "50W", "LU50 Early low wattage with niobium wire seals", "1980"],
						["GE", "70W", "LU70/90/T10/27 Compact Tubular", "1992"],
						["GE", "1000W", "LU1000 with voltage fuse in outer jacket", "1980"],
						["GE Mexico", "150W", "LU150 55-Volt of Mexican Design", "~1985"],
						["Tesla", "400W", "Early Czech lamp with metal end seals", "1967"],
						["Atlas", "250W", "Early British KolorSON with metal end seals", "1969"],
						["Philips", "400W", "SON-T 400W with monolithic ceramic seals", "1971"],
						["Westinghouse", "150W", "C150S56 Canadian lamp with niobium cup seals", "1974"],
						["Tungsram", "400W", "TC 400 with unusual large end seals", "c. 1975"],
						["Thorn", "70W", "First 70W-HV lamp, with wide bore arc tube", "1976"],
						["Thorn", "70W", "Early low wattage lamp with large bore arc tube", "1983"],
						["Thorn", "50W", "Early low wattage lamp with large bore arc tube", "1987"],
						["Polamp", "400W", "WLS 400 with early Niobium cup seals", "1978"],
						["Philips", "250W", "SON-T with scraped-tip electrode assembly", "1980"],
						["Norleco", "250W", "SON-T of Philips American design", "1980"],
						["Sylvania", "200W", "Lumalux LU200 of unusual power rating", "1982"],
						["Thorn", "400W", "SON-T with prototype Cermet arc tube seal", "1983"],
						["Tungsram", "250W", "TC 250W with double niobium wire seals", "1985"],
						["PZGRL", "400W", "DNaT 400-4 of early Ukranian design", "1985"],
						["Tesla", "70W", "SHC with Monolithic 2-Piece PCA design", "1987"],
						["Thorn", "1000W", "SON-T 1000W with narrow bore Nb seals", "1988"],
						["Thorn", "70W", "SON-T with cermet arc tube seals", "c. 1991"],
						["Osram", "70W", "SON-Plus with side arm to measure vacuum", "1991"]
					],
					pictures: [
						"/t D SHP GE LU500.jpg",
						"/t D SHP GE LU400BD.jpg",
						"/t D SHP GE LU1000BD.jpg",
						"/t D SHP GE LU250.jpg",
						"/t D SHP GE LU125BD.jpg",
						"/t D SHP GE LU70BU.jpg",
						"/t D SHP GE LU50A.jpg",
						"/t D SHP GE LU70-90-T10-27.jpg",
						"/t D SHP GE LU1000.jpg",
						"/t D SHP GE LU150-55 Mexico.jpg",
						"/t D SHP Tesla SHC400 Nb-cup.jpg",
						"/t Atlas SONT250.jpg",
						"/t D SHP Philips SONT400.jpg",
						"/t Westinghouse C150S56.jpg",
						"/t D SHP Orion TC400.jpg",
						"/t D SHP Thorn SONE70.jpg",
						"/t Thorn SONT70.jpg",
						"/t D SHP Thorn SONT50.jpg",
						"/t D SHP Polamp WLS400.jpg",
						"/t Philips SONT250.jpg",
						"/t Philips SON-USA 250W.jpg",
						"/t Sylvania LU200.jpg",
						"/t D SHP Thorn SONT400 Cermet.jpg",
						"/t Tungsram LU250.jpg",
						"/t D SHP GRL DNaT400-4.jpg",
						"/t Tesla SHC70 Monolithic.jpg",
						"/t D SHP Thorn SONT1000.jpg",
						"/t Thorn SON70 Cermet.jpg",
						"/t Osram SONPT70 Test.jpg"
					]
				},
				{
					subhead: "漫射外罩",
					intros: [
						["Philips", "400W", "SON-E 400W with diffuse outer envelope", "1971"],
						["Atlas", "400W", "KolorSON 400W with diffuse outer envelope", "1974"],
						["Thorn", "40W", "SON-E Experimental low wattage lamp", "~1983"],
						["GE-Thorn", "50W", "SON-E with pearl glass outer envelope", "1992"],
						["Philips", "250W", "Tubular SON with Coated Outer Bulb", "~1985"],
						["GE", "50W", "LU50/90/D/27 with diffuse outer envelope", "1987"],
						["Osram", "70W", "NAV-E 70W/NB low voltage for Leipzig City", "1993"]
					],
					pictures: [
						"/t D SHP Philips SONE400.jpg",
						"/t D SHP Atlas SONE400.jpg",
						"/t D SHP Thorn SONE40 Pearl.jpg",
						"/t D SHP Thorn SONE50 Pearl.jpg",
						"/t D SHP Philips SONT250 Coated.jpg",
						"/t D SHP GE LU50D.jpg",
						"/t D SHP Osram NAVE70NB.jpg"
					]
				},
				{
					subhead: "透明弧光管",
					intros: [
						["GE", "100W", "Flux polished polycrystalline arc tube", "1976"],
						["Westinghouse", "400W", "Corstar single crystal sapphire arc tube", "1977"],
						["Thorn", "400W", "Corstar single crystal sapphire arc tube", "1981"],
						["Thorn", "70W", "Corstar single crystal sapphire arc tube", "~1983"]
					],
					pictures: [
						"/t D SHP GE LU100BD.jpg",
						"/t Westinghouse Corstar 400.jpg",
						"/t D SHP Thorn SONT400 Corstar.jpg",
						"/t Thorn SON70 Corstar.jpg"
					]
				},
				{
					subhead: "瞬时再启动双弧设计",
					intros: [["Sylvania", "400W", "SHP-Standby twin arc tubes for hot restrike", "1989"]],
					pictures: ["/t Sylvania SON2T400.jpg"]
				},
				{
					subhead: "自启动及汞灯改装设计",
					intros: [
						["OsramGEC", "310W", "Solarcolour Plug-In Mercury lamp retrofit", "1969"],
						["OsramGEC", "120W", "SON-I with internal snap-switch starter", "1976"],
						["Sylvania", "360W", "Unalux Penning-Start Mercury lamp retrofit", "1982"],
						["GE", "215W", "E-Z Lux Penning-Start Mercury lamp retrofit", "1988"],
						["Philips", "70W", "SON/I with internal glowbottle starter", "1980"],
						["GE", "70W", "LU70/90/D/I/27 internal electronic ignitor", "1990"],
						["Iwasaki", "150W", "Ignitron NHT150-I with internal FEC ignitor", "1997"],
						["Iwasaki", "150W", "SunluxUltra NH150CE Unsaturated Vapour", "2000"],
						["Sylvania", "69/108W", "SPX EcoArc Unsaturated Mercury Retrofit", "2009"]
					],
					pictures: [
						"/t D SHP GEC SONI310.jpg",
						"/t GEC SONI120.jpg",
						"/t D HPS Sylvania ULX360.jpg",
						"/t D SHP GE LUH215.jpg",
						"/t D SHP Philips SON70I.jpg",
						"/t D SHP GE LU70-90-D-I-27.jpg",
						"/t Iwasaki Ignitron T150.jpg",
						"/t Iwasaki NH150CE.jpg",
						"/t D SHP Sylvania SPX69-108.jpg"
					]
				},
				{
					subhead: "增强效率设计",
					intros: [
						["GE", "250W", "LU250/BD/S with Superior Performance", "1977"],
						["OsramGEC", "310W", "Solarcolour Plus early high efficacy lamp", "1987"],
						["GE-Thorn", "70W", "SON XL-T with Cermet arc tube seals", "1991"],
						["GE-Thorn", "400W", "SON XL-T with sintered moly antenna on tube", "1991"],
						["Sylvania", "100W", "SHP-MF Mercury-Free high pressure sodium", "1996"],
						["GE", "70W", "Lucalox XO with monolithic arc tube", "2008"]
					],
					pictures: [
						"/t D SHP GE LU250-BD-S.jpg",
						"/t D SHP GEC SONPT310.jpg",
						"/t D SHP Thorn SONXLT70 Cermet.jpg",
						"/t Thorn SONXL400.jpg",
						"/t Sylvania SHP-MF100.jpg",
						"/t D SHP GE LU70XO.jpg"
					]
				},
				{
					subhead: "豪华色彩",
					intros: [
						["Westinghouse", "250W", "Ceramalux-4 first deluxe HPS C250S50/DX4", "1982"],
						["OsramGEC", "400W", "Solarcolour SONDL-T Deluxe Colour", "1985"],
						["Thorn", "400W", "SONDL-T Deluxe Colour", "1988"],
						["Philips", "250W", "SON-T Comfort Deluxe Colour", "1989"],
						["GE", "400W", "Lucalox LU400/DX/40 Deluxe Colour", "1998"],
						["Thorn", "400W", "SON-Deluxe with dichroic filter sleeve", "~1983"]
					],
					pictures: [
						"/t D SHP Westinghouse C250S50DX4.jpg",
						"/t D SHP GEC SONDLT400.jpg",
						"/t D SHP Thorn SONDLT400.jpg",
						"/t D SHP Philips SONT250 Comfort.jpg",
						"/t D SHP GE LU400DX.jpg",
						"/t Thorn SONDL400 IR.jpg"
					]
				},
				{
					subhead: "白光",
					intros: [
						["Matsushita", "50W", "K-HICA-Light White with elliptical arc tube", "~1985"],
						["Iwasaki", "50W", "NHT50 SDX White SON High Colour Rendering", "~1985"],
						["Philips", "50W", "SDW-T White SON with high CRI", "1991"],
						["Philips", "50W", "SDW-R White SON Blown Reflector", "Early 1980s"],
						["Philips", "22W", "SDW-AR White SON Crown Silver Replica", "1986 + 2018"],
						["GE", "95W", "White Lucalox for Pulsed Operation", "1990"],
						["Philips", "150W", "SON-T Deco for City Beatification projects", "1995"],
						["Philips", "100W", "SDW-TG Reduced size Mini WhiteSON", "2002"],
						["Osram", "80W", "ColorStar DSX-T with Variable Colour Output", "1998"]
					],
					pictures: [
						"/t National SON50.jpg",
						"/t Iwasaki NHT50SDX.jpg",
						"/t Philips SDWT50.jpg",
						"/t D SHP Philips SDWR50.jpg",
						"/t D SHP Philips SDW-AR22.jpg",
						"/t D SHP GE LU95.jpg",
						"/t Philips SONTDeco150.jpg",
						"/t Philips SDWTG100.jpg",
						"/t HID HPS Osram DSX-T.jpg"
					]
				},
				{
					subhead: "反射形状",
					intros: [
						["Westinghouse", "70W", "Ceramalux C70S62/PAR Dichroic for Coal Mines", "1970s"],
						["Osram", "310/360W", "SON-R Mercury-Retrofit high pressure sodium", "1998"],
						["Thorn", "70W", "SON-R Reflector style high pressure sodium", "1982"],
						["Reflux", "250W", "Reflux lamp with special side reflector", "2003"]
					],
					pictures: [
						"/t D SHP Westinghouse C70S62PAR.jpg",
						"/t D SHP Osram SONR310.jpg",
						"/t D SHP Thorn SONR70.jpg",
						"/t Reflux250.jpg"
					]
				},
				{
					subhead: "线性形状",
					intros: [
						["Thorn", "250W", "SON-TD Quartzray Gas-filled Linear style", "1981"],
						["Thorn", "400W", "SON-TD Quartzray Gas-filled Linear style", "1987"],
						["Thorn", "1000W", "SON-TD Quartzray Gas-filled Linear style", "~1990"],
						["GEC", "250W", "SON-L SolarStream Gas-filled Linear style", "1996"],
						["Osram", "400W", "NAV-TS Vialox Standard Gas-filled Linear style", "1989"],
						["Osram", "150W", "SON-TS Super double ended design", "2000"],
						["COBR", "400W", "WLS-TC Double ended quartz prototype", "~2000"],
						["Philips", "1000W", "Master GreenPower Horticultural Linear", "2005"]
					],
					pictures: [
						"/t D SHP Thorn SONTD250.jpg",
						"/t Thorn SONTD400.jpg",
						"/t D SHP Thorn SONTD1000.jpg",
						"/t%20Osram%20SONL250.jpg",
						"/t Osram NAVTS400.jpg",
						"/t Osram SONTS150.jpg",
						"/t D SHP COBR WLSTC400.jpg",
						"/t Philips SONTD Greenpower 1000.jpg"
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
