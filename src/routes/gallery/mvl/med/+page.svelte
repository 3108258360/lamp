<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Medium Pressure Mercury Vapour",
					description: [
						"Medium pressure mercury lamps are classified as the MA type. They operate at a vapour pressure of about one atmosphere, the discharge dissipates between 10 and 100 watts per centimetre of arc length, and their arc tubes are made of a special thermally-resistant aluminosilicate hard glass.",
						"This was the first successful mercury lamp for general lighting applications. The technology was developed in 1931 by Osram-GEC of England, by combining its expertise in glassmaking with a fundamental new electrode design conceived by Osram in Germany. The concept was introduced in 1932 and proved tremendously successful. By 1933 the lamp technology had been licensed to the European manufacturers, in 1934 to the Americans, and was soon adopted worldwide.",
						"The first lamp was a 400W rating limited to vertical use. Later achievements permitted horizontal and then universal operation, and other power ratings were developed. However, the lower power lamps of 150W and 90W were not commercially viable, due to a rapid decrease in efficacy as lamp power is reduced. This problem was not solved until the developmennt of the MB High Pressure lamps. Improved variants of the MA lamps were made with a fluorescent bulb and in a self-ballasted design. Detailed information on the development and fundamentals of medium pressure mercury lamps can be found at the MA Technical Section."
					]
				},
				{
					subhead: "British Lamps",
					intros: [
						["Osira", "150W", "Osira MA/V low wattage lamp", "1936-37"],
						["Mazda", "400W", "Mercra MA/V early British design", "1944"],
						["Philips", "250W", "Philora MA/V early British design", "1945"],
						["Mazda", "250W", "MA/U improved universal burning design", "1955"],
						["Crompton", "250W", "MA/V with air-filled outer bulb", "1959"],
						["Osram", "400W", "MA/V of late design for vertical use", "1963"],
						["Mazda", "1000W", "MA/H horizontal floodlighting", "1952"]
					],
					pictures: [
						"/t D MA Osira MAV150.jpg",
						"/t Mazda MAV400.jpg",
						"/t Philips MAV250.jpg",
						"/t Mazda MAU250.jpg",
						"/t Crompton MAV250.jpg",
						"/t Osram MAV400.jpg",
						"/t D MA Mazda MAH1000.jpg"
					]
				},
				{
					subhead: "European Lamps",
					intros: [
						["Osram", "265W", "HgH 1000 of early German construction", "1957"],
						["Osram", "450W", "HgH 2000 of later German construction", "1945"],
						["Philips", "450W", "HO 450 of later Dutch construction", "1956"]
					],
					pictures: ["/t Osram HgH1000.jpg", "/t D MA Osram HgH2000.jpg", "/t Philips HO450.jpg"]
				},
				{
					subhead: "American Lamps",
					intros: [
						["Westinghouse", "400W", "A-H1 of early American design", "1942"],
						["GE", "400W", "A-H1 of early American design", "1947"],
						["GE", "250W", "H-2 with unusual bare arc tube design", "1944"],
						["GE", "400W", "H25-DE of late American design", "1959"]
					],
					pictures: ["/t Westinghouse H1.jpg", "/t GE A-H1.jpg", "/t GE H2.jpg", "/t GE H25DE.jpg"]
				},
				{
					subhead: "Soviet Lamps",
					intros: [["MELZ", "500W", "IGAR-2 of high power Russian design", "1957"]],
					pictures: ["/t D MA MELZ IGAR-2.jpg"]
				},
				{
					subhead: "Coloured Lamps",
					intros: [
						["Siemens", "400W", "Sieray MA/H coloured lamp for floodlighting", "~1940"],
						["Siemens", "400W", "Sieray MA/H coloured lamp for floodlighting", "~1940"]
					],
					pictures: ["/t Siemens MAV400 Green.jpg", "/t Siemens MAV400 Yellow.jpg"]
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
					title: "中压汞蒸气",
					description: [
						"中压汞灯被归类为MA型。它们在大约一个大气压的蒸气压力下工作，放电在每厘米弧长之间耗散10到100瓦的功率，它们的弧光管由一种特殊的耐热铝硅酸盐硬玻璃制成。",
						"这是第一个用于普通照明应用的成功汞灯。该技术是由英国的欧司朗-通用电气（Osram-GEC）在1931年开发的，它将自己在玻璃制造方面的专业知识与德国欧司朗构思的一种全新的电极设计相结合。该概念于1932年推出，并取得了巨大的成功。到1933年，该灯具技术已授权给欧洲制造商，1934年授权给美国制造商，并很快在全球范围内被采用。",
						"第一个灯具是400W的额定功率，仅限于垂直使用。后来的成就允许水平使用，然后是通用操作，并且开发了其他功率等级。然而，由于随着灯具功率的降低，效率迅速下降，150W和90W的低功率灯具在商业上并不可行。直到开发出MB高压灯，这个问题才得以解决。MA灯的改进型配有荧光灯泡，并采用自镇流设计。关于中压汞灯的发展和基本原理的详细信息可以在MA技术部分找到。"
					]
				},
				{
					subhead: "英国灯",
					intros: [
						["Osira", "150W", "Osira MA/V low wattage lamp", "1936-37"],
						["Mazda", "400W", "Mercra MA/V early British design", "1944"],
						["Philips", "250W", "Philora MA/V early British design", "1945"],
						["Mazda", "250W", "MA/U improved universal burning design", "1955"],
						["Crompton", "250W", "MA/V with air-filled outer bulb", "1959"],
						["Osram", "400W", "MA/V of late design for vertical use", "1963"],
						["Mazda", "1000W", "MA/H horizontal floodlighting", "1952"]
					],
					pictures: [
						"/t D MA Osira MAV150.jpg",
						"/t Mazda MAV400.jpg",
						"/t Philips MAV250.jpg",
						"/t Mazda MAU250.jpg",
						"/t Crompton MAV250.jpg",
						"/t Osram MAV400.jpg",
						"/t D MA Mazda MAH1000.jpg"
					]
				},
				{
					subhead: "欧洲灯",
					intros: [
						["Osram", "265W", "HgH 1000 of early German construction", "1957"],
						["Osram", "450W", "HgH 2000 of later German construction", "1945"],
						["Philips", "450W", "HO 450 of later Dutch construction", "1956"]
					],
					pictures: ["/t Osram HgH1000.jpg", "/t D MA Osram HgH2000.jpg", "/t Philips HO450.jpg"]
				},
				{
					subhead: "美国灯",
					intros: [
						["Westinghouse", "400W", "A-H1 of early American design", "1942"],
						["GE", "400W", "A-H1 of early American design", "1947"],
						["GE", "250W", "H-2 with unusual bare arc tube design", "1944"],
						["GE", "400W", "H25-DE of late American design", "1959"]
					],
					pictures: ["/t Westinghouse H1.jpg", "/t GE A-H1.jpg", "/t GE H2.jpg", "/t GE H25DE.jpg"]
				},
				{
					subhead: "苏联灯",
					intros: [["MELZ", "500W", "IGAR-2 of high power Russian design", "1957"]],
					pictures: ["/t D MA MELZ IGAR-2.jpg"]
				},
				{
					subhead: "彩色灯",
					intros: [
						["Siemens", "400W", "Sieray MA/H coloured lamp for floodlighting", "~1940"],
						["Siemens", "400W", "Sieray MA/H coloured lamp for floodlighting", "~1940"]
					],
					pictures: ["/t Siemens MAV400 Green.jpg", "/t Siemens MAV400 Yellow.jpg"]
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
