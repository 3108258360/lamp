<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Incandescent - Decorative Lamps",
					description: [
						"Since the beginnings of the electric lamp industry, manufacturers have striven to increase the value of their products by developing a diverse range of special bulb shapes, colours, coatings and textures. In many cases their primary purpose is not even to illuminate a space, but to function as a decorative object or to highlight architectural details. Owing to the fact that the primary feature of these products is their external appearance rather than the internal light-generating technology, lamps having different technical features such as filament materials or atmoshperes are not distinguished and have been grouped together."
					]
				},
				{
					subhead: "Light-Diffusing Finishes",
					intros: [
						["GE", "50W", "First Inside Frosted & first A-line shape lamp", "c.1925-35"],
						["GE", "100W", "'Q-Coat' with internal silica powder coating", "c.1950"],
						["GEC", "40W", "Osram Accent opal finish square shape", "1974"]
					],
					pictures: [
						"/t IN WC GE-Edison 120-50A21IF-E26.jpg",
						"/t IN WC GE 120-100A21QC-E26.jpg",
						"/t IN WC GEC 240-40T65OP-BC Accent.jpg"
					]
				},
				{
					subhead: "Natural Coloured Glass",
					intros: [
						["Ediswan", "16CP", "Fancy Lamps Series - Natural Coloured Glass", "~1890"],
						["Ediswan", "16CP", "Fancy Lamps Series - Opal Striped Glass", "~1890"],
						["Ediswan", "16CP", "Fancy Lamps Series - Iced Glass", "~1890"],
						["G & A", "16CP", "Fancy Lamps Series - Dimpled Brown Glass", "~1900"],
						["National", "200W", "Mazda Daylight Blue lamp of first design", "1919"]
					],
					pictures: [
						"/t IN C Ediswan Fancy Azure.jpg",
						"/t IN C Ediswan Fancy Opal Striped Green.jpg",
						"/t IN C Ediswan Fancy Iced Amber.jpg",
						"/t IN C GA Fancy Dimpled Brown.jpg",
						"/t IN WC D GE 105-200PS30DAY-E26.jpg"
					]
				},
				{
					subhead: "Decorative Bulb Shapes",
					intros: [
						["GE", "50W", "Decorative Enamelled Bowl 50-GA", "1958"],
						["GE", "75W", 'Decorative Enamelled "Celeste" Lamp', "~1965"]
					],
					pictures: ["/t IN WC D GE 50GA25IFP-E26.jpg", "/t IN WC D GE 75DC30IFP-E26.jpg"]
				},
				{
					subhead: "Linear Lamps",
					intros: [
						["Ediswan", "12CP", "Tubolite double ended carbon filament", "1901-1910"],
						["Ediswan", "30W", "Beautalite double ended tungsten filament", "~1910"],
						["GE", "60W", "Lumiline double ended with metal disc seals", "~1950"]
					],
					pictures: [
						"/t IN C D Ediswan Tubolite.jpg",
						"/t IN WC D Ediswan Beautalite.jpg",
						"/t IN WC D GE 60T8CL-Lumiline.jpg"
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
					title: "装饰白炽灯",
					description: [
						"自电灯行业诞生以来，制造商们一直致力于通过开发各种特殊的灯泡形状、颜色、涂层和纹理来提升产品的价值。在许多情况下，这些产品的首要目的甚至不是照亮空间，而是作为装饰物或突出建筑细节。由于这些产品的主要特征是其外观，而不是内部发光技术，因此具有不同技术特征的灯具，如灯丝材料或气氛，并未被区分，而是被归为一组。"
					]
				},
				{
					subhead: "漫射光涂层",
					intros: [
						["GE", "50W", "First Inside Frosted & first A-line shape lamp", "c.1925-35"],
						["GE", "100W", "'Q-Coat' with internal silica powder coating", "c.1950"],
						["GEC", "40W", "Osram Accent opal finish square shape", "1974"]
					],
					pictures: [
						"/t IN WC GE-Edison 120-50A21IF-E26.jpg",
						"/t IN WC GE 120-100A21QC-E26.jpg",
						"/t IN WC GEC 240-40T65OP-BC Accent.jpg"
					]
				},
				{
					subhead: "天然色玻璃",
					intros: [
						["Ediswan", "16CP", "Fancy Lamps Series - Natural Coloured Glass", "~1890"],
						["Ediswan", "16CP", "Fancy Lamps Series - Opal Striped Glass", "~1890"],
						["Ediswan", "16CP", "Fancy Lamps Series - Iced Glass", "~1890"],
						["G & A", "16CP", "Fancy Lamps Series - Dimpled Brown Glass", "~1900"],
						["National", "200W", "Mazda Daylight Blue lamp of first design", "1919"]
					],
					pictures: [
						"/t IN C Ediswan Fancy Azure.jpg",
						"/t IN C Ediswan Fancy Opal Striped Green.jpg",
						"/t IN C Ediswan Fancy Iced Amber.jpg",
						"/t IN C GA Fancy Dimpled Brown.jpg",
						"/t IN WC D GE 105-200PS30DAY-E26.jpg"
					]
				},
				{
					subhead: "装饰灯泡形状",
					intros: [
						["GE", "50W", "Decorative Enamelled Bowl 50-GA", "1958"],
						["GE", "75W", 'Decorative Enamelled "Celeste" Lamp', "~1965"]
					],
					pictures: ["/t IN WC D GE 50GA25IFP-E26.jpg", "/t IN WC D GE 75DC30IFP-E26.jpg"]
				},
				{
					subhead: "线性灯具",
					intros: [
						["Ediswan", "12CP", "Tubolite double ended carbon filament", "1901-1910"],
						["Ediswan", "30W", "Beautalite double ended tungsten filament", "~1910"],
						["GE", "60W", "Lumiline double ended with metal disc seals", "~1950"]
					],
					pictures: [
						"/t IN C D Ediswan Tubolite.jpg",
						"/t IN WC D Ediswan Beautalite.jpg",
						"/t IN WC D GE 60T8CL-Lumiline.jpg"
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
