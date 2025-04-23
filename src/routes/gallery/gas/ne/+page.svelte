<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Neon Discharge Lamps",
					description: [
						`The first neon discharge lamp was invented by the French engineer and scientist Georges Claude, who first applied an electric current through a neon-filled glass tube around 1902. On December 11th 1910 he demonstrated his brilliantly glowing luminous tubes to the public in Paris. However it was not until 1923 that the business potential of the neon lamp was realised, when his company, Claude Neon, supplied two signs to an American car dealership with the glass tube being bent to spell out the name of the firm "Packard". Those signs sold for a phenomenal $24,000, and kicked off the modern neon sign industry. Claude eventually became part of Sylvania Electric Products, and indeed his name lives on in France today through Sylvania's popular Claude brand name for its lighting products sold in that country. Outside of the neon sign industry, the linear neon lamp is manufactured today only by GE Lighting UK, in the form of the Airfield Hazard lamp shown below.`,
						"A second family of neon lamp was the negative glow type, invented by Daniel MacFarlan Moore of General Electric USA. He discovered that a glow will envelop the cathode electrode of a lamp evacuated to a suitably low pressure and filled with one of the inert gases. By operating the lamp on alternating current, the polarity is reversed so rapidly that both electrodes appear to glow, and a useful miniature indicator lamp was developed."
					]
				},
				{
					subhead: "Positive Column Discharge",
					intros: [
						["GEC", "400W", "NE/H Linear Neon Floodlighting Lamp", "1975"],
						["Thorn", "160W", "NE/H Linear Neon Airfield Hazard Warning", "1990"]
					],
					pictures: ["/t GEC NE400.jpg", "/t Thorn Linear Neon 160W.jpg"]
				},
				{
					subhead: "Negative Glow Discharge",
					intros: [
						["GE", "0.25W", "NE-45 neon indicator with internal resistance", "~1960"],
						["GE", "3W", "NE-42 high power neon indicator lamp", "~1970"],
						["Ediswan", "2W", "Neon Pilot lamp with internal resistance", "~1945"],
						["Mazda", "0.5W", "Neon Indicator lamp with internal resistance", "1966"],
						["Mazda", "0.5W", "Neon Indicator lamp for external resistance", "1950"],
						["Osram", "0.1W", "Miniature neon indicator with lens end", "~1985"],
						["Osglim", "5W", "Beehive neon spiral with internal ballast resistor", "1945"],
						["Osglim", "5W", "Beehive neon with Letter electrode for signs", "1935"],
						["Atlas", "5W", "Coronation of Queen Elizabeth II", "1952"],
						["Sylvania", "", "Strobotron neon stroboscope lamp", "~1950"]
					],
					pictures: [
						"/t GE NE45.jpg",
						"/t GE NE42.jpg",
						"/t Ediswan Neon Pilot.jpg",
						"/t Mazda Pygmy Neon Int.jpg",
						"/t Mazda Pygmy Neon Ext.jpg",
						"/t Osram MES Neon.jpg",
						"/t Osglim Beehive Neon.jpg",
						"/t Osglim Letter N.jpg",
						"/t Atlas Coronation Lamp glowing.jpg",
						"/t Sylvania Strobotron.jpg"
					]
				},
				{
					subhead: "Miscellaneous Devices",
					intros: [["Sylvania", "", "Strobotron neon stroboscope lamp", "~1950"]],
					pictures: ["/t Sylvania Strobotron.jpg"]
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
					title: "氖放电灯",
					description: [
						"第一盏氖放电灯是由法国工程师和科学家乔治·克劳德发明的，他在1902年左右首次将电流通过充满氖气的玻璃管。1910年12月11日，他在巴黎向公众展示了他那光芒四射的发光管。然而，直到1923年，氖灯的商业潜力才被意识到，当时他的公司克劳德霓虹灯为一家美国汽车经销商提供了两个标志，玻璃管被弯曲成拼写出“帕卡德”公司名称的形状。这些标志以惊人的24,000美元售出，开启了现代霓虹灯行业。克劳德最终成为西凡尼亚电气产品的组成部分，事实上，他的名字今天仍然通过西凡尼亚在法国销售的照明产品中流行的克劳德品牌而延续下来。在霓虹灯行业之外，线性氖灯如今只有英国的通用电气照明公司生产，形式如下图所示的机场障碍灯。",
						"第二种氖灯是负辉光型，由美国通用电气公司的丹尼尔·麦克法兰·摩尔发明。他发现，在将灯抽至适当低压并充入惰性气体后，灯的阴极电极周围会出现辉光。通过在交流电上运行灯，极性变化如此之快，以至于两个电极似乎都在发光，从而开发出了一种有用的微型指示灯。"
					]
				},
				{
					subhead: "正柱放电",
					intros: [
						["GEC", "400W", "NE/H Linear Neon Floodlighting Lamp", "1975"],
						["Thorn", "160W", "NE/H Linear Neon Airfield Hazard Warning", "1990"]
					],
					pictures: ["/t GEC NE400.jpg", "/t Thorn Linear Neon 160W.jpg"]
				},
				{
					subhead: "负辉光放电",
					intros: [
						["GE", "0.25W", "NE-45 neon indicator with internal resistance", "~1960"],
						["GE", "3W", "NE-42 high power neon indicator lamp", "~1970"],
						["Ediswan", "2W", "Neon Pilot lamp with internal resistance", "~1945"],
						["Mazda", "0.5W", "Neon Indicator lamp with internal resistance", "1966"],
						["Mazda", "0.5W", "Neon Indicator lamp for external resistance", "1950"],
						["Osram", "0.1W", "Miniature neon indicator with lens end", "~1985"],
						["Osglim", "5W", "Beehive neon spiral with internal ballast resistor", "1945"],
						["Osglim", "5W", "Beehive neon with Letter electrode for signs", "1935"],
						["Atlas", "5W", "Coronation of Queen Elizabeth II", "1952"],
						["Sylvania", "", "Strobotron neon stroboscope lamp", "~1950"]
					],
					pictures: [
						"/t GE NE45.jpg",
						"/t GE NE42.jpg",
						"/t Ediswan Neon Pilot.jpg",
						"/t Mazda Pygmy Neon Int.jpg",
						"/t Mazda Pygmy Neon Ext.jpg",
						"/t Osram MES Neon.jpg",
						"/t Osglim Beehive Neon.jpg",
						"/t Osglim Letter N.jpg",
						"/t Atlas Coronation Lamp glowing.jpg",
						"/t Sylvania Strobotron.jpg"
					]
				},
				{
					subhead: "其他装置",
					intros: [["Sylvania", "", "Strobotron neon stroboscope lamp", "~1950"]],
					pictures: ["/t Sylvania Strobotron.jpg"]
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
