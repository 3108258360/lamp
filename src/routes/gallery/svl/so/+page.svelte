<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "SO/H Detatchable Low Pressure Sodium",
					description: [
						"Developed by Philips in early 1932, the SO/H design was the first commercial sodium vapour lamp to become popular and enter mass production. The discharge tube is U-shaped and fabricated from 2-ply sodium-resistant glass, and to allow this to attain the necessary wall temperature of 260°C for maximum efficacy, it is operated inside a dewar vacuum jacket to provide thermal insulation. At end of life it was customary to replace only the inner tube, the same dewar being used up to about six times, before its vacuum would tend to go soft and no longer provide the necessary insulation.",
						"Although the SO/H lamp was technically superseded by the superior SOI/H 'Integral' design after 1955, it remained in production until about 1965 for replacement purposes. Illustrated here is a selection of SO/H lamps from a variety of manufacturers, exhibiting some of the different construction techniques employed.",
						"It is worth noting here that the rate at which the glasses used in some of these lamps cleans up argon gas can be rather high. In particular, if the lamp has not been lit for more than twenty years or so, the argon gas needed for starting may be adsorped quite rapidly after ignition. If the lamp is then turned off, the loss of this gas makes re-igniton extremely difficult. However if it is left burning for some five hours or so after its first start, this will be sufficient to re-release much of the argon and it will then be safe to turn off the lamp and know that it should strike again."
					]
				},
				{
					subhead: "Philips Lamps",
					intros: [
						["Philora", "60W", "SO/H lamp of Dutch 2nd generation", "1938"],
						["Philips", "45W", "SO/H lamp of British design", "1952"],
						["Philips", "140W", "SO/H lamp of British design", "1951"],
						["Philips", "60W", "SO/H replacement inner of British design", "1954"],
						["Philips", "45W", "SO/H replacement Bamboo discharge tube", "1957"],
						["Philips", "60W", "SO/H lamp with Bamboo discharge tube", "1958"],
						["Philips", "85W", "SO/H lamp with Bamboo discharge tube", "1955"],
						["Philips", "140W", "SO/H lamp with Dimpled discharge tube", "1958"]
					],
					pictures: [
						"/t D SLP Philora SO60.jpg",
						"/t D SLP Philips SO45 British.jpg",
						"/t D SLP Philips SO140 British.jpg",
						"/t D SLP Philips SO60 British inner.jpg",
						"/t D SLP Philips SO45 Bamboo inner.jpg",
						"/t D SLP Philips SO60 Bamboo.jpg",
						"/t D SLP Philips SO85 Bamboo.jpg",
						"/t D SLP Philips SO140 Dimpled.jpg"
					]
				},
				{
					subhead: "Osram-GEC Lamps",
					intros: [
						["OsramGEC", "140W", "SO/H lamp of early production style", "1949"],
						["OsramGEC", "45W", "SO/H discharge tube of last production style", "1965"]
					],
					pictures: ["/t D SLP GEC SO140.jpg", "/t D SLP GEC SO45 inner.jpg"]
				},
				{
					subhead: "BTH-Mazda and AEI-Mazda Lamps",
					intros: [
						["Mazda", "60W", "SO/H lamp with hard glass discharge tube", "1950"],
						["Mazda", "140W", "SO/H lamp with hard glass discharge tube", "1953"],
						["Mazda", "85W", "SO/H discharge tube of hard glass design", "1955"],
						["Mazda", "60W", "SO/H discharge tube of soft glass design", "1965"]
					],
					pictures: [
						"/t D SLP Mazda SO60 Hard.jpg",
						"/t D SLP Mazda SO140 Hard.jpg",
						"/t D SLP Mazda SO85 Hard inner.jpg",
						"/t D SLP Mazda SO60 Soft inner.jpg"
					]
				},
				{
					subhead: "Soviet Lamps",
					intros: [["MELZ", "140W", "DNAO-140 Soviet Style low pressure sodium", "1966"]],
					pictures: ["/t D SLP MELZ DNaO140.jpg"]
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
					title: "SO/H 可拆卸低压钠灯",
					description: [
						"由飞利浦于1932年初开发，SO/H设计是第一款广受欢迎并进入大规模生产的商用钠蒸气灯。放电管呈U形，由双层耐钠玻璃制成，为了使其达到最大效率所需的260°C壁温，它在杜瓦真空夹层内运行以提供隔热。在使用寿命结束时，通常只更换内管，同一个杜瓦夹层可以使用大约六次，直到其真空度变弱，不再提供必要的隔热。",
						"尽管SO/H灯在技术上于1955年后被更优越的SOI/H“一体式”设计所取代，但为了更换用途，它一直生产到大约1965年。这里展示了一些不同制造商生产的SO/H灯，展示了所采用的不同制造技术。",
						"值得一提的是，这些灯中使用的某些玻璃清除氩气的速率相当高。特别是如果灯已经二十多年没有点亮，启动所需的氩气在点火后可能会被迅速吸附。如果此时关闭灯，这种气体的损失会使重新点燃变得极其困难。然而，如果让它在首次启动后继续燃烧大约五个小时，这将足以重新释放大部分氩气，然后就可以安全地关闭灯，并且知道它应该能够再次启动。"
					]
				},
				{
					subhead: "飞利浦灯",
					intros: [
						["Philora", "60W", "SO/H lamp of Dutch 2nd generation", "1938"],
						["Philips", "45W", "SO/H lamp of British design", "1952"],
						["Philips", "140W", "SO/H lamp of British design", "1951"],
						["Philips", "60W", "SO/H replacement inner of British design", "1954"],
						["Philips", "45W", "SO/H replacement Bamboo discharge tube", "1957"],
						["Philips", "60W", "SO/H lamp with Bamboo discharge tube", "1958"],
						["Philips", "85W", "SO/H lamp with Bamboo discharge tube", "1955"],
						["Philips", "140W", "SO/H lamp with Dimpled discharge tube", "1958"]
					],
					pictures: [
						"/t D SLP Philora SO60.jpg",
						"/t D SLP Philips SO45 British.jpg",
						"/t D SLP Philips SO140 British.jpg",
						"/t D SLP Philips SO60 British inner.jpg",
						"/t D SLP Philips SO45 Bamboo inner.jpg",
						"/t D SLP Philips SO60 Bamboo.jpg",
						"/t D SLP Philips SO85 Bamboo.jpg",
						"/t D SLP Philips SO140 Dimpled.jpg"
					]
				},
				{
					subhead: "欧司朗灯",
					intros: [
						["OsramGEC", "140W", "SO/H lamp of early production style", "1949"],
						["OsramGEC", "45W", "SO/H discharge tube of last production style", "1965"]
					],
					pictures: ["/t D SLP GEC SO140.jpg", "/t D SLP GEC SO45 inner.jpg"]
				},
				{
					subhead: "马自达灯",
					intros: [
						["Mazda", "60W", "SO/H lamp with hard glass discharge tube", "1950"],
						["Mazda", "140W", "SO/H lamp with hard glass discharge tube", "1953"],
						["Mazda", "85W", "SO/H discharge tube of hard glass design", "1955"],
						["Mazda", "60W", "SO/H discharge tube of soft glass design", "1965"]
					],
					pictures: [
						"/t D SLP Mazda SO60 Hard.jpg",
						"/t D SLP Mazda SO140 Hard.jpg",
						"/t D SLP Mazda SO85 Hard inner.jpg",
						"/t D SLP Mazda SO60 Soft inner.jpg"
					]
				},
				{
					subhead: "苏联灯",
					intros: [["MELZ", "140W", "DNAO-140 Soviet Style low pressure sodium", "1966"]],
					pictures: ["/t D SLP MELZ DNaO140.jpg"]
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
