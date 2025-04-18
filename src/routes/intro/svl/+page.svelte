<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Sodium-vapor lamp",
					subhead: "Introduction",
					imgs: ["/A_High_Pressure_Sodium_Light_in_Toronto_Min.jpg"],
					description: [
						"A sodium-vapor lamp is a gas-discharge lamp that uses sodium in an excited state to produce light at a characteristic wavelength near 589 nm.",
						"Two varieties of such lamps exist: low pressure, and high pressure. Low-pressure sodium lamps are highly efficient electrical light sources, but their yellow light restricts applications to outdoor lighting, such as street lamps, where they are widely used. High-pressure sodium lamps emit a broader spectrum of light than the low-pressure lamps, but they still have poorer color rendering than other types of lamps. Low-pressure sodium lamps give only monochromatic yellow light, inhibiting color vision at night.",
						"Single ended self-starting lamps are insulated with a mica disc and contained in a borosilicate glass gas discharge tube (arc tube) with a metal cap. They include the sodium-vapor lamp that is the gas-discharge lamp used in street lighting."
					]
				},
				{
					subhead: "Development",
					description: [
						"The low-pressure sodium arc discharge lamp was first made practical around 1920 owing to the development of a type of glass that could resist the corrosive effects of sodium vapor. These operated at pressures of less than 1 Pa and produced a near monochromatic light spectrum around the sodium emission lines at 589.0 and 589.56 nanometres wavelength. The yellow light produced by these limited the range of applications to those where color vision was not required.",
						"Research into high-pressure sodium lamps occurred in both the United Kingdom and the United States. Increasing the pressure of the sodium vapor broadened the sodium emission spectrum so that the light produced had more energy emitted at wavelengths above and below the 589 nm region. The quartz material used in mercury discharge lamps was corroded by high pressure sodium vapor. A laboratory demonstration of a high pressure lamp was carried out in 1959. The development by General Electric of a sintered aluminum oxide material (with magnesium oxide added to improve light transmission) was an important step in construction of a commercial lamp. The material was available in the form of tubing by 1962, but additional techniques were required to seal the tubes and add the necessary electrodes—the material could not be fused like quartz. The end caps of the arc tube would get as hot as 800 °C (1,470 °F) in operation, then cool to room temperature when the lamp was turned off, so the electrode terminations and arc tube seal had to tolerate repeated temperature cycles. This problem was solved by Michael Arendash at the GE Nela Park plant. The first commercial high-pressure sodium lamps were available in 1965 from companies in the United States, the United Kingdom, and the Netherlands; at introduction a 400 watt lamp would produce around 100 lumens per watt.",
						"Single-crystal artificial sapphire tubes were also manufactured and used for HPS lamps in the early 1970s, with a slight improvement in efficacy, but production costs were higher than for polycrystalline alumina tubes."
					]
				},
				{
					subhead: "End of life",
					description: [
						"At end of life, high-pressure sodium (HPS) lamps exhibit a phenomenon known as cycling, caused by a loss of sodium in the arc. Sodium is a highly reactive element and is lost in a reaction with the aluminum oxide of the arc tube. ",
						"As a result, these lamps can be started at a relatively low voltage, but, as they heat up during operation, the internal gas pressure within the arc tube rises, and more and more voltage is required to maintain the arc discharge. As a lamp gets older, the maintaining voltage for the arc eventually rises to exceed the maximum voltage output by the electrical ballast. As the lamp heats to this point, the arc fails, and the lamp goes out. Eventually, with the arc extinguished, the lamp cools down again, the gas pressure in the arc tube is reduced, and the ballast can once again cause the arc to strike. The effect of this is that the lamp glows for a while and then goes out, typically starting at a pure or bluish white then moving to a red-orange before going out.",
						"More sophisticated ignitor designs detect cycling and give up attempting to start the lamp after a few cycles, as the repeated high-voltage ignitions needed to restart the arc reduce the lifetime of the ballast or the ignitor, depending on the ignitor configuration. If power is removed and reapplied, the ballast will make a new series of startup attempts.",
						"LPS lamp failure does not result in cycling; rather, the lamp will simply not strike or will maintain the dull red glow of the start-up phase. In another failure mode, a tiny puncture of the arc tube leaks some of the sodium vapor into the outer vacuum bulb. The sodium condenses and creates a mirror on the outer glass, partially obscuring the arc tube. The lamp often continues operating normally, but much of the light generated is obscured by the sodium coating, providing no illumination."
					]
				},
				{
					title: "Low-pressure sodium lamp",
					imgs: [
						"/LPS_Lamp_35W_Min.jpg",
						"/LPS_Lamp_35W_running_Min.jpg",
						"/LPS_lamp_warm-up_Min.png",
						"/LPS Electrical parameters_Min.png"
					],
					description: [
						"Low-pressure sodium (LPS) lamps have a borosilicate glass gas discharge tube (arc tube) containing solid sodium and a small amount of neon and argon gas in a Penning mixture to start the gas discharge. The discharge tube may be linear (SLI lamp) or U-shaped. When the lamp is first started, it emits a dim red/pink light to warm the sodium metal; within a few minutes as the sodium metal vaporizes, the emission becomes the common bright yellow. These lamps produce a virtually monochromatic light averaging a 589.3 nm wavelength (actually two dominant spectral lines very close together at 589.0 and 589.6 nm). The colors of objects illuminated by only this narrow bandwidth are difficult to distinguish.",
						"LPS lamps have an outer glass vacuum envelope around the inner discharge tube for thermal insulation, which improves their efficiency. Earlier LPS lamps had a detachable dewar jacket (SO lamps). Lamps with a permanent vacuum envelope (SOI lamps) were developed to improve thermal insulation. Further improvement was attained by coating the glass envelope with an infrared reflecting layer of indium tin oxide, resulting in SOX lamps.",
						"LPS lamps are among the most efficient electrical light sources when measured in photopic lighting conditions, producing above 100 and up to 206 lm/W. This high efficiency is partly due to the light emitted being at a wavelength near the peak sensitivity of the human eye. They are used mainly for outdoor lighting (such as street lights and security lighting) where faithful color rendition is not important.",
						"LPS lamps are similar to fluorescent lamps in that they are a low-intensity light source with a linear lamp shape. They do not exhibit a bright arc as do high-intensity discharge (HID) lamps; they emit a softer luminous glow, resulting in less glare. Unlike HID lamps, during a voltage dip low-pressure sodium lamps return to full brightness rapidly. LPS lamps are available with power ratings from 10 to 180 W; longer lamp lengths can, however, suffer design and engineering problems.",
						"Modern LPS lamps have a service life of about 18,000 hours and do not decline in lumen output with age, though they do increase in energy consumption by about 10% towards end of life. This property contrasts with mercury vapor HID lamps, which become dimmer towards the end of life to the point of being ineffective, while consuming undiminished electrical power.",
						"In 2017 Philips Lighting, the last manufacturer of LPS lamps, announced they were discontinuing production of the lamps due to falling demand. Initially, production was due to be phased out in the course of 2020, but this date was brought forward and the last lamps were produced at the Hamilton, Scotland factory on December 31,2019."
					]
				},
				{
					title: "High-pressure sodium lamp",
					imgs: [
						"/SON-T_Master_600W_Min.jpg",
						"/SON-T-Master-600W_Min.jpg",
						"/HPS Electrical parameters_Min.png"
					],
					description: [
						"High-pressure sodium (HPS) lamps have been widely used in industrial lighting, especially in large manufacturing facilities, and are commonly used as plant grow lights. They contain mercury. They have also been widely used for outdoor area lighting, such as on roadways, parking lots, and security areas. Understanding the change in human color vision sensitivity from photopic to mesopic and scotopic is essential for proper planning when designing lighting for roadways.",
						"High-pressure sodium lamps are quite efficient—about 100 lumens per watt, when measured for photopic lighting conditions. Some higher-power lamps (e.g. 600 watt) have efficacies of about 150 lumens per watt.",
						'Since the high-pressure sodium arc is extremely chemically reactive, the arc tube is typically made of translucent aluminum oxide. This construction led the General Electric Company to use the tradename "Lucalox" for its line of high-pressure sodium lamps.',
						'Xenon at a low pressure is used as a "starter gas" in the HPS lamp. It has the lowest thermal conductivity and lowest ionization potential of all the stable noble gases. As a noble gas, it does not interfere with the chemical reactions occurring in the operating lamp. The low thermal conductivity minimizes thermal losses in the lamp while in the operating state, and the low ionization potential causes the breakdown voltage of the gas to be relatively low in the cold state, which allows the lamp to be easily started.',
						"A variation of the high-pressure sodium introduced in 1986, the White HPS has a higher pressure than the typical HPS lamp, producing a color temperature of around 2700 kelvins with a color rendering index (CRI) of about 85, greatly resembling the color of an incandescent light. These lamps are often used indoors in cafes and restaurants for aesthetic effect. However, white HPS lamps have higher cost, shorter service lives, and lower light efficiency, and so they cannot compete with HPS at this time.",
						"An amalgam of metallic sodium and mercury lies at the coolest part of the lamp and provides the sodium and mercury vapor that is needed to draw an arc. The temperature of the amalgam is determined to a great extent by lamp power. The higher the lamp power, the higher will be the amalgam temperature. The higher the temperature of the amalgam, the higher will be the mercury and sodium vapor pressures in the lamp and the higher will be the terminal voltage. As the temperature rises, the constant current and increasing voltage consumes increasing energy until the operating level of power is reached. For a given voltage, there are generally three modes of operation: The lamp is extinguished and no current flows. The lamp is operating with liquid amalgam in the tube. The lamp is operating with all amalgam evaporated.",
						"The first and last states are stable, because the lamp resistance is weakly related to the voltage, but the second state is unstable. Any anomalous increase in current will cause an increase in power, causing an increase in amalgam temperature, which will cause a decrease in resistance, which will cause a further increase in current. This will create a runaway effect, and the lamp will jump to the high-current state (#3). Because actual lamps are not designed to handle this much power, this would result in catastrophic failure. Similarly, an anomalous drop in current will drive the lamp to extinction. It is the second state that is the desired operating state of the lamp, because a slow loss of the amalgam over time from a reservoir will have less effect on the characteristics of the lamp than a fully evaporated amalgam. The result is an average lamp life in excess of 20,000 hours.",
						'In practical use, the lamp is powered by an AC voltage source in series with an inductive "ballast" in order to supply a nearly constant current to the lamp, rather than a constant voltage, thus assuring stable operation. The ballast is usually inductive rather than simply being resistive to minimize energy waste from resistance losses. Because the lamp effectively extinguishes at each zero-current point in the AC cycle, the inductive ballast assists in the reignition by providing a voltage spike at the zero-current point.',
						"The light from the lamp consists of atomic emission lines of mercury and sodium, but is dominated by the sodium D-line emission. This line is extremely pressure (resonance) broadened and is also self-reversed because of absorption in the cooler outer layers of the arc, giving the lamp its improved color rendering characteristics. In addition, the red wing of the D-line emission is further pressure broadened by the Van der Waals forces from the mercury atoms in the arc."
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
					title: "钠蒸气灯",
					subhead: "介绍",
					imgs: ["/A_High_Pressure_Sodium_Light_in_Toronto_Min.jpg"],
					description: [
						"钠蒸气灯是一种气体放电灯，它利用激发态的钠产生接近589纳米特征波长的光。",
						"这种灯有两种类型：低压和高压。低压钠灯是高效的电光源，但其黄色光线限制了其应用范围，主要用于户外照明，如路灯，在此领域被广泛使用。高压钠灯比低压钠灯发出更宽光谱的光，但它们的显色性仍不如其他类型的灯。低压钠灯只发出单色黄光，抑制了夜间对颜色的视觉感知。",
						"单端自启动灯用云母片绝缘，并装在带有金属帽的硼硅酸盐玻璃气体放电管（弧光管）中。它们包括用于路灯的钠蒸气灯，即气体放电灯。"
					]
				},
				{
					subhead: "发展",
					description: [
						"由于开发出一种能够抵抗钠蒸气腐蚀效应的玻璃，低压钠弧放电灯在1920年左右开始实用化。这些灯在低于1帕的压力下工作，产生接近钠发射线在589.0和589.56纳米波长处的近乎单色光谱。这些灯产生的黄光限制了其应用范围，仅适用于不需要彩色视觉的场合。",
						"对高压钠灯的研究在英国和美国都有开展。提高钠蒸气的压力拓宽了钠发射光谱，使得产生的光在589纳米区域的上下波长处发射了更多的能量。用于汞放电灯的石英材料会被高压钠蒸气腐蚀。1959年进行了一次高压灯的实验室演示。通用电气公司开发出一种烧结氧化铝材料（添加氧化镁以提高光传输效率）是制造商业用灯的重要一步。这种材料在1962年以管材形式问世，但还需要额外的技术来密封管材并添加必要的电极——这种材料不能像石英那样熔接。弧光管的端盖在运行时温度可高达800°C（1470°F），灯关闭后会冷却至室温，因此电极引脚和弧光管密封必须能够承受反复的温度循环。这一问题由通用电气公司尼拉公园工厂的迈克尔·阿伦达什解决。1965年，美国、英国和荷兰的公司首次推出了商业高压钠灯；在推出时，一款400瓦的灯泡每瓦大约能产生100流明。",
						"在20世纪70年代初，还制造并用于高压钠灯的单晶人造蓝宝石管，略微提高了功效，但生产成本比多晶氧化铝管更高。"
					]
				},
				{
					subhead: "寿命终结",
					description: [
						"在寿命终结时，高压钠（HPS）灯会出现一种被称为循环的现象，这是由于弧光管中钠的损失造成的。钠是一种高度活泼的元素，会在与弧光管的氧化铝的反应中损失。",
						"因此，这些灯可以在相对较低的电压下启动，但在运行过程中随着温度升高，弧光管内的气压上升，维持弧光放电所需的电压越来越高。随着灯的老化，维持弧光的电压最终会超过电气镇流器的最大输出电压。当灯加热到这一点时，弧光熄灭，灯熄灭。最终，随着弧光熄灭，灯冷却下来，弧光管内的气压降低，镇流器又能再次引燃弧光。这种现象导致灯亮一会儿然后熄灭，通常从纯白或蓝白色开始，然后变为红橙色，最后熄灭。",
						"更复杂的点火器设计能够检测到循环现象，并在几次循环后放弃尝试启动灯，因为重新引燃弧光所需的重复高电压会减少镇流器或点火器的使用寿命，具体取决于点火器的配置。如果切断电源后再重新接通，镇流器将再次进行一系列启动尝试。",
						"低压钠（LPS）灯故障不会导致循环现象；相反，灯要么根本无法引燃，要么只能保持启动阶段的暗红色光。在另一种故障模式中，弧光管上出现一个微小的穿孔，使得部分钠蒸气泄漏到外层真空泡中。钠凝结并在外玻璃上形成一面镜子，部分遮挡了弧光管。灯通常仍能正常运行，但大部分产生的光线被钠涂层遮挡，无法提供照明。"
					]
				},
				{
					title: "低压钠灯",
					imgs: [
						"/LPS_Lamp_35W_Min.jpg",
						"/LPS_Lamp_35W_running_Min.jpg",
						"/LPS_lamp_warm-up_Min.png",
						"/LPS Electrical parameters_Min.png"
					],
					description: [
						"低压钠（LPS）灯有一个含有固态钠以及少量氖气和氩气（用于启动气体放电的潘宁混合物）的硼硅酸盐玻璃气体放电管（弧光管）。放电管可能是直线形（SLI灯）或U形。灯刚启动时，发出暗红色/粉色光来加热钠金属；几分钟内，随着钠金属汽化，光变为常见的明亮黄色。这些灯发出的光几乎是单色光，平均波长为589.3纳米（实际上是589.0和589.6纳米处的两条非常接近的主导光谱线）。仅在这种狭窄波段照明下的物体颜色很难区分。",
						"LPS灯的外层有一个真空玻璃外壳，用于对内部放电管进行隔热，从而提高了其效率。早期的LPS灯有一个可拆卸的杜瓦夹套（SO灯）。为了改善隔热效果，开发了带有永久真空外壳的灯（SOI灯）。通过在玻璃外壳上涂覆一层氧化铟锡制成的红外反射层，进一步提高了性能，从而产生了SOX灯。",
						"LPS灯是光opic照明条件下最高效的电光源之一，光效超过100流明/瓦，最高可达206流明/瓦。这种高效率部分是因为发出的光波长接近人眼的峰值灵敏度。它们主要用于户外照明（如路灯和安全照明），在这些场合，准确的色彩还原并不重要。",
						"LPS灯与荧光灯相似，都是低强度光源，呈线性灯形。它们不像高强度放电（HID）灯那样有明亮的弧光；它们发出柔和的光，因此眩光更少。与HID灯不同，在电压下降时，低压钠灯能迅速恢复到全亮度。LPS灯的功率范围为10瓦至180瓦；然而，较长的灯管可能会出现设计和工程问题。",
						"现代LPS灯的使用寿命约为18000小时，随着使用时间的增长，其光输出不会下降，但在使用寿命接近结束时，其能耗会增加约10%。这一特性与汞蒸气HID灯形成对比，后者在使用寿命接近结束时会变暗，直至失去效力，同时消耗的电能却丝毫未减。",
						"2017年，作为最后一家生产LPS灯的厂商，飞利浦照明公司宣布将停止生产这种灯，原因是需求下降。最初计划在2020年逐步停产，但这一日期提前了，最后一批灯于2019年12月31日在苏格兰汉密尔顿工厂生产。"
					]
				},
				{
					title: "高压钠灯",
					imgs: [
						"/SON-T_Master_600W_Min.jpg",
						"/SON-T-Master-600W_Min.jpg",
						"/HPS Electrical parameters_Min.png"
					],
					description: [
						"高压钠（HPS）灯在工业照明中得到了广泛应用，特别是在大型制造设施中，并且通常用作植物生长灯。它们含有汞。它们还被广泛用于户外区域照明，例如道路、停车场和安全区域。了解人类色觉灵敏度从光opic到中opic再到暗opic的变化对于设计道路照明时的合理规划至关重要。",
						"高压钠灯的效率相当高——在光opic照明条件下，每瓦大约有100流明。一些高功率的灯（例如600瓦）的光效约为每瓦150流明。",
						"由于高压钠弧光具有极强的化学活性，因此弧光管通常由半透明的氧化铝制成。这种构造使通用电气公司为其高压钠灯系列使用了“Lucalox”这一商标。",
						"低压下的氙气被用作HPS灯的“启动气体”。它在所有稳定惰性气体中具有最低的热导率和最低的电离势。作为一种惰性气体，它不会干扰工作灯中发生的化学反应。低热导率使灯在工作状态下的热损失最小化，低电离势使气体在冷态下的击穿电压相对较低，从而使灯能够轻松启动。",
						"1986年引入的高压钠灯的一个变种是白光HPS，其压力高于典型的HPS灯，产生约2700开尔文的色温，显色指数（CRI）约为85，与白炽灯的颜色非常相似。这些灯通常用于咖啡馆和餐厅的室内，以达到美观效果。然而，白光HPS灯成本更高，使用寿命更短，光效更低，因此目前无法与HPS竞争。",
						"金属钠和汞的合金位于灯的最冷部分，提供产生电弧所需的钠和汞蒸气。合金的温度在很大程度上取决于灯的功率。灯的功率越高，合金的温度就越高。合金的温度越高，灯内汞和钠的蒸气压力就越高，端电压也就越高。随着温度的升高，恒定电流和不断增加的电压消耗的能量越来越多，直到达到运行功率水平。对于给定的电压，通常有三种工作模式：灯熄灭，没有电流流动。灯在管内有液态合金时工作。灯在所有合金都蒸发后工作。",
						"第一种和最后一种状态是稳定的，因为灯的电阻与电压关系不大，但第二种状态是不稳定的。任何异常的电流增加都会导致功率增加，从而导致合金温度升高，进而导致电阻降低，这又会导致电流进一步增加。这将产生一种失控效应，灯将跳转到高电流状态（#3）。由于实际的灯并不是设计来承受这么多功率的，这将导致灾难性的故障。同样，异常的电流下降将导致灯熄灭。第二种状态是灯的期望工作状态，因为随着时间的推移，从储液池中缓慢损失合金，对灯的特性的影响比完全蒸发的合金要小。结果是平均灯寿命超过20000小时。",
						"在实际使用中，灯由交流电压源供电，与电感式“镇流器”串联，以向灯提供几乎恒定的电流，而不是恒定的电压，从而确保稳定运行。镇流器通常是电感式的，而不是简单的电阻式的，以最大限度地减少电阻损耗造成的能量浪费。因为灯在交流周期的每个零电流点实际上都会熄灭，所以电感式镇流器通过在零电流点提供电压尖峰来协助重新点燃。",
						"灯发出的光由汞和钠的原子发射线组成，但主要由钠D线发射主导。该线因压力（共振）而极度展宽，并且由于在弧光较冷的外层发生吸收，还发生了自反转，这赋予了灯改进的显色特性。此外，由于弧光中的汞原子的范德华力，D线发射的红翼进一步因压力而展宽。"
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
