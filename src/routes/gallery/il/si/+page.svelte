<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent & Halogen - Special incandescent lamps",
					description: [
						"This page covers the broad range of special incandescent lamps. Some of these are technologically similar to the types featured eleswhere on this site, but have been modified in such as way as to make them more suitable for applications other than general illumination. In view of the great diversity of miniature lamps for special applications, such types are not included on this page and are featured separately."
					]
				},
				{
					subhead: "Infrared Lamps",
					intros: [
						["Robertson", "250W", "Carbon Radiator with anti-glare flame-tint", "~1940"],
						["Robertson", "250W", "Carbon Radiator with double ended design", "1947"],
						["Crompton", "200W", "Tricity Sunray Tungsten Radiator", "~1930"],
						["Ediswan", "200W", "'Thermalite' Compact Carbon Heater", "~1930"],
						["GEC", "65W", "Robertson Carbon Heater modern style", "1949"],
						["GE", "375W", "Industrial Infrared with Light Pearl Glass", "~1950"],
						["GE", "500W", "Industrial Infrared with Triangular Filament", "1974"],
						["Philips", "100W", "Infrared Incubator Mother Lamp", "1986"],
						["Sylvania", "100W", "Infrared Ruby Glass Reptile Nightlight", "2001"],
						["Kyokko", "40W", "Infrared Longwave Petcare Heater", "~2000"],
						["Thorn", "275W", "Hardglass Clear Infrared Reflector", "1982"],
						["GE", "250W", "Infrared Brooder lamp for animal husbandry", "1960's"],
						["GE", "250W", "Hardglass Ruby Infrared Reflector", "1949"],
						["Philips", "150W", "Infraphil 13373F/479 Ruby Therapeutic", "1961"],
						["Philips", "150W", "Infraphil 13379F/479 Ruby Therapeutic", "1973"],
						["Philips", "150W", "Infraphil R95E with CdS:Se Internal Film", "1990"],
						["Philips", "250W", "Infrared R125 with natural ruby glass", "2003"],
						["Narva", "500W", "Linear Double Ended Infrared", "1957"],
						["Philips", "500W", "Side Reflector Infrared IRG 13342F/01", "1959"],
						["GE", "500W", "Quartz Incandescent Linear 500T3/CL", "1963"],
						["Thorn EMI", "450W", "Quartz Halogen Side Reflector Cooker", "~1985"],
						["GE-Thorn", "1500W", "Quartz Halogen Ruby Jacket Spaceheater", "1992"],
						["GE-Thorn", "1500W", "Quartz Halogen Ruby Slim Spaceheater", "1992"],
						["Philips", "2000W", "Quartz Halogen HeLeN coated Spaceheater", "2002"],
						["Victory", "1000W", "Quartz Halogen Ruby Slim Spaceheater", "1999"]
					],
					pictures: [
						"/t IN SP IR Robertson 240-250T57FL-B22d.jpg",
						"/t IN SP IR Robertson 240-250T57CL-S22.jpg",
						"/t IN SP IR Tricity Sunray.jpg",
						"/t IN SP IR Ediswan 50-200G88CL-E27.jpg",
						"/t IN SP IR Robertson Carbon 245-65PS60CL-B22d.jpg",
						"/t IN SP IR GE 110-375G30IF-E26.jpg",
						"/t IN SP IR GE 115-500T40CL-G22.jpg",
						"/t IN SP IR Philips Moederlamp.jpg",
						"/t IN SP IR Sylvania Reptile Red 100W PS68.jpg",
						"/t IN SP IR Kyokko 100-40M75CL-E26.jpg",
						"/t IN SP IR Thorn 250-275R125CL-B22d.jpg",
						"/t IN SP IR GE 120-250PS30R-E26.jpg",
						"/t IN R 120-250R40IRR-E26 GE.jpg",
						"/t IN SP IR Philips 210-150R125IRR-B22d3 Infraphil.jpg",
						"/t IN SP IR Philips 240-150PAR38IRR-B22d3 Infraphil.jpg",
						"/t IN SP IR Philips 225-150R95IRR-E27 Infraphil.jpg",
						"/t IN SP IR Philips 230-250R125IRR-E27.jpg",
						"/t IN SP IR Narva 220-500TD50CL.jpg",
						"/t IN SP IR Philips IRG500.jpg",
						"/t IN SP IR GE 120-500T3QCL-Wires.jpg",
						"/t TH SP IR Thorn 240-450T10R-Wires.jpg",
						"/t TH SP IR Thorn 235-1500T24RUBY-SK15.jpg",
						"/t TH SP IR Thorn 225-1500T10RUBY-SK15.jpg",
						"/t TH SP IR Philips 235-2000T10HeLeN-SK15.jpg",
						"/t TH SP IR Victory 240-1000T10RUBY-SK15.jpg"
					]
				},
				{
					subhead: "Ultraviolet Lamps",
					intros: [
						["Westinghouse", "250W", "CX Mild Ultraviolet with UV-Transmitting Glass", "~1930"],
						["Osram", "500W", "Vitalux Ultraviolet with Blue-tinted Glass", "1940"],
						["Mazda", "150W", "Mazda-Vite Ultraviolet with Blue-tinted Glass", "1939"],
						["GE", "250W", "Purple-X Ultraviolet with Wood's Glass", "1953"],
						["Mazda", "60W", "Blacklight Miniature Military Auto/Aircraft", "1943"]
					],
					pictures: [
						"/t IN SP UV Westinghouse 120-250G30CX-E26.jpg",
						"/t IN SP UV Osram Vitalux.jpg",
						"/t IN SP UV Mazda 230-150P80UV-E27.jpg",
						"/t IN SP UV GE 120-250A21PX-E26.jpg",
						"/t IN SP UV Mazda 12-60P50BL-B15d.jpg"
					]
				},
				{
					subhead: "Miniature Lamps",
					intros: [["Sylvania", "0.1W", "Mite-T-Lite B8810 Microminiature", "1960 c."]],
					pictures: ["/t IN M Sylvania Microminiature B8810.jpg"]
				},
				{
					subhead: "Photographic Lamps",
					intros: [
						["GE-Mazda", "1000W", "Blue Glass 5200K Photoflood", "1945"],
						["Atlas", "1250W", "U-Tube Photoflood Halogen - 3400K P1/19", "1976"]
					],
					pictures: [
						"/t IN P GE-Mazda 1000PS52DB-120V.jpg",
						"/t TH SE P Q1250T8U-225 P1-19 Atlas.jpg"
					]
				},
				{
					subhead: "Projection Lamps",
					intros: [
						["GE-Edison", "200W", "Stereopticon with Spiral Carbon Filament", "~1895-1914"],
						["GE-Mazda", "400W", "400T20 Grid-Filament Projector Lamp", "c.1920"],
						["GE-Mazda", "108W", "108T10 Ribbon Filament Microscope Illuminator", "c.1925"],
						["GE-Edison", "500W", "500T12PF Pre-focussed Projector Lamp", "1932"],
						["Westinghouse", "1000W", "1000T20PF DRS A1/58 Bi-Plane Filament", "c.1940"],
						["Sylvania", "150W", "DLS World's first Dichroic Reflector Lamp", "1962"],
						["Sylvania", "150W", "DNF Dichroic Coated 8mm Projector Lamp", "1966"],
						["Atlas", "150W", "A1/24 DFN Tru-Flector with Conical Bulb Profile", "1967"],
						["Fujifilm", "150W", "Type SM Double Reflector Incandescent Projector", "~1970"]
					],
					pictures: [
						"/t IN C GE Stereopticon.jpg",
						"/t IN P GE-National-Mazda 400T20-115V-C13-E26.jpg",
						"/t IN P A1 GE-Mazda 108T10-6V-R6-E26.jpg",
						"/t IN P A1 GE 500T12PF.jpg",
						"/t IN P A1 Westinghouse 1000T20PF-C13D.jpg",
						"/t IN SP P Sylvania DLS.jpg",
						"/t IN P Sylvania DNF side.jpg",
						"/t IN P A1-24 Atlas.jpg",
						"/t IN P SM Fuji.jpg"
					]
				},
				{
					subhead: "Studio & Theatre Lamps",
					intros: [
						["GE", "750W", "Q750T12-CL 1st Gen. Theatre Halogen", "1968"],
						["GE", "750W", "Q750T20-4CL 1st Gen. Planar Filament", "1966"],
						["GE", "2000W", "Q2000T11-4CL CYX 2nd Gen. Planar Filament", "1973"],
						["Thorn", "1000W", "T/15 Theatre Planar Filament & Bulged envelope", "1974"],
						["GEC", "1¼/2½kW", "CP/57 Twin-Filament Glass Halogen Studio", "1977"],
						["GEC", "1¼/1¼kW", "CP/22 Twin-Filament Glass Halogen Flexi-Pin", "1986"],
						["Thorn", "2½/2½kW", "CP/30 Twin-Filament Quartz Halogen Studio", "1973"],
						["Thorn", "1000W", "CP/60 PAR64 Sealed Beam High Voltage", "1981"],
						["Siemens", "4000W", "EC102 Cruciform Filament Low Voltage", "1952"]
					],
					pictures: [
						"/t TH SE P Q750T12CL-120 GE.jpg",
						"/t TH SE P Q750T20-4CL GE.jpg",
						"/t TH SE P Q2000T11-4CL GE.jpg",
						"/t TH SE P Atlas T15.jpg",
						"/t TH SE P GEC CP57.jpg",
						"/t TH SE P GEC CP22.jpg",
						"/t TH SE P Thorn CP32.jpg",
						"/t TH RA Thorn PAR64 CP60.jpg"
					]
				},
				{
					subhead: "Lighthouse Lamps",
					intros: [
						["Siemens", "4000W", "EC102 Cruciform Filament Low Voltage", "1952"],
						["GEC", "3000W", "EC111 Triple Cylindrical Rapid Nigrescence", "1969"],
						["Thorn", "3000W", "EC111A Box Filament Rapid Nigrescence", "1986"],
						["Philips", "3000W", "6096S Three Phase with Lightning Conductors", "1968"],
						["Mazda", "1500W", "6073S Three Phase with Lightning Conductors", "~1970"],
						["Thorn", "1500W", "L/25 Cylinder Filament Pre-Focussed", "1985"],
						["Victory", "1000W", "L/11 Bunch Filament Pre-Focussed", "2001"],
						["GEC", "500W", "L/9 Bunch Filament Pre-Focussed", "1956"],
						["Victory", "250W", "L/5 Bunch Filament Pre-Focussed", "1999"],
						["GEC", "375W", "L/8 Triple Axial Planar Filament Pre-Focussed", "1972"],
						["GE", "250W", "250T14/1 American Bunch-Filament", "1971"],
						["GE", "1000W", "Q1000T20BP American Axial-Filament Halogen", "2006"],
						["Lumalux", "200W", "BSL/3H Quad-Filament Lighthouse Halogen", "1996"]
					],
					pictures: [
						"/t IN P L Siemens EC102.jpg",
						"/t IN P L GEC EC111.jpg",
						"/t IN P L Thorn EC111A.jpg",
						"/t IN P L Philips 6096S.jpg",
						"/t IN P L Mazda 1500W.jpg",
						"/t IN P L Thorn L25.jpg",
						"/t IN P L Victory L11.jpg",
						"/t IN P L GEC L9.jpg",
						"/t IN P L Victory L5.jpg",
						"/t IN P L GEC L8.jpg",
						"/t IN P L GE 250T14.jpg",
						"/t TH SE P GE Q1000T20BP.jpg",
						"/t TH SE P Lumalux BSL3H.jpg"
					]
				},
				{
					subhead: "Special Service Military Lamps",
					intros: [
						["Thorn", "3000W", "Rapid Nigrescence Masthead Signalling", "1975"],
						["GE", "1200W", "MS-25015-2 Airway Beacon Mogul Bi-Post", "1998"]
					],
					pictures: [
						"/t IN P Thorn Rapid Nigrescence Signal 3000W.jpg",
						"/t IN P L GE MS-25015-2.jpg"
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
					title: "特殊白炽灯和卤素灯",
					description: [
						"本页面涵盖了广泛的特殊白炽灯。其中一些在技术上与本网站其他地方介绍的类型相似，但经过修改，使其更适合除一般照明之外的应用。鉴于特殊应用的小型灯具种类繁多，此类灯具未包含在本页面中，而是单独介绍。"
					]
				},
				{
					subhead: "红外线灯",
					intros: [
						["Robertson", "250W", "Carbon Radiator with anti-glare flame-tint", "~1940"],
						["Robertson", "250W", "Carbon Radiator with double ended design", "1947"],
						["Crompton", "200W", "Tricity Sunray Tungsten Radiator", "~1930"],
						["Ediswan", "200W", "'Thermalite' Compact Carbon Heater", "~1930"],
						["GEC", "65W", "Robertson Carbon Heater modern style", "1949"],
						["GE", "375W", "Industrial Infrared with Light Pearl Glass", "~1950"],
						["GE", "500W", "Industrial Infrared with Triangular Filament", "1974"],
						["Philips", "100W", "Infrared Incubator Mother Lamp", "1986"],
						["Sylvania", "100W", "Infrared Ruby Glass Reptile Nightlight", "2001"],
						["Kyokko", "40W", "Infrared Longwave Petcare Heater", "~2000"],
						["Thorn", "275W", "Hardglass Clear Infrared Reflector", "1982"],
						["GE", "250W", "Infrared Brooder lamp for animal husbandry", "1960's"],
						["GE", "250W", "Hardglass Ruby Infrared Reflector", "1949"],
						["Philips", "150W", "Infraphil 13373F/479 Ruby Therapeutic", "1961"],
						["Philips", "150W", "Infraphil 13379F/479 Ruby Therapeutic", "1973"],
						["Philips", "150W", "Infraphil R95E with CdS:Se Internal Film", "1990"],
						["Philips", "250W", "Infrared R125 with natural ruby glass", "2003"],
						["Narva", "500W", "Linear Double Ended Infrared", "1957"],
						["Philips", "500W", "Side Reflector Infrared IRG 13342F/01", "1959"],
						["GE", "500W", "Quartz Incandescent Linear 500T3/CL", "1963"],
						["Thorn EMI", "450W", "Quartz Halogen Side Reflector Cooker", "~1985"],
						["GE-Thorn", "1500W", "Quartz Halogen Ruby Jacket Spaceheater", "1992"],
						["GE-Thorn", "1500W", "Quartz Halogen Ruby Slim Spaceheater", "1992"],
						["Philips", "2000W", "Quartz Halogen HeLeN coated Spaceheater", "2002"],
						["Victory", "1000W", "Quartz Halogen Ruby Slim Spaceheater", "1999"]
					],
					pictures: [
						"/t IN SP IR Robertson 240-250T57FL-B22d.jpg",
						"/t IN SP IR Robertson 240-250T57CL-S22.jpg",
						"/t IN SP IR Tricity Sunray.jpg",
						"/t IN SP IR Ediswan 50-200G88CL-E27.jpg",
						"/t IN SP IR Robertson Carbon 245-65PS60CL-B22d.jpg",
						"/t IN SP IR GE 110-375G30IF-E26.jpg",
						"/t IN SP IR GE 115-500T40CL-G22.jpg",
						"/t IN SP IR Philips Moederlamp.jpg",
						"/t IN SP IR Sylvania Reptile Red 100W PS68.jpg",
						"/t IN SP IR Kyokko 100-40M75CL-E26.jpg",
						"/t IN SP IR Thorn 250-275R125CL-B22d.jpg",
						"/t IN SP IR GE 120-250PS30R-E26.jpg",
						"/t IN R 120-250R40IRR-E26 GE.jpg",
						"/t IN SP IR Philips 210-150R125IRR-B22d3 Infraphil.jpg",
						"/t IN SP IR Philips 240-150PAR38IRR-B22d3 Infraphil.jpg",
						"/t IN SP IR Philips 225-150R95IRR-E27 Infraphil.jpg",
						"/t IN SP IR Philips 230-250R125IRR-E27.jpg",
						"/t IN SP IR Narva 220-500TD50CL.jpg",
						"/t IN SP IR Philips IRG500.jpg",
						"/t IN SP IR GE 120-500T3QCL-Wires.jpg",
						"/t TH SP IR Thorn 240-450T10R-Wires.jpg",
						"/t TH SP IR Thorn 235-1500T24RUBY-SK15.jpg",
						"/t TH SP IR Thorn 225-1500T10RUBY-SK15.jpg",
						"/t TH SP IR Philips 235-2000T10HeLeN-SK15.jpg",
						"/t TH SP IR Victory 240-1000T10RUBY-SK15.jpg"
					]
				},
				{
					subhead: "紫外线灯",
					intros: [
						["Westinghouse", "250W", "CX Mild Ultraviolet with UV-Transmitting Glass", "~1930"],
						["Osram", "500W", "Vitalux Ultraviolet with Blue-tinted Glass", "1940"],
						["Mazda", "150W", "Mazda-Vite Ultraviolet with Blue-tinted Glass", "1939"],
						["GE", "250W", "Purple-X Ultraviolet with Wood's Glass", "1953"],
						["Mazda", "60W", "Blacklight Miniature Military Auto/Aircraft", "1943"]
					],
					pictures: [
						"/t IN SP UV Westinghouse 120-250G30CX-E26.jpg",
						"/t IN SP UV Osram Vitalux.jpg",
						"/t IN SP UV Mazda 230-150P80UV-E27.jpg",
						"/t IN SP UV GE 120-250A21PX-E26.jpg",
						"/t IN SP UV Mazda 12-60P50BL-B15d.jpg"
					]
				},
				{
					subhead: "小型灯",
					intros: [["Sylvania", "0.1W", "Mite-T-Lite B8810 Microminiature", "1960 c."]],
					pictures: ["/t IN M Sylvania Microminiature B8810.jpg"]
				},
				{
					subhead: "摄影灯",
					intros: [
						["GE-Mazda", "1000W", "Blue Glass 5200K Photoflood", "1945"],
						["Atlas", "1250W", "U-Tube Photoflood Halogen - 3400K P1/19", "1976"]
					],
					pictures: [
						"/t IN P GE-Mazda 1000PS52DB-120V.jpg",
						"/t TH SE P Q1250T8U-225 P1-19 Atlas.jpg"
					]
				},
				{
					subhead: "投影灯",
					intros: [
						["GE-Edison", "200W", "Stereopticon with Spiral Carbon Filament", "~1895-1914"],
						["GE-Mazda", "400W", "400T20 Grid-Filament Projector Lamp", "c.1920"],
						["GE-Mazda", "108W", "108T10 Ribbon Filament Microscope Illuminator", "c.1925"],
						["GE-Edison", "500W", "500T12PF Pre-focussed Projector Lamp", "1932"],
						["Westinghouse", "1000W", "1000T20PF DRS A1/58 Bi-Plane Filament", "c.1940"],
						["Sylvania", "150W", "DLS World's first Dichroic Reflector Lamp", "1962"],
						["Sylvania", "150W", "DNF Dichroic Coated 8mm Projector Lamp", "1966"],
						["Atlas", "150W", "A1/24 DFN Tru-Flector with Conical Bulb Profile", "1967"],
						["Fujifilm", "150W", "Type SM Double Reflector Incandescent Projector", "~1970"]
					],
					pictures: [
						"/t IN C GE Stereopticon.jpg",
						"/t IN P GE-National-Mazda 400T20-115V-C13-E26.jpg",
						"/t IN P A1 GE-Mazda 108T10-6V-R6-E26.jpg",
						"/t IN P A1 GE 500T12PF.jpg",
						"/t IN P A1 Westinghouse 1000T20PF-C13D.jpg",
						"/t IN SP P Sylvania DLS.jpg",
						"/t IN P Sylvania DNF side.jpg",
						"/t IN P A1-24 Atlas.jpg",
						"/t IN P SM Fuji.jpg"
					]
				},
				{
					subhead: "工作室与剧院灯",
					intros: [
						["GE", "750W", "Q750T12-CL 1st Gen. Theatre Halogen", "1968"],
						["GE", "750W", "Q750T20-4CL 1st Gen. Planar Filament", "1966"],
						["GE", "2000W", "Q2000T11-4CL CYX 2nd Gen. Planar Filament", "1973"],
						["Thorn", "1000W", "T/15 Theatre Planar Filament & Bulged envelope", "1974"],
						["GEC", "1¼/2½kW", "CP/57 Twin-Filament Glass Halogen Studio", "1977"],
						["GEC", "1¼/1¼kW", "CP/22 Twin-Filament Glass Halogen Flexi-Pin", "1986"],
						["Thorn", "2½/2½kW", "CP/30 Twin-Filament Quartz Halogen Studio", "1973"],
						["Thorn", "1000W", "CP/60 PAR64 Sealed Beam High Voltage", "1981"],
						["Siemens", "4000W", "EC102 Cruciform Filament Low Voltage", "1952"]
					],
					pictures: [
						"/t TH SE P Q750T12CL-120 GE.jpg",
						"/t TH SE P Q750T20-4CL GE.jpg",
						"/t TH SE P Q2000T11-4CL GE.jpg",
						"/t TH SE P Atlas T15.jpg",
						"/t TH SE P GEC CP57.jpg",
						"/t TH SE P GEC CP22.jpg",
						"/t TH SE P Thorn CP32.jpg",
						"/t TH RA Thorn PAR64 CP60.jpg"
					]
				},
				{
					subhead: "灯塔灯",
					intros: [
						["Siemens", "4000W", "EC102 Cruciform Filament Low Voltage", "1952"],
						["GEC", "3000W", "EC111 Triple Cylindrical Rapid Nigrescence", "1969"],
						["Thorn", "3000W", "EC111A Box Filament Rapid Nigrescence", "1986"],
						["Philips", "3000W", "6096S Three Phase with Lightning Conductors", "1968"],
						["Mazda", "1500W", "6073S Three Phase with Lightning Conductors", "~1970"],
						["Thorn", "1500W", "L/25 Cylinder Filament Pre-Focussed", "1985"],
						["Victory", "1000W", "L/11 Bunch Filament Pre-Focussed", "2001"],
						["GEC", "500W", "L/9 Bunch Filament Pre-Focussed", "1956"],
						["Victory", "250W", "L/5 Bunch Filament Pre-Focussed", "1999"],
						["GEC", "375W", "L/8 Triple Axial Planar Filament Pre-Focussed", "1972"],
						["GE", "250W", "250T14/1 American Bunch-Filament", "1971"],
						["GE", "1000W", "Q1000T20BP American Axial-Filament Halogen", "2006"],
						["Lumalux", "200W", "BSL/3H Quad-Filament Lighthouse Halogen", "1996"]
					],
					pictures: [
						"/t IN P L Siemens EC102.jpg",
						"/t IN P L GEC EC111.jpg",
						"/t IN P L Thorn EC111A.jpg",
						"/t IN P L Philips 6096S.jpg",
						"/t IN P L Mazda 1500W.jpg",
						"/t IN P L Thorn L25.jpg",
						"/t IN P L Victory L11.jpg",
						"/t IN P L GEC L9.jpg",
						"/t IN P L Victory L5.jpg",
						"/t IN P L GEC L8.jpg",
						"/t IN P L GE 250T14.jpg",
						"/t TH SE P GE Q1000T20BP.jpg",
						"/t TH SE P Lumalux BSL3H.jpg"
					]
				},
				{
					subhead: "特殊用途军用灯",
					intros: [
						["Thorn", "3000W", "Rapid Nigrescence Masthead Signalling", "1975"],
						["GE", "1200W", "MS-25015-2 Airway Beacon Mogul Bi-Post", "1998"]
					],
					pictures: [
						"/t IN P Thorn Rapid Nigrescence Signal 3000W.jpg",
						"/t IN P L GE MS-25015-2.jpg"
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
