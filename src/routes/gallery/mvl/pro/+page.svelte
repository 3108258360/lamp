<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Mercury Projection",
					description: [
						"The high intrinsic brightness of the mercury vapour discharge at once attracted the interest of optical engineers, to create a more effective lamp for image projection applications than had been possible with tungsten filament technologies. Early variants consisted of the arc tubes of MB High Pressure lamps sealed into a compact clear outer bulb, to enable it to be brought closer to an optical system.",
						"Efforts then focussed on overpowering these lamps at still higher pressure to achieve even greater brightness, but soon reached the limits of strength of the quartz arc tubes. In 1935 Philips of the Netherlands developed the MD class of Capillary lamps, whose pressure is typically in the range 50-200 atmospheres with a power dissipation >100W per cm. To prevent immediate destruction of the quartz arc tube, its outer surface must be chilled by a flow of water having sufficiently high velocity to prevent the water from boiling. Despite such extreme measures, the life of MD lamps is rather short. Failure is due to devitrification of the inner surface of the arc tube, which may either become so opaque that the intensity falls off and the lamp becomes useless for its application, or it will become sufficiently weakened that it cannot contain the internal pressure and will explode. Despite the immensely high pressure within the arc tube the explosion is not particularly violent in view of the small tube volume. Typical service life is of the order of fifty hours.",
						"Almost in parallel with the Dutch development of MD lamps, the British and Germans explored an alternative concept consisting of an extremely short arc within a spherical thick-walled quartz arc tube. That work led to introduction of the ME Short Arc lamps, having power loadings in the region of 1000 watts per centimetre of arc length and mercury pressures of around 25-100 atmospheres. The reduced thermal loading of the enlarged spherical arc tubes obviated the need for complex water cooling, and dramatically extended lamp life. ME lamps were produced in a wide variety of powers from 50W to 25,000W, sometimes with the addition of cadmium to increase the red ratio (type MEC lamps). Such lamps have an extremely rich shortwave ultraviolet spectrum, which makes them the favoured radiation sources for microlithographic printing in the semiconductor industry. Following the development of metal halide lamps, the pure mercury short arc ME types were almost completely supserseded by the MEI class containing metal iodide salts to improve the colour rendering.",
						"Around the turn of the last century, there was a return to pure mercury discharges running at Ultra High Pressures above 200 atmospheres. Their benefit over metal halide types is an improved spatial colour uniformity, and the fact that their arc gap can be made much shorter. This is of profound importance in digital image projection devices, a technology which became commonplace largely thanks to the development of this remarkable projection light source."
					]
				},
				{
					subhead: "High Pressure",
					intros: [
						["GEC", "80W", "MB/D Projector lamp with handmade arctube", "1942"],
						["GE", "85W", "H85A3/UV Lab-Arc Ultraviolet Source", "1952"],
						["Mazda", "80W", "MB/D for monochrome slide projection", "1962"],
						["Mazda", "125W", "MBL/D with diaphragms for laboratory use", "1967"],
						["Philips", "125W", "HPK 125 for laboratory use", "1975"]
					],
					pictures: [
						"/t GEC MBD80.jpg",
						"/t GE H85UV.jpg",
						"/t Mazda MBD80.jpg",
						"/t Mazda MBLD125.jpg",
						"/t Philips HPK125.jpg"
					]
				},
				{
					subhead: "High Pressure Capillary",
					intros: [
						["Mazda", "1000W", "MD/H arc tube with water jacket", "1947"],
						["Philips", "500W", "SP500 arc tube mounted in reflector housing", "1961"],
						["GE", "1000W", "AH-6 Super pressure water-cooled arc tube", "1961"],
						["ARC", "1000W", "Mercury Capillary with curved & coated tube", "~2000"]
					],
					pictures: [
						"/t D MD Mazda MD1000.jpg",
						"/t Philips SP500R.jpg",
						"/t D MB GE H6-A.jpg",
						"/t ARC MD Curved.jpg"
					]
				},
				{
					subhead: "High Pressure Short Arc",
					intros: [
						["Osram", "250W", "ME/D Compact Source Glass 3-Pin style", "1959"],
						["Mazda", "250W", "ME/D Compact Source Glass 3-Pin style", "1963"],
						["Thorn", "250W", "ME/D Compact Source Glass Pre-focus style", "1980"],
						["Osram", "250W", "ME/D Compact Source Metal box 3-Pin style", "1964"],
						["Mazda", "250W", "ME/D Compact Source Metal box Prefocus style", "1950"],
						["Osira", "500W", "ME/H Bombing Teacher Glass Pre-focus style", "1945"],
						["Westinghouse", "250W", "SAH-250B Short Arc DC Mercury", "1942"],
						["Osram", "3500W", "HBO deep UV source for semiconductr fabrication", "2000"]
					],
					pictures: [
						"/t Osram MED250.jpg",
						"/t Mazda MED Glass.jpg",
						"/t Thorn MED250.jpg",
						"/t Osram MED250 Box.jpg",
						"/t Mazda MED Oval.jpg",
						"/t Osram MED500.jpg",
						"/t Westinghouse SAH250B.jpg",
						"/t Osram HBO3500.jpg"
					]
				},
				{
					subhead: "Ultra High Pressure",
					intros: [
						["Philips", "120W", " UHP 120W projector First Generation lamp", "1995"],
						["Philips", "120W", "UHP 120W for LCD Video Projector", "2001"]
					],
					pictures: ["/t Philips UHP First.jpg", "/t Philips UHP120.jpg"]
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
					title: "汞投影灯",
					description: [
						"汞蒸气放电的高固有亮度立即吸引了光学工程师的兴趣，使其能够制造出比白炽灯技术更有效的用于图像投影应用的灯。早期的变体由MB高压灯的弧光管密封在一个紧凑的透明外灯泡中，以便将其靠近光学系统。",
						"随后的努力集中在以更高的压力过载这些灯，以实现更高的亮度，但很快就达到了石英弧光管强度的极限。1935年，荷兰的飞利浦开发了MD系列毛细管灯，其压力通常在50-200个大气压之间，每厘米功率消耗>100瓦。为了防止石英弧光管立即破裂，其外表面必须通过足够高速度的水流来冷却，以防止水沸腾。尽管采取了如此极端的措施，MD灯的使用寿命仍然相对较短。灯的失效是由于弧光管内表面的脱玻化，这可能使表面变得如此不透明，以至于强度下降，灯对其应用变得无用，或者它会变得足够弱，无法承受内部压力并爆炸。尽管弧光管内的压力极高，但由于管体积小，爆炸并不特别剧烈。典型使用寿命约为50小时。",
						"几乎与荷兰开发MD灯的同时，英国人和德国人探索了一种替代概念，即在一个球形厚壁石英弧光管内有一个极短的弧光。这项工作导致了ME短弧灯的推出，其功率负荷约为每厘米弧长1000瓦，汞压约为25-100个大气压。扩大的球形弧光管的热负荷减少，消除了复杂的水冷却的需要，并显著延长了灯的使用寿命。ME灯的功率范围从50瓦到25000瓦不等，有时添加镉以增加红色比例（MEC型灯）。这种灯具有极其丰富的短波紫外线光谱，使其成为半导体行业中微影印刷的首选辐射源。随着金属卤化物灯的发展，纯汞短弧ME型几乎被含有金属碘化物盐的MEI类完全取代，以改善显色性。",
						"在上个世纪之交，人们又回到了运行在超高压力（超过200个大气压）的纯汞放电。与金属卤化物类型相比，其好处是空间颜色均匀性更好，而且其弧隙可以做得更短。这在数字图像投影设备中具有深远的重要性，这种投影光源的发展使得这种技术变得司空见惯。"
					]
				},
				{
					subhead: "高压",
					intros: [
						["GEC", "80W", "MB/D Projector lamp with handmade arctube", "1942"],
						["GE", "85W", "H85A3/UV Lab-Arc Ultraviolet Source", "1952"],
						["Mazda", "80W", "MB/D for monochrome slide projection", "1962"],
						["Mazda", "125W", "MBL/D with diaphragms for laboratory use", "1967"],
						["Philips", "125W", "HPK 125 for laboratory use", "1975"]
					],
					pictures: [
						"/t GEC MBD80.jpg",
						"/t GE H85UV.jpg",
						"/t Mazda MBD80.jpg",
						"/t Mazda MBLD125.jpg",
						"/t Philips HPK125.jpg"
					]
				},
				{
					subhead: "高压毛细管",
					intros: [
						["Mazda", "1000W", "MD/H arc tube with water jacket", "1947"],
						["Philips", "500W", "SP500 arc tube mounted in reflector housing", "1961"],
						["GE", "1000W", "AH-6 Super pressure water-cooled arc tube", "1961"],
						["ARC", "1000W", "Mercury Capillary with curved & coated tube", "~2000"]
					],
					pictures: [
						"/t D MD Mazda MD1000.jpg",
						"/t Philips SP500R.jpg",
						"/t D MB GE H6-A.jpg",
						"/t ARC MD Curved.jpg"
					]
				},
				{
					subhead: "高压短弧",
					intros: [
						["Osram", "250W", "ME/D Compact Source Glass 3-Pin style", "1959"],
						["Mazda", "250W", "ME/D Compact Source Glass 3-Pin style", "1963"],
						["Thorn", "250W", "ME/D Compact Source Glass Pre-focus style", "1980"],
						["Osram", "250W", "ME/D Compact Source Metal box 3-Pin style", "1964"],
						["Mazda", "250W", "ME/D Compact Source Metal box Prefocus style", "1950"],
						["Osira", "500W", "ME/H Bombing Teacher Glass Pre-focus style", "1945"],
						["Westinghouse", "250W", "SAH-250B Short Arc DC Mercury", "1942"],
						["Osram", "3500W", "HBO deep UV source for semiconductr fabrication", "2000"]
					],
					pictures: [
						"/t Osram MED250.jpg",
						"/t Mazda MED Glass.jpg",
						"/t Thorn MED250.jpg",
						"/t Osram MED250 Box.jpg",
						"/t Mazda MED Oval.jpg",
						"/t Osram MED500.jpg",
						"/t Westinghouse SAH250B.jpg",
						"/t Osram HBO3500.jpg"
					]
				},
				{
					subhead: "超高压",
					intros: [
						["Philips", "120W", " UHP 120W projector First Generation lamp", "1995"],
						["Philips", "120W", "UHP 120W for LCD Video Projector", "2001"]
					],
					pictures: ["/t Philips UHP First.jpg", "/t Philips UHP120.jpg"]
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
