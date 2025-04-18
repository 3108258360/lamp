<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Linear Fluorescent Lamps",
					description: [
						"The Linear Fluorescent category represents the original and most basic form of fluorescent lamp. While the long, slender proportions of this light source makes them ideal for many applications, it can be a hindrance in others. Some two decades after their commercialisation and the refinement of the basic range, efforts were diverted into reducing the size of the light source. This resulted first in the range of Non-Linear Fluorescent Lamps, and later during the 1980s the extention to still more advanced Compact Fluorescent Lamps.",
						"All of the lamps features on this page belong to the original Linear category, and despite the advantages of the more modern versions, the original linear fluorescent lamp still accounts for a greater quantity of artificial light produced on this planet than any other light source. Owing to its high efficacy and supremely low cost, this lamp type will most likely be one of the last to be seriously challenged by LED technology."
					]
				},
				{
					subhead: "Silicate Lamps",
					intros: [
						["GE-Mazda", "14W", "F14T12-WEarly American lamp", "1945"],
						["Westinghouse", "20W", "F15T8-WEarly American lamp", "1944"],
						["BTH-Mazda", "80W", "F80T12-WW BayonetFirst British lamp", "1945"],
						["GE", "85W", "F85T10-IW Type RF Rectified Fluorescent", "1959"]
					],
					pictures: [
						"/t D FL Silicate Ar GE F14T12-W.jpg",
						"/t D FL Silicate Ar Westinghouse F15T8-W.jpg",
						"/t D FL Silicate Ar Mazda F80T12-WW BC.jpg",
						"/t D FL GE RF85.jpg"
					]
				},
				{
					subhead: "Halophosphate Lamps",
					intros: [
						["BTH-Mazda", "80W", "Early halophosphate lamp of British design", "1949"],
						["Philips", "80W", "MCFE 80w/33 with Bayonet Caps", "1969"],
						["Osram-GEC", "80W", "Last Production with Bayonet Caps", "1990"],
						["Sylvania", "15W", "American halophosphor with bakelite caps", "1950"]
					],
					pictures: [
						"/t D FL Halo Ar Mazda F80T12-D BC.jpg",
						"/t D FL Halo Ar Philips F80T12-CW BC.jpg",
						"/t D FL Halo Ar Osram F80T12-W BC.jpg",
						"/t D FL Halo Ar Sylvania F15T12-W.jpg"
					]
				},
				{
					subhead: "Halophosphate Deluxe Lamps",
					intros: [["Osram-GEC", "80W", "Deluxe Warm White with Bayonet Caps", "1956"]],
					pictures: ["/t D FL HaloDX Ar GEC F80T12-WWX BC.jpg"]
				},
				{
					subhead: "Lamps with Ignition Aids",
					intros: [["Mazda", "20W", "MCFA Linear Fluorescent with Instant Start Stripe", "1962"]],
					pictures: ["/t Mazda MCFE20 stripe.jpg"]
				},
				{
					subhead: "High Output Lamps",
					intros: [
						["GE", "215W", "PowerGroove Very High Output F96PG17-CW", "1987"],
						["Sylvania", "110W", "Powertube Very High Output F48T12-VHO", "1963"]
					],
					pictures: ["/t D FL Halo Ar GE F96PG17-CW.jpg", "/t D FL Sylvania F48T12-CW-VHO.jpg"]
				},
				{
					subhead: "Energy-Saving Lamps",
					intros: [["GE", "82W", "Krypton Watt-Miser T17 F90T17-CW-WM", "1995"]],
					pictures: ["/t D FL Halo Kr GE F90T17-CW-WM.jpg"]
				},
				{
					subhead: "Reflector Lampss",
					intros: [["Philips", "8W", "TL Mini Aperture with clear stripe along lamp", "2000"]],
					pictures: ["/t Philips Aperture.jpg"]
				},
				{
					subhead: "Coloured Lamps",
					intros: [
						["GE-Mazda", "15W", "Early Red with cadmium borate phosphor + dye", "1941"],
						["GE-Mazda", "15W", "Early Blue with calcium tungstate phosphor", "1941"]
					],
					pictures: ["/t D FL Coloured GE F15T8-Red.jpg", "/t D FL Coloured GE F15T8-Blue.jpg"]
				},
				{
					subhead: "Ultra-Violet Lamps",
					intros: [
						["GE-Mazda", "4W", "Miniature Flat Aircraft Cockpit Lamp", "1942"],
						["Philips", "20W", "Woods Glass Blacklight Blue", "1969"]
					],
					pictures: ["/t D FL UV GE F4O5-Blue.jpg", "/t D FL UV Philips TL20W-08.jpg"]
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
					title: "线性荧光灯",
					description: [
						"线性荧光灯类别代表了荧光灯最初和最基本的形式。虽然这种光源的长而细的形状使其适用于许多应用，但在其他一些情况下可能会成为阻碍。在它们商业化和基本系列完善后的二十多年里，人们开始努力缩小光源的尺寸。这首先导致了非线性荧光灯系列的出现，后来在20世纪80年代又扩展到了更先进的紧凑型荧光灯。",
						"本页面上介绍的所有灯具都属于最初的线性类别，尽管更现代版本具有优势，但最初的线性荧光灯仍然是地球上产生人工光最多的光源。由于其高效率和极低的成本，这种灯具类型很可能是最后受到LED技术真正挑战的灯具之一。"
					]
				},
				{
					subhead: "硅酸盐灯具",
					intros: [
						["GE-Mazda", "14W", "F14T12-WEarly American lamp", "1945"],
						["Westinghouse", "20W", "F15T8-WEarly American lamp", "1944"],
						["BTH-Mazda", "80W", "F80T12-WW BayonetFirst British lamp", "1945"],
						["GE", "85W", "F85T10-IW Type RF Rectified Fluorescent", "1959"]
					],
					pictures: [
						"/t D FL Silicate Ar GE F14T12-W.jpg",
						"/t D FL Silicate Ar Westinghouse F15T8-W.jpg",
						"/t D FL Silicate Ar Mazda F80T12-WW BC.jpg",
						"/t D FL GE RF85.jpg"
					]
				},
				{
					subhead: "卤磷酸盐灯具",
					intros: [
						["BTH-Mazda", "80W", "Early halophosphate lamp of British design", "1949"],
						["Philips", "80W", "MCFE 80w/33 with Bayonet Caps", "1969"],
						["Osram-GEC", "80W", "Last Production with Bayonet Caps", "1990"],
						["Sylvania", "15W", "American halophosphor with bakelite caps", "1950"]
					],
					pictures: [
						"/t D FL Halo Ar Mazda F80T12-D BC.jpg",
						"/t D FL Halo Ar Philips F80T12-CW BC.jpg",
						"/t D FL Halo Ar Osram F80T12-W BC.jpg",
						"/t D FL Halo Ar Sylvania F15T12-W.jpg"
					]
				},
				{
					subhead: "卤磷酸盐豪华灯具",
					intros: [["Osram-GEC", "80W", "Deluxe Warm White with Bayonet Caps", "1956"]],
					pictures: ["/t D FL HaloDX Ar GEC F80T12-WWX BC.jpg"]
				},
				{
					subhead: "带点火辅助装置的灯具",
					intros: [["Mazda", "20W", "MCFA Linear Fluorescent with Instant Start Stripe", "1962"]],
					pictures: ["/t Mazda MCFE20 stripe.jpg"]
				},
				{
					subhead: "高输出灯具",
					intros: [
						["GE", "215W", "PowerGroove Very High Output F96PG17-CW", "1987"],
						["Sylvania", "110W", "Powertube Very High Output F48T12-VHO", "1963"]
					],
					pictures: ["/t D FL Halo Ar GE F96PG17-CW.jpg", "/t D FL Sylvania F48T12-CW-VHO.jpg"]
				},
				{
					subhead: "节能灯具",
					intros: [["GE", "82W", "Krypton Watt-Miser T17 F90T17-CW-WM", "1995"]],
					pictures: ["/t D FL Halo Kr GE F90T17-CW-WM.jpg"]
				},
				{
					subhead: "反光灯具",
					intros: [["Philips", "8W", "TL Mini Aperture with clear stripe along lamp", "2000"]],
					pictures: ["/t Philips Aperture.jpg"]
				},
				{
					subhead: "彩色灯具",
					intros: [
						["GE-Mazda", "15W", "Early Red with cadmium borate phosphor + dye", "1941"],
						["GE-Mazda", "15W", "Early Blue with calcium tungstate phosphor", "1941"]
					],
					pictures: ["/t D FL Coloured GE F15T8-Red.jpg", "/t D FL Coloured GE F15T8-Blue.jpg"]
				},
				{
					subhead: "紫外线灯具",
					intros: [
						["GE-Mazda", "4W", "Miniature Flat Aircraft Cockpit Lamp", "1942"],
						["Philips", "20W", "Woods Glass Blacklight Blue", "1969"]
					],
					pictures: ["/t D FL UV GE F4O5-Blue.jpg", "/t D FL UV Philips TL20W-08.jpg"]
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
