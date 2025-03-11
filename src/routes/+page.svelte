<script lang="ts">
	import { onMount } from "svelte";
	type Language = "en" | "zh";
	let language: Language = "zh";
	let buttonText: string;

	const texts = {
		en: {
			title: "Welcome to the Museum of Electric Lamp Technology",
			description: [
				"The first artificial electric light was demonstrated during 1802 in London, by Sir Humphry Davy at the Royal Institution of Great Britain. It was the carbon arc discharge lamp, and since then the electric discharge has been intensely researched and developed for one fundamental reason - that it creates light from electricity more efficiently than any other kind of artificial light source.",
				"Over time it was learned that the discharge could be made to generate light more efficiently by arranging that it took place inside a rare gas instead of through the air. This led to the creation of gaseous discharge lamps which frequently make use of the noble gases helium, neon, argon, krypton or xenon. Carbon dioxide was also of considerable interest owing to its white light output.",
				"During the later parts of the nineteenth and  early twentieth centuries, developments in discharge lamps took a back seat whilst efforts were focussed  on the development of an incandescent lamp. Although the arc was very efficient by comparison with other sources of its time, it was intensely bright and mainly suited to outdoor illumination. Small oil and gas burners continued to dominate indoors and to coin a phrase of Sir Joseph Swan, it was recognised that efforts should be made to 'subdivide the electric light', such that it could be made in smaller lumen packages for the mass market of indoor lighting.",
				"There were numerous contributors, but the first men to achieve practical success with commercially viable lamps were Sir Joseph Swan in England, and Thomas Edison in America, who quite independently invented the carbon filament incandescent lamp in 1878. Numerous changes have taken place over the years in search of better filament materials yielding increased efficacy and longer life. In addition, developments in halogen chemistry have realised smaller, longer lived and still more efficient lamps, and optical innovations have played an important role in efficiently creating beams of usable light.",
				"In the 1930s attention returned to the discharge lamps, this time employing metallic vapours instead of the former gaseous fillings. Sodium and mercury were initially employed on account of their high vapour pressures and desirable emission in the visible spectrum, but their light colours are not white.  The combination of luminescent materials with the mercury discharge has led to tremendous progress in the field of fluorescent lighting, and since the 1950s the colour properties of the discharge itself were improved by the introduction of other elements in the form of metal halide salts.",
				"In more recent years, a  new category of solid-state light sources is emerging in the form of Light Emitting Diodes and their Organic counterparts, which are having an equally profound effect on the lighting market. In addition to general illumination with white light, their potential to create saturated colours with high efficacy has opened up entirely new areas in decorative lighting.",
				"This website traces the development of the materials, science and technology behind electric light sources from their earliest beginnings right up to the present day. Where possible, these developments are illustrated with examples of historic lamps. Please follow the links on the left to choose a particular family of light source. Clicking on the category title will reveal technical information regarding the development of that style of light source. Choosing individual sub-category headings will bring up a page illustrating that technology with historic examples of the same."
			],
			linkText: [
				["Incandescent lamp", "/il"],
				["Fluorescent Lamp", "/fl"],
				["Sodium-vapor lamp", "/svl"]
			],
			buttonText: "中文"
		},
		zh: {
			title: "欢迎来到电灯技术博物馆",
			description: [
				"1802年，汉弗里·戴维爵士在伦敦大不列颠皇家学会首次展示了人造电光，即碳弧放电灯。自那以后，电放电被深入研究和开发，原因只有一个——它比其他任何类型的人造光源都更高效地将电能转化为光能。",
				"随着时间的推移，人们发现通过将放电安排在稀有气体中而不是空气中进行，可以使其更高效地产生光。这导致了气体放电灯的诞生，这种灯通常使用氦、氖、氩、氪或氙等惰性气体。由于其白光输出，二氧化碳也引起了相当大的关注。",
				"在19世纪后期和20世纪初期，放电灯的发展退居二线，而人们集中精力开发白炽灯。尽管与当时的其他光源相比，电弧非常高效，但它非常明亮，主要用于户外照明。小型油灯和煤气灯继续在室内占据主导地位。正如约瑟夫·斯旺爵士所说，人们认识到应该努力“细分电灯”，使其能够以更小的流明包装生产，以满足室内照明的大众市场。",
				"有许多人做出了贡献，但在商业可行的灯具方面取得实际成功的第一个人是英国的约瑟夫·斯旺爵士和美国的托马斯·爱迪生，他们于1878年独立发明了碳丝白炽灯。多年来，人们一直在寻找更好的灯丝材料，以提高效率和延长使用寿命。此外，卤素化学的发展实现了更小、更长寿且更高效的灯具，光学创新在高效产生可用光束方面也发挥了重要作用。",
				"20世纪30年代，人们的注意力重新回到了放电灯，这次使用金属蒸汽而不是以前的气体填充物。最初使用钠和汞是因为它们的蒸汽压高且在可见光谱中有理想的发射，但它们的光色不是白色。荧光材料与汞放电的结合在荧光照明领域取得了巨大进步，自20世纪50年代以来，通过引入其他元素的金属卤化物，放电本身的色性也得到了改善。",
				"在最近几年，一种新的固态光源类别以发光二极管及其有机对应物的形式出现，它们对灯具市场产生了同样深远的影响。除了用白光进行一般照明外，它们在产生高效率的饱和色方面的潜力也为装饰性照明开辟了全新的领域。",
				"这个网站追溯了电光源的材料、科学和技术的发展，从它们最早的起源一直到今天。在可能的情况下，这些发展通过历史灯具的例子来说明。请通过左侧的链接选择特定类型的光源。点击类别标题将显示该类型光源的发展技术信息。选择各个子类别的标题将显示带有相同技术的历史实例的页面。"
			],
			linkText: [
				["白炽灯", "/il"],
				["荧光灯", "/fl"],
				["钠灯", "/svl"]
			],
			buttonText: "English"
		}
	} as const;

	function updateLanguage(lang: Language) {
		language = lang;
		localStorage.setItem("language", language);
		buttonText = texts[language].buttonText;
	}

	onMount(() => {
		const savedLanguage = localStorage.getItem("language") as Language;
		if (savedLanguage) {
			updateLanguage(savedLanguage);
		} else {
			updateLanguage("zh");
		}
	});

	function toggleLanguage() {
		updateLanguage(language === "en" ? "zh" : "en");
	}

	$: text = texts[language];
</script>

<button on:click={toggleLanguage} style="position:fixed; top: 20px; right: 20px;">
	{buttonText}
</button>
<div class="box">
	<h1>{text.title}</h1>
	{#each text.linkText as [linkName, linkHref]}
		<a href={linkHref} style="margin-right: 10px;">{linkName}</a>
	{/each}
	{#each text.description as descriptionItem}
		<p>{descriptionItem}</p>
	{/each}
</div>
