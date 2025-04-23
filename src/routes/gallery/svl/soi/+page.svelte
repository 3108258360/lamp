<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "SOI/H Integral Low Pressure Sodium",
					description: [
						"In 1955 the thermal insulation (and hence luminous efficacy) of the low pressure sodium lamp was improved through an Osram-GEC innovation, which dispensed with the separate dewar jacket and replaced it with a permanent one piece evacuated outer bulb. The vacuum directly surrounding the discharge tube minimised conducted and convected heat losses, and allowed the diameter of the discharge tube to be increased while maintaining the same wall temperature. Owing to the resulting reduction in electrical current density in the discharge the efficacy of this so-called 'Integral' lamp was increased.",
						"Further gains in efficacy were realised in 1956 via another GEC development, which involved adding a glass heat-reflection sleeve around each limb of the discharge tube. This provided additional thermal insuation while only absorbing about 3% light. It took a further four years for Philips to catch up, and its lamps are of slightly different design - employing one large single sleeve around both limbs of the discharge tube.",
						"Another advantage of the Integral design is that lumen maintenance during life is enhanced by keeping the inside of the lamp clean. When the earlier SO/H Dewar Jacket lamps cooled, dusty air from outside would be drawn in and the jackets rapidly became quite dirty. However the Integral design brought with it the problem of sodium migration. Vacuum does not proved a uniform temperature gradient along the tube length, which was previously ensured by the turbulent air movement within the dewar jacket. Thus sodium migrates (in fact it is distilled) from hot areas to cold, namely from the electrodes to the U-bend. It accumulates in the cold regions where it forms light-blocking mirrors, while leaving other parts of the tube devoid of sodium.",
						"Sodium migration was combated by adjusting the gas composition and pressure, such that when a region of the discharge became depleted of sodium the temperature at that point would fall and encourage sodium to migrate back. In addition it became customary to constrict the tube at the bend to marginally increase the temperature at this point. Philips lamps were less susceptible to this problem, owing to the use of sodium-retaining dimples formed into the discharge tube surface."
					]
				},
				{
					subhead: "Osram-GEC Lamps",
					intros: [
						["OsramGEC", "45W", "SOI/H with twin glass sleeved discharge tube", "1973"],
						["OsramGEC", "85W", "SOI/H with twin glass sleeved discharge tube", "1973"],
						["OsramGEC", "140W", "SOI/H with twin glass sleeved discharge tube", "1972"],
						["OsramGEC", "280W", "Double discharge tube high output lamp", "1958"],
						["OsramGEC", "140W", "Experimental design with holes in sleeves", "1958"]
					],
					pictures: [
						"/t D SLP GEC SOI45.jpg",
						"/t D SLP GEC SOI85.jpg",
						"/t D SLP GEC SOI140.jpg",
						"/t D SLP GEC SOI280.jpg",
						"/t D SLP GEC SOI140 Holes.jpg"
					]
				},
				{
					subhead: "Philips Lamps",
					intros: [
						["Philips", "85W", "First integral lamp, without glass sleeve", "1958"],
						["Philips", "45W", "SOI with single glass sleeved discharge tube", "1963"],
						["Philips", "60W", "SOI with single glass sleeved discharge tube", "1965"],
						["Philips", "85W", "SOI with single glass sleeved discharge tube", "1965"],
						["Philips", "140W", "SOI with single glass sleeved discharge tube", "1962"],
						["Philips", "200W", "SOI with single glass sleeved discharge tube", "1960"],
						["Philips", "45W", "SOI with orange darkroom safelight filter", "1966"]
					],
					pictures: [
						"/t Philips SOI85.jpg",
						"/t D SLP Philips SOI45.jpg",
						"/t D SLP Philips SOI60.jpg",
						"/t D SLP Philips SOI85.jpg",
						"/t D SLP Philips SOI140.jpg",
						"/t D SLP Philips SOI200.jpg",
						"/t D SLP Philips SOI45 Orange.jpg"
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
					title: "SOI/H 一体式低压钠灯",
					description: [
						"1955年，通过欧司朗-通用电气（Osram-GEC）的一项创新，低压钠灯的隔热性能（从而光效）得到了提升，该创新取消了独立的杜瓦夹层，取而代之的是一个永久性的整体真空外罩。放电管周围的真空最大限度地减少了传导和对流的热损失，并允许在保持相同壁温的情况下增加放电管的直径。由于放电中电流密度的相应降低，这种所谓的“一体式”灯的光效得到了提高。",
						"1956年，通过另一项通用电气（GEC）的开发，光效进一步提高，该开发在放电管的每一肢周围增加了一个玻璃反光袖。这在只吸收大约3%光线的情况下提供了额外的隔热。又过了四年，飞利浦才迎头赶上，其灯具设计略有不同——使用一个大的单袖包裹放电管的两肢。",
						"一体式设计的另一个优势是，通过保持灯具内部的清洁，提高了使用寿命期间的光通维持率。当早期的SO/H杜瓦夹层灯冷却时，外部的灰尘空气会被吸入，夹层很快就会变得很脏。然而，一体式设计带来了钠迁移的问题。真空无法沿管长提供均匀的温度梯度，而这一点此前是由杜瓦夹层内的湍流空气运动来保证的。因此，钠从较热区域迁移到较冷区域，即从电极迁移到U形弯处。它在较冷区域积累，形成阻挡光线的镜子，而管的其他部分则钠含量不足。",
						"通过调整气体组成和压力来对抗钠迁移，当放电的某个区域钠含量减少时，该点的温度会下降，从而促使钠迁移回来。此外，通常会在弯管处略微收缩管径，以提高该点的温度。由于在放电管表面形成了钠保持凹点，飞利浦灯具对这个问题的敏感性较低。"
					]
				},
				{
					subhead: "欧司朗灯",
					intros: [
						["OsramGEC", "45W", "SOI/H with twin glass sleeved discharge tube", "1973"],
						["OsramGEC", "85W", "SOI/H with twin glass sleeved discharge tube", "1973"],
						["OsramGEC", "140W", "SOI/H with twin glass sleeved discharge tube", "1972"],
						["OsramGEC", "280W", "Double discharge tube high output lamp", "1958"],
						["OsramGEC", "140W", "Experimental design with holes in sleeves", "1958"]
					],
					pictures: [
						"/t D SLP GEC SOI45.jpg",
						"/t D SLP GEC SOI85.jpg",
						"/t D SLP GEC SOI140.jpg",
						"/t D SLP GEC SOI280.jpg",
						"/t D SLP GEC SOI140 Holes.jpg"
					]
				},
				{
					subhead: "飞利浦灯",
					intros: [
						["Philips", "85W", "First integral lamp, without glass sleeve", "1958"],
						["Philips", "45W", "SOI with single glass sleeved discharge tube", "1963"],
						["Philips", "60W", "SOI with single glass sleeved discharge tube", "1965"],
						["Philips", "85W", "SOI with single glass sleeved discharge tube", "1965"],
						["Philips", "140W", "SOI with single glass sleeved discharge tube", "1962"],
						["Philips", "200W", "SOI with single glass sleeved discharge tube", "1960"],
						["Philips", "45W", "SOI with orange darkroom safelight filter", "1966"]
					],
					pictures: [
						"/t Philips SOI85.jpg",
						"/t D SLP Philips SOI45.jpg",
						"/t D SLP Philips SOI60.jpg",
						"/t D SLP Philips SOI85.jpg",
						"/t D SLP Philips SOI140.jpg",
						"/t D SLP Philips SOI200.jpg",
						"/t D SLP Philips SOI45 Orange.jpg"
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
