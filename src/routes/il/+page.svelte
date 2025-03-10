<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "The Incandescent Lamp",
					subhead1: "Introduction",
					imgs: ["IN GLS Lamp ES_Min.jpg"],
					description1: [
						"The incandescent lamp is the oldest type of electric lamp still in general use. Its practical form was invented simultaneously in 1879 by Sir Joseph Swan in England, and by Thomas Edison in America. Over the past 130 years it has undergone numerous changes in materials and manufacture to bring it to its present performance and convenience as a light source. Fig. I1 illustrates the construction of a typical modern incandescent lamp.",
						"Until recently the incandescent lamp was found in almost every application, and despite the fact that it is the least efficient technology for the conversion of electrical energy into visible light, and the fact that several considerably more efficient retrofit lamp types have been developed, until 2010 the incandescent lamp still accounted for a greater quantity made annually than any other lamp type. Perhaps a testament to the effectiveness, popularity and simplicity of its design in the eyes of the consumer is that no other light source has shown sufficiently strong technical features to be able to truly displace incandescent lighting. For decades the ordinary man has been wlling to pay the price of its low efficacy in order to enjoy its other benefits. In the end it was only by poltical intervetion, by way of the banning of incandescent lamps so as to reduce global energy consumption, that it has been possible to enforce a transition to more energy-efficient light sources. However incandescent technology continues to survive in the form of its slightly more efficient tungsten-halogen relatives."
					],
					subhead2: "Lamp Construction",
					description2: [
						"The coiled-coil tungsten filament is the heart of the lamp, this is where the light is created.  It is supported at two intermediate points by fine molybdenum wires which offer the necessary refractory properties, while also being slightly springy.  The electrical current is carried to the filament by a pair of nickel plated steel lead-in wires, into which the filament tails are clamped.  Each of these wires is welded to a short length of dumet wire, a very special alloy which forms a gas-tight seal between the glass and wire.  The other end of the dumet is welded to a copper plated steel wire which makes the electrical connection to the cap.  In one or both of these outer leads there is a fuse wire section, often glass sleeved and filled with ballotini (minute glass beads), which ensures that the lamp will fail safely at the end of its life.  The lead wires are held in a glass assembly called the stem, through which a smaller glass tube, the exhaust tube is also sealed.  This is kept open at the top of the stem which allows the air to be pumped out of the bulb after sealing.  The cap is affixed to the bulb with a special heat-curing cement, and the copper lead wires pass through eyelets in the end of the cap where they are fluxed and soldered to the brass contact plates.  The terminals are insulated from each other by a special black glass called vitrite, which offers high electrical resistance even at elevated temperatures."
					]
				},
				{
					subhead3: "Lamp Efficacy",
					imgs: ["Lamp Efficacies_Min.jpg"],
					description3: [
						"By comparison with other light sources, incandescent lamps have the lowest luminous efficacy.  Howwever during their 130-years of development, numerous changes in design and materials have taken place to ensure that a gain in performance has occurred every few years up to the 1940's, when all further technical development for general lighting lamps effectively ceased.",
						"The technological progress in terms of luminous efficacy is compared with other light sources in Figure I2 below. Lumens per watt are only one aspect of lamp performance though, and incandescent lamps do have numerous other advantages to offer - principally that they operate directly from the mains supply with no requirement for any transformer or ballast, they offer a perfect colour rendering index of 100, they are bright light sources that are easily dimmable, and their cost is extremely low."
					]
				},
				{
					subhead4: "Cap Nomenclature",
					imgs: ["Cap Nomenclature_Min.png"],
					description4: [
						"Because of the large variety of different cap types a comprehensive system of nomenclature has been developed by the International Electrotechnical Commission. It commences with a single letter to denote the general type of cap, which may be followed by additional letters to denote a sub-category. The second part is a number which denotes the shell diameter (or pin spacing) in millimetres. The third part of the code is a small letter to indicate the number of contact plates (or pins). Special modifications to the basic design may be indicated by a character following a hyphen. These three or four parts are generally sufficient to define the cap as far as the end user is concerned, for compatibility purposes. However to provide a full definition certain other dimensions may be necessary, and these follow a forward slash (such as, for example, the length of the cap). The list of all general lighting cap types is maintained in the international standard IEC 60061."
					]
				},
				{
					subhead5: "Bulb Nomenclature",
					imgs: [
						"IN Glass Bulb Shapes_Min.jpg",
						"Bulb Nomenclature1_Min.png",
						"Bulb Nomenclature2_Min.png"
					],
					description5: [
						`Each glass bulb is classified with a unique code which determines its size and shape. The shape of the bulb is denoted by a letter (or letters), and this is followed by a number which gives the maximum diameter. In most countries of the world the diameter is stated in millimetres. However in the Americas the number represents the maximum diameter in eighths of an inch (e.g. an A19 bulb has a diameter of 19 eighths of an inch, which is 2.375" or 60mm). The imperial measures are sometimes also encountered even in metric countries for certain bulb shapes, particilarly for PAR and MR reflector types, and for fluorescent tubes.`
					]
				},
				{
					subhead6: "Filament Nomenclature",
					imgs: ["IN Filament Mount Shapes_Min.jpg"],
					description6: [
						"There are a number of different filament mounting styles that have become standard over the years. These are not specified in any national or international standards, but a comprehensive system of nomenclature was introduced by General Electric around 1910. It has been adopted by a majority of other lamp manufacturers and thus exists as a kind of industrial standard.",
						"The system consists of a two-part coding. The first letter identifies the type of filament wire employed (S = Straight Wire, C = Single Coil, CC = Coiled Coil, FC = Flat Coil, R = Ribbon, B = Braided). The second part is a number which indicates the shape of the mounted filament, according to the illustrations shown in Figure I4."
					]
				},
				{
					title: "Technology",
					subhead7: "Operating Principle",
					imgs: ["IN Wiens Curves_Min.jpg", "IN Glowing_Min.jpg", "IN GLS Energy_Min.jpg"],
					description7: [
						"The incandescent lamp is based on the principle of temperature radiation - in that objects emit light when they are heated to high temperatures. It is a well known phenomenon observed everyday, for instance from the glow of coals in a fire or the bright yellow radiation of molten steel being cast into a mould. The incandescent body in the modern lamp consists of a fine metallic wire, and it is heated by passing an electric current through it. The friction of the flow of electrons being forced along the narrow wire causes its temperature to be increased, and the higher the electric current the greater the degree of heating.",
						"The filament will begin to glow dimly if heated above about 500°C, but to obtain a useful amount of light it is necessary to operate at temperatures in excess of 2500°C when it glows white hot. The actual temperature attained by the filament is depending on the power, or wattage that it dissipates. The wattage in turn depends on the electrical resistance of the filament wire and the voltage of the electricity supply. Lamps of various ratings are thus made by providing them with filaments having differing electrical resistances.",
						"Figure I6 illustrates the classical Wien's Displacement Law, which reveals the spectral power distribution of filaments heated to various temperatures (shown by the different curves in Kelvins, K). It will be observed that the higher the filament temperature the greater the amount of energy it radiates, represented by the area under each curve.  The dashed line indicates a general trend that the hotter the filament, the further its peak emission wavelength is shifted from the infrared towards the visible region. It will thus be appreciated that the most efficient lamps are those having the highest possible filament operating temperatures.",
						"Most metals are molten at the desired filament operating temperature, and there are very few materials which make suitable lamp filaments. Swan and Edison chose carbon because it has the highest working temperature of any of the known chemical elements – it sublimes at about 3825°C. However its vapour pressure is rather high and before this temperature is reached, it evaporates away rapidly. To reduce the rate of evaporation and obtain satisfactory life performance, carbon must be operated at considerably lower temperatures. Nevertheless it served as the only mass-produced filament material until the introduction of osmium in 1906 (melting point 3033°C) and tantalum in 1907 (melting point 3017°C). Despite having lower melting temperatures, these metals feature much lower vapour pressures than carbon. Consequently for a given rate of filament evaporation, and hence lamp life, they can be operated at higher temperatures than carbon. Owing to the higher temperature they produce more light as already explained with Wien's Displacement Curves. In 1907 lamps having pressed tungsten filaments were introduced, having a melting point of 3417°C and a still lower vapour pressure. Tungsten remains the metal of choice today, but the fragile filaments made from pressed tungsten powder were superseded in 1909 by drawn tungsten wire, which is stronger and easier to handle.",
						"Despite the very high operating temperature that the tungsten filament permits, the efficacy with which it converts electrical energy into visible light remains pitifully low. The energy balance diagram in Figure I7 to the right shows how the energy of a modern 100W GLS lamp is dissipated. Only some 5% is converted into visible light, this representing an efficacy of 13.4 lumens per watt. A massive 83% of the energy is wasted as radiant heat, while the remaining 12% is lost as heat conducted through the base and glass envelope. Indeed, these lamps are better described as very efficient electrical heaters which waste a small amount of their energy in the form of light!"
					]
				},
				{
					subhead8: "Gas Filling Effects",
					imgs: ["IN Cage Lamp BC_Min.jpg", "IN Gas Loss_Min.jpg"],
					description8: [
						"The mains voltage tungsten lamp requires a relatively long filament of very small diameter. A typical modern 240V 100W GLS lamp contains a filament finer than a human hair and a staggering 1152mm in length. In the first tungsten lamps the great length of this filament was accommodated by mounting it in a series of V-form hairpins, strung between two sets of supports at either end of the bulb. This is known as the 'Squirrel Cage' or S-1 filament mount construction, and is illustrated in Figure I8 to the right. The bulb encloses high vacuum as the hot filament is chemically very reactive and would soon oxidise in the presence of air.",
						"As already mentioned, filaments evaporate during their high temperature operation, and this results in the wire becoming thinner over time. Some parts of the filament always evaporate slightly faster than others, for instance due to microscopic defects in the tungsten wire which cannot be manufactured with a perfectly uniform diameter. These thinned regions lead to the formation of hot spots during operation. The higher temperature in the region of the hot spots accelerates the rate of evaporation, which proceeds until the wire either overheats and melts, or it becomes so thin that it can no longer support its own weight. In GLS lamp design it is customary to choose a filament temperature that will deliver an average lifetime of 1000 hours before failure.",
						"It is clearly desirable to find some method of retarding the rate of tungsten evaporation. This would allow lamps of much longer life to be manufactured, but the prospects of creating a more efficient lamp are even more interesting. If evaporation is slowed, it is possible to boost the filament temperature and bring life back down to the 1000 hour level. Hotter filaments generate light more efficiently, as explained on the previous page. Since lamps consume many times their own cost price in electric current over lifetime, high efficacy lamps make better financial sense to the customer than long life versions, in almost every case.",
						"One practical solution is to replace the vacuum in the bulb with an inert gas. The physical pressure of the gas acting on the filament then reduces the tendency for tungsten atoms to boil away from its surface, by exactly the same mechanism as the boiling point of water is increased in a pressure cooker. Unfortunately there is a snag - although the gas is effective in slowing filament evaporation, it of course has a higher thermal conductivity than vacuum. As a result it carries some heat away from the filament due to conduction and convection effects. This is clearly demonstrated in a pair of special squirrel-cage tungsten lamps manufactured by the author at the works of Victory Lighting, London. Both have identical filaments but one is vacuum and the other has an argon/nitrogen gas filling at a pressure of approximately 700 torr.",
						"These are illustrated in Figure I9, the lamp on the left being vacuum and on the right gas-filled. The vacuum lamp lights up brightly whereas the gas-filled version glows only dimly, even though they are both of the same wattage. It's easy to prove that the filament is losing heat to the gas-filling because if the tops of the two bulbs are touched, the glass on the gas-filled one is very much hotter - despite the fact that its filament is visibly so much colder. This often confuses people, but the reason for the colder filament is that the gas is conducting heat away and transferring it to the bulb wall above.",
						"The effect of the gas convection currents is also superbly visualised, because only the upper portion of the filament lights up due to the fact that heat rises. If the lamp is inverted the hot gases move to the other end of the bulb, and the glowing part of the filament also moves. A shimmering effect may be observed due to turbulence currents as the gas flows around the stem.",
						`It is well known that modern incandescent lamps are gas filled, so the problem of heat loss to the gas filling has clearly been solved. The mechanisms of preventing thermal losses to the gas filling are described in detail on the following page under the section "Filament Coiling Effects".`
					]
				}
			],
			viewFullImage: "View Full Image",
			close: "Close",
			returnHome: "Home"
		},
		zh: {
			boxes: [
				{
					title: "白炽灯",
					subhead1: "简介",
					imgs: ["IN GLS Lamp ES_Min.jpg"],
					description1: [
						"白炽灯是最古老的仍在普遍使用的电灯类型。其实用形式于1879年同时由英国的约瑟夫·斯旺爵士和美国的托马斯·爱迪生发明。在过去的130年中，它在材料和制造方面经历了许多变化，以达到其当前作为光源的性能和便利性。图I1展示了一种典型现代白炽灯的构造。",
						"直到最近，白炽灯几乎被用于所有应用场合。尽管它是将电能转化为可见光的效率最低的技术，并且尽管已经开发出几种效率明显更高的替代灯具类型，直到2010年，白炽灯的年产量仍高于其他任何灯具类型。也许这证明了在消费者眼中，其设计的有效性、受欢迎程度和简单性是如此突出，以至于没有其他光源显示出足够强大的技术特点来真正取代白炽灯照明。多年来，普通民众一直愿意为其低效率付出代价，以享受它的其他好处。最终，只有通过政治干预，通过禁止白炽灯以减少全球能源消耗，才有可能强制向更节能的光源过渡。然而，白炽灯技术以略微更高效的钨卤素灯的形式继续存在。"
					],
					subhead2: "灯具构造",
					description2: [
						"卷绕的钨丝是灯具的核心，光就在这里产生。它通过两根细钼丝在两个中间点得到支撑，这些钼丝具有必要的耐火特性，同时又略带弹性。电流通过一对镀镍钢引线导入灯丝，灯丝尾部被夹在这些引线中。这些引线的每一端都焊接有一段特殊的合金——杜美丝，杜美丝能在玻璃和引线之间形成气密密封。杜美丝的另一端焊接在镀铜钢引线上，镀铜钢引线则与灯座相连，完成电气连接。在这些外引线中的一根或两根上，有一个保险丝段，通常套有玻璃套管并填充有玻璃微珠（ballotini），这确保了灯具在其使用寿命结束时能够安全地失效。引线固定在一个称为灯脚的玻璃组件中，一根较小的玻璃管——排气管也密封在灯脚中。排气管在灯脚的顶部保持开口，这使得在密封后可以将空气从灯泡中抽出。灯座通过一种特殊的热固化水泥固定在灯泡上，镀铜引线穿过灯座末端的眼孔，用助焊剂处理后焊接在黄铜接触片上。端子之间由一种特殊的黑色玻璃——维特玻璃（vitrite）绝缘，即使在高温下，维特玻璃也能提供高电阻。"
					]
				},
				{
					subhead3: "灯具光效",
					imgs: ["Lamp Efficacies_Min.jpg"],
					description3: [
						"与其他光源相比，白炽灯的光效最低。然而，在其130年的发展过程中，设计和材料发生了许多变化，确保了其性能每几年就会有所提升，直到20世纪40年代，针对普通照明灯具的进一步技术开发实际上已经停止。",
						"图I2比较了白炽灯与其他光源在光效方面的技术进步。每瓦流明只是灯具性能的一个方面，白炽灯确实还有许多其他优点——主要是它们可以直接从电源供电，无需任何变压器或镇流器，它们提供了完美的显色指数100，它们是易于调光的明亮光源，而且成本极其低。"
					]
				},
				{
					subhead4: "灯座命名",
					imgs: ["Cap Nomenclature_Min.png"],
					description4: [
						"由于灯座的种类繁多，国际电工委员会开发了一套完整的命名系统。它以一个字母开头，表示灯座的一般类型，后面可能跟着额外的字母来表示一个子类别。第二部分是一个数字，表示灯座的外壳直径（或插脚间距）以毫米为单位。代码的第三部分是一个小写字母，用来表示接触片（或插脚）的数量。基本设计的特殊修改可以用一个破折号后的字符来表示。这三到四部分通常足以定义灯座，以满足最终用户在兼容性方面的需要。然而，为了提供完整的定义，可能还需要某些其他尺寸，这些尺寸跟在一个正斜杠后面（例如，灯座的长度）。所有普通照明灯座类型的列表都保留在国际标准IEC 60061中。"
					]
				},
				{
					subhead5: "灯泡命名",
					imgs: [
						"IN Glass Bulb Shapes_Min.jpg",
						"Bulb Nomenclature1_Min.png",
						"Bulb Nomenclature2_Min.png"
					],
					description5: [
						"每个玻璃灯泡都用一个独特的代码来分类，以确定其大小和形状。灯泡的形状用字母（或字母组合）表示，后面跟着一个数字，表示最大直径。在世界上的大多数国家，直径是以毫米为单位表示的。然而，在美洲，这个数字代表最大直径是八分之一英寸的倍数（例如，A19灯泡的直径是19个八分之一英寸，即2.375英寸或60毫米）。在公制国家，对于某些灯泡形状，特别是PAR和MR反射型灯泡，以及荧光灯管，有时也会遇到这种英制单位。"
					]
				},
				{
					subhead6: "灯丝命名",
					imgs: ["IN Filament Mount Shapes_Min.jpg"],
					description6: [
						"多年来，已经形成了几种不同的灯丝安装风格标准。这些风格没有在任何国家或国际标准中规定，但通用电气公司在1910年左右引入了一套完整的命名系统。大多数其他灯具制造商都采用了这种系统，因此它成为了一种工业标准。",
						"该系统由两部分编码组成。第一个字母标识所使用的灯丝线类型（S = 直线，C = 单圈，CC = 双圈，FC = 平圈，R = 带状，B = 编织）。第二部分是一个数字，表示安装后的灯丝形状，如图I4所示的插图。"
					]
				},
				{
					title: "工艺",
					subhead7: "工作原理",
					imgs: ["IN Wiens Curves_Min.jpg", "IN Glowing_Min.jpg", "IN GLS Energy_Min.jpg"],
					description7: [
						"白炽灯基于温度辐射原理——即物体在被加热到高温时会发出光。这是一种众所周知的现象，每天都能观察到，例如炉火中煤炭的发光，或者熔化的钢水在倒入模具时发出的明亮黄色光芒。现代灯具中的发光体是一根细金属丝，通过电流流过它来加热。电子被迫沿着狭窄的导线流动所产生的摩擦使其温度升高，电流越大，加热程度越高。",
						"如果加热到大约500°C以上，灯丝会开始微弱发光，但要获得有用的光量，需要在超过2500°C的温度下工作，此时它会发出白炽光。灯丝实际达到的温度取决于它所消耗的功率，即瓦数。瓦数又取决于灯丝导线的电阻和电源的电压。因此，通过为它们提供具有不同电阻的灯丝，可以制造出各种功率等级的灯具。",
						"图I6展示了经典的维恩位移定律，揭示了被加热到各种温度的灯丝的光谱功率分布（由不同的曲线以开尔文温度K表示）。可以看出，灯丝温度越高，它辐射的能量就越多，由每条曲线下的面积表示。虚线表明了一个普遍趋势，即灯丝温度越高，其峰值发射波长就越从红外区域向可见光区域移动。因此，可以理解为效率最高的灯具是那些具有尽可能高的灯丝工作温度的灯具。",
						"大多数金属在所需的灯丝工作温度下会熔化，只有很少的材料可以作为合适的灯丝。斯旺和爱迪生选择了碳，因为它是所有已知化学元素中工作温度最高的——它在大约3825°C时升华。然而，它的蒸汽压相当高，在达到这个温度之前，它就会迅速蒸发。为了降低蒸发速率并获得令人满意的使用寿命，碳必须在明显较低的温度下工作。尽管如此，它仍然是直到1906年引入锇（熔点3033°C）和1907年引入钽（熔点3017°C）之前唯一的量产灯丝材料。尽管这些金属的熔点较低，但它们的蒸汽压比碳低得多。因此，对于给定的灯丝蒸发速率，以及因此的灯具寿命，它们可以在比碳更高的温度下工作。由于温度更高，它们产生的光更多，这已经通过维恩位移曲线解释过了。1907年，引入了具有压铸钨丝的灯具，其熔点为3417°C，蒸汽压更低。钨至今仍然是首选金属，但从压铸钨粉制成的易碎灯丝在1909年被拉制钨丝取代，后者更强韧，更易于操作。",
						"尽管钨丝允许的极高工作温度，其将电能转化为可见光的效率仍然低得可怜。图I7右侧的能量平衡图显示了现代100W普通照明灯的能量是如何耗散的。只有大约5%的能量转化为可见光，这相当于每瓦13.4流明的光效。高达83%的能量以辐射热的形式浪费掉，而剩余的12%则以通过灯座和玻璃外壳传导的热量形式散失。事实上，这些灯具更像是高效的电加热器，只是浪费了少量能量以光的形式散发出去！"
					]
				},
				{
					subhead8: "充气效果",
					imgs: ["IN Cage Lamp BC_Min.jpg", "IN Gas Loss_Min.jpg"],
					description8: [
						"主电源电压的白炽灯需要一根相对较长且直径非常小的灯丝。典型的现代240V、100W普通照明灯的灯丝比人的头发还细，长度却达到了惊人的1152毫米。在最初的白炽灯中，灯丝的这种巨大长度是通过将其安装成一系列V形发夹来容纳的，这些发夹连接在灯泡两端的两组支撑之间。这种结构被称为“松鼠笼”或S-1灯丝安装结构，如右侧的图I8所示。灯泡内是高真空环境，因为高温下的灯丝在化学上非常活泼，如果暴露在空气中，很快就会被氧化。",
						"正如前面提到的，灯丝在高温工作时会蒸发，这导致灯丝逐渐变细。灯丝的某些部分总是比其他部分蒸发得稍快一些，例如由于钨丝存在微观缺陷，而钨丝无法制造出完全均匀的直径。这些变薄的区域会导致在工作时形成热点。热点区域的温度更高，这加速了蒸发速率，直到灯丝过热熔化，或者变得如此之细，以至于无法支撑自身的重量。在普通照明灯的设计中，通常选择一种灯丝温度，使其平均寿命达到1000小时。",
						"显然，找到一种减缓钨蒸发速率的方法是很有必要的。这不仅可以制造出寿命更长的灯泡，而且制造出更高效灯泡的可能性更加令人感兴趣。如果减缓了蒸发，就可以提高灯丝温度，并将寿命重新降低到1000小时的水平。更热的灯丝产生光的效率更高，这在前面的页面中已经解释过了。由于灯泡在其使用寿命内消耗的电流成本是其自身成本的许多倍，因此高效率的灯泡在几乎所有情况下都比长寿命版本对客户更有经济意义。",
						"一个实际的解决方案是用惰性气体替换灯泡内的真空。气体对灯丝施加的物理压力可以减少钨原子从其表面蒸发的倾向，其原理与压力锅中水的沸点升高完全相同。不幸的是，有一个问题——尽管气体在减缓灯丝蒸发方面是有效的，但它的导热性当然比真空高。因此，由于传导和对流效应，它会从灯丝带走一些热量。这一点在作者在伦敦胜利照明公司制造的两盏特殊的松鼠笼式白炽灯中得到了清晰的展示。这两盏灯的灯丝完全相同，但一盏是真空的，另一盏充有大约700托的压力的氩气/氮气混合气体。",
						"这些灯如图I9所示，左边的是真空灯，右边的是充气灯。真空灯亮得很亮，而充气灯却只发出微弱的光，尽管它们的功率相同。很容易证明灯丝正在向气体充气散热，因为如果触摸两个灯泡的顶部，充气的那个玻璃会明显更热——尽管它的灯丝看起来明显更冷。这常常让人们感到困惑，但灯丝更冷的原因是气体正在传导热量，并将其传递到灯泡上方的壁上。",
						"气体对流的效果也得到了极好的可视化，因为只有灯丝的上部会发光，这是由于热量上升。如果将灯倒置，热气体会移动到灯泡的另一端，灯丝发光的部分也会随之移动。由于气体在灯脚周围流动时产生的湍流，可能会观察到闪烁的效果。",
						"众所周知，现代白炽灯是充气的，因此气体充气导致的热量损失问题显然已经得到了解决。关于防止热量损失到气体充气的机制将在下一页的“灯丝卷绕效果”部分中详细描述。"
					]
				}
			],
			viewFullImage: "查看原图",
			close: "退出",
			returnHome: "首页"
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
