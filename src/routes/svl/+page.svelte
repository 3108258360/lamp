<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			viewFullImage: "View Full Image",
			close: "Close",
			returnHome: "Home",
			boxes: [
				{
					title: "Sodium-vapor lamp",
					imgs: ["A_High_Pressure_Sodium_Light_in_Toronto_Min.jpg", "Sodium-glow_Min.jpg"],
					description: [
						"A sodium-vapor lamp is a gas-discharge lamp that uses sodium in an excited state to produce light at a characteristic wavelength near 589 nm.",
						"Two varieties of such lamps exist: low pressure, and high pressure. Low-pressure sodium lamps are highly efficient electrical light sources, but their yellow light restricts applications to outdoor lighting, such as street lamps, where they are widely used. High-pressure sodium lamps emit a broader spectrum of light than the low-pressure lamps, but they still have poorer color rendering than other types of lamps. Low-pressure sodium lamps give only monochromatic yellow light, inhibiting color vision at night.",
						"Single ended self-starting lamps are insulated with a mica disc and contained in a borosilicate glass gas discharge tube (arc tube) with a metal cap. They include the sodium-vapor lamp that is the gas-discharge lamp used in street lighting.",
						"The low-pressure sodium arc discharge lamp was first made practical around 1920 owing to the development of a type of glass that could resist the corrosive effects of sodium vapor. These operated at pressures of less than 1 Pa and produced a near monochromatic light spectrum around the sodium emission lines at 589.0 and 589.56 nanometres wavelength. The yellow light produced by these limited the range of applications to those where color vision was not required.",
						"Research into high-pressure sodium lamps occurred in both the United Kingdom and the United States. Increasing the pressure of the sodium vapor broadened the sodium emission spectrum so that the light produced had more energy emitted at wavelengths above and below the 589 nm region. The quartz material used in mercury discharge lamps was corroded by high pressure sodium vapor. A laboratory demonstration of a high pressure lamp was carried out in 1959. The development by General Electric of a sintered aluminum oxide material (with magnesium oxide added to improve light transmission) was an important step in construction of a commercial lamp. The material was available in the form of tubing by 1962, but additional techniques were required to seal the tubes and add the necessary electrodes—the material could not be fused like quartz. The end caps of the arc tube would get as hot as 800 °C (1,470 °F) in operation, then cool to room temperature when the lamp was turned off, so the electrode terminations and arc tube seal had to tolerate repeated temperature cycles. This problem was solved by Michael Arendash at the GE Nela Park plant. The first commercial high-pressure sodium lamps were available in 1965 from companies in the United States, the United Kingdom, and the Netherlands; at introduction a 400 watt lamp would produce around 100 lumens per watt.",
						"Single-crystal artificial sapphire tubes were also manufactured and used for HPS lamps in the early 1970s, with a slight improvement in efficacy, but production costs were higher than for polycrystalline alumina tubes."
					]
				},
				{
					title: "Low-pressure sodium lamp",
					imgs: [
						"LPS_Lamp_35W_Min.jpg",
						"LPS_Lamp_35W_running_Min.jpg",
						"LPS_lamp_warm-up_Min.png"
					],
					description: [
						"Low-pressure sodium (LPS) lamps have a borosilicate glass gas discharge tube (arc tube) containing solid sodium and a small amount of neon and argon gas in a Penning mixture to start the gas discharge. The discharge tube may be linear (SLI lamp) or U-shaped. When the lamp is first started, it emits a dim red/pink light to warm the sodium metal; within a few minutes as the sodium metal vaporizes, the emission becomes the common bright yellow. These lamps produce a virtually monochromatic light averaging a 589.3 nm wavelength (actually two dominant spectral lines very close together at 589.0 and 589.6 nm). The colors of objects illuminated by only this narrow bandwidth are difficult to distinguish.",
						"LPS lamps have an outer glass vacuum envelope around the inner discharge tube for thermal insulation, which improves their efficiency. Earlier LPS lamps had a detachable dewar jacket (SO lamps). Lamps with a permanent vacuum envelope (SOI lamps) were developed to improve thermal insulation. Further improvement was attained by coating the glass envelope with an infrared reflecting layer of indium tin oxide, resulting in SOX lamps.",
						"LPS lamps are among the most efficient electrical light sources when measured in photopic lighting conditions, producing above 100 and up to 206 lm/W. This high efficiency is partly due to the light emitted being at a wavelength near the peak sensitivity of the human eye. They are used mainly for outdoor lighting (such as street lights and security lighting) where faithful color rendition is not important.",
						"LPS lamps are similar to fluorescent lamps in that they are a low-intensity light source with a linear lamp shape. They do not exhibit a bright arc as do high-intensity discharge (HID) lamps; they emit a softer luminous glow, resulting in less glare. Unlike HID lamps, during a voltage dip low-pressure sodium lamps return to full brightness rapidly. LPS lamps are available with power ratings from 10 to 180 W; longer lamp lengths can, however, suffer design and engineering problems.",
						"Modern LPS lamps have a service life of about 18,000 hours and do not decline in lumen output with age, though they do increase in energy consumption by about 10% towards end of life. This property contrasts with mercury vapor HID lamps, which become dimmer towards the end of life to the point of being ineffective, while consuming undiminished electrical power.",
						"In 2017 Philips Lighting, the last manufacturer of LPS lamps, announced they were discontinuing production of the lamps due to falling demand. Initially, production was due to be phased out in the course of 2020, but this date was brought forward and the last lamps were produced at the Hamilton, Scotland factory on December 31,2019."
					]
				}
			]
		},
		zh: {
			viewFullImage: "查看原图",
			close: "退出",
			returnHome: "首页",
			boxes: [
				{
					title: "钠灯",
					imgs: ["A_High_Pressure_Sodium_Light_in_Toronto_Min.jpg", "Sodium-glow_Min.jpg"],
					description: [
						"钠蒸气灯是一种气体放电灯，利用激发态的钠产生波长接近589纳米的特征光。",
						"这种灯有两种类型：低压和高压。低压钠灯是高效的电光源，但其黄色光限制了其应用范围，主要用于户外照明，如路灯，在那里被广泛使用。高压钠灯比低压钠灯发出更宽光谱的光，但它们的显色性仍然不如其他类型的灯。低压钠灯只能发出单色黄光，这在夜间抑制了色彩视觉。",
						"单端自启动灯用云母片绝缘，并装在一个带有金属帽的硼硅酸盐玻璃气体放电管（弧管）中。它们包括用于路灯的钠蒸气灯，即气体放电灯。",
						"由于开发出一种能抵抗钠蒸气腐蚀的玻璃，低压钠弧放电灯在1920年左右开始实用化。这些灯在低于1帕的压力下工作，产生接近钠发射线589.0和589.56纳米波长的近乎单色的光谱。这些灯发出的黄光限制了其应用范围，仅限于不需要色彩视觉的场合。",
						"对高压钠灯的研究在英国和美国都有进行。提高钠蒸气的压力拓宽了钠的发射光谱，使发出的光在589纳米区域的上下波长有更多的能量发射。用于汞放电灯的石英材料会被高压钠蒸气腐蚀。1959年进行了一次高压灯的实验室演示。通用电气公司开发的烧结氧化铝材料（添加氧化镁以提高光的透过率）是制造商业灯的重要一步。到1962年，这种材料已以管材的形式出现，但还需要额外的技术来密封管子并添加必要的电极——这种材料不能像石英那样熔接。弧管的端盖在运行时温度可达800°C（1470°F），关灯后则冷却至室温，因此电极引线和弧管密封必须能够承受反复的温度循环。这一问题由通用电气公司奈拉公园工厂的迈克尔·阿伦达什解决。1965年，美国、英国和荷兰的公司首次推出了商业高压钠灯；在推出时，400瓦的灯大约可以产生每瓦100流明的光。",
						"在20世纪70年代初，还制造并使用了单晶人造蓝宝石管用于高压钠灯，其效率略有提高，但生产成本高于多晶氧化铝管。"
					]
				},
				{
					title: "低压钠灯",
					imgs: [
						"LPS_Lamp_35W_Min.jpg",
						"LPS_Lamp_35W_running_Min.jpg",
						"LPS_lamp_warm-up_Min.png"
					],
					description: [
						"低压钠（LPS）灯有一个硼硅酸盐玻璃气体放电管（弧管），其中含有固态钠和少量氖气与氩气的潘宁混合气体，用于启动气体放电。放电管可能是线性的（SLI灯）或U形的。当灯首次启动时，它会发出暗红色/粉色的光来加热钠金属；几分钟后，随着钠金属的汽化，发光变为常见的明亮黄色。这些灯发出的光几乎是单色的，平均波长为589.3纳米（实际上是两个非常接近的主导光谱线，分别为589.0纳米和589.6纳米）。仅在这种狭窄波段的光照射下，物体的颜色很难区分。",
						"LPS灯在内部放电管周围有一个外层玻璃真空外壳，用于隔热，从而提高了它们的效率。早期的LPS灯有一个可拆卸的杜瓦夹套（SO灯）。开发了具有永久真空外壳的灯具（SOI灯），以改善隔热效果。通过在玻璃外壳上涂覆一层氧化铟锡制成的红外反射层，进一步提高了隔热效果，从而产生了SOX灯。",
						"在光opic照明条件下测量时，LPS灯是效率最高的电光源之一，光效超过100流明/瓦，最高可达206流明/瓦。这种高效率部分归因于发出的光的波长接近人眼的峰值灵敏度。它们主要用于户外照明（如路灯和安全照明），在这些场合，准确的色彩还原并不重要。",
						"LPS灯与荧光灯类似，它们是低强度光源，具有线性灯形。它们不像高强度放电（HID）灯那样有明亮的弧光；它们发出柔和的光晕，从而减少眩光。与HID灯不同，在电压骤降时，低压钠灯能迅速恢复到全亮度。LPS灯的功率范围为10瓦至180瓦；然而，较长的灯管可能会出现设计和工程问题。",
						"现代LPS灯的使用寿命约为18000小时，并且其光输出不会随着使用时间的增加而下降，尽管它们在使用寿命末期的功耗会增加约10%。这一特性与汞蒸气HID灯形成对比，汞蒸气HID灯在使用寿命末期会变得越来越暗，最终失去照明效果，同时仍然消耗相同的电功率。",
						"2017年，作为最后一家生产LPS灯的制造商，飞利浦照明公司宣布由于需求下降，他们将停止生产这种灯。最初，计划在2020年逐步停产，但这一日期被提前了，最后一批灯于2019年12月31日在苏格兰汉密尔顿工厂生产。"
					]
				}
			]
		}
	};
	type Language = "zh" | "en";
	let language: Language = "en";

	onMount(() => {
		language = (localStorage.getItem("language") as Language) || "en";
		if (!translations[language]) {
			language = "en";
		}
	});
</script>

<TranslationBox {translations} {language} />

<button on:click={() => goto("/")} class="return-home">{translations[language].returnHome}</button>
