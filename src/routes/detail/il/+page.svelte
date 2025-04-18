<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "The Incandescent Lamp",
					subhead: "Introduction",
					imgs: ["/IN GLS Lamp ES_Min.jpg", "/Lamp Efficacies_Min.jpg"],
					description: [
						"The incandescent lamp is the oldest type of electric lamp still in general use. Its practical form was invented simultaneously in 1879 by Sir Joseph Swan in England, and by Thomas Edison in America. Over the past 130 years it has undergone numerous changes in materials and manufacture to bring it to its present performance and convenience as a light source. Fig. I1 illustrates the construction of a typical modern incandescent lamp.",
						"Until recently the incandescent lamp was found in almost every application, and despite the fact that it is the least efficient technology for the conversion of electrical energy into visible light, and the fact that several considerably more efficient retrofit lamp types have been developed, until 2010 the incandescent lamp still accounted for a greater quantity made annually than any other lamp type. Perhaps a testament to the effectiveness, popularity and simplicity of its design in the eyes of the consumer is that no other light source has shown sufficiently strong technical features to be able to truly displace incandescent lighting. For decades the ordinary man has been wlling to pay the price of its low efficacy in order to enjoy its other benefits. In the end it was only by poltical intervetion, by way of the banning of incandescent lamps so as to reduce global energy consumption, that it has been possible to enforce a transition to more energy-efficient light sources. However incandescent technology continues to survive in the form of its slightly more efficient tungsten-halogen relatives.",
						"The coiled-coil tungsten filament is the heart of the lamp, this is where the light is created.  It is supported at two intermediate points by fine molybdenum wires which offer the necessary refractory properties, while also being slightly springy.  The electrical current is carried to the filament by a pair of nickel plated steel lead-in wires, into which the filament tails are clamped.  Each of these wires is welded to a short length of dumet wire, a very special alloy which forms a gas-tight seal between the glass and wire.  The other end of the dumet is welded to a copper plated steel wire which makes the electrical connection to the cap.  In one or both of these outer leads there is a fuse wire section, often glass sleeved and filled with ballotini (minute glass beads), which ensures that the lamp will fail safely at the end of its life.  The lead wires are held in a glass assembly called the stem, through which a smaller glass tube, the exhaust tube is also sealed.  This is kept open at the top of the stem which allows the air to be pumped out of the bulb after sealing.  The cap is affixed to the bulb with a special heat-curing cement, and the copper lead wires pass through eyelets in the end of the cap where they are fluxed and soldered to the brass contact plates.  The terminals are insulated from each other by a special black glass called vitrite, which offers high electrical resistance even at elevated temperatures.",
						"By comparison with other light sources, incandescent lamps have the lowest luminous efficacy.  Howwever during their 130-years of development, numerous changes in design and materials have taken place to ensure that a gain in performance has occurred every few years up to the 1940's, when all further technical development for general lighting lamps effectively ceased.",
						"The technological progress in terms of luminous efficacy is compared with other light sources in Figure I2 below. Lumens per watt are only one aspect of lamp performance though, and incandescent lamps do have numerous other advantages to offer - principally that they operate directly from the mains supply with no requirement for any transformer or ballast, they offer a perfect colour rendering index of 100, they are bright light sources that are easily dimmable, and their cost is extremely low."
					]
				},
				{
					subhead: "Cap Nomenclature",
					imgs: ["/Cap Nomenclature_Min.png"],
					description: [
						"Because of the large variety of different cap types a comprehensive system of nomenclature has been developed by the International Electrotechnical Commission. It commences with a single letter to denote the general type of cap, which may be followed by additional letters to denote a sub-category. The second part is a number which denotes the shell diameter (or pin spacing) in millimetres. The third part of the code is a small letter to indicate the number of contact plates (or pins). Special modifications to the basic design may be indicated by a character following a hyphen. These three or four parts are generally sufficient to define the cap as far as the end user is concerned, for compatibility purposes. However to provide a full definition certain other dimensions may be necessary, and these follow a forward slash (such as, for example, the length of the cap). The list of all general lighting cap types is maintained in the international standard IEC 60061."
					]
				},
				{
					subhead: "Bulb Nomenclature",
					imgs: [
						"/IN Glass Bulb Shapes_Min.jpg",
						"/Bulb Nomenclature1_Min.png",
						"/Bulb Nomenclature2_Min.png"
					],
					description: [
						`Each glass bulb is classified with a unique code which determines its size and shape. The shape of the bulb is denoted by a letter (or letters), and this is followed by a number which gives the maximum diameter. In most countries of the world the diameter is stated in millimetres. However in the Americas the number represents the maximum diameter in eighths of an inch (e.g. an A19 bulb has a diameter of 19 eighths of an inch, which is 2.375" or 60mm). The imperial measures are sometimes also encountered even in metric countries for certain bulb shapes, particilarly for PAR and MR reflector types, and for fluorescent tubes.`
					]
				},
				{
					subhead: "Filament Nomenclature",
					imgs: ["/IN Filament Mount Shapes_Min.jpg"],
					description: [
						"There are a number of different filament mounting styles that have become standard over the years. These are not specified in any national or international standards, but a comprehensive system of nomenclature was introduced by General Electric around 1910. It has been adopted by a majority of other lamp manufacturers and thus exists as a kind of industrial standard.",
						"The system consists of a two-part coding. The first letter identifies the type of filament wire employed (S = Straight Wire, C = Single Coil, CC = Coiled Coil, FC = Flat Coil, R = Ribbon, B = Braided). The second part is a number which indicates the shape of the mounted filament, according to the illustrations shown in Figure I4."
					]
				},
				{
					title: "Technology",
					subhead: "Operating Principle",
					imgs: ["/IN Wiens Curves_Min.jpg", "/IN Glowing_Min.jpg", "/IN GLS Energy_Min.jpg"],
					description: [
						"The incandescent lamp is based on the principle of temperature radiation - in that objects emit light when they are heated to high temperatures. It is a well known phenomenon observed everyday, for instance from the glow of coals in a fire or the bright yellow radiation of molten steel being cast into a mould. The incandescent body in the modern lamp consists of a fine metallic wire, and it is heated by passing an electric current through it. The friction of the flow of electrons being forced along the narrow wire causes its temperature to be increased, and the higher the electric current the greater the degree of heating.",
						"The filament will begin to glow dimly if heated above about 500°C, but to obtain a useful amount of light it is necessary to operate at temperatures in excess of 2500°C when it glows white hot. The actual temperature attained by the filament is depending on the power, or wattage that it dissipates. The wattage in turn depends on the electrical resistance of the filament wire and the voltage of the electricity supply. Lamps of various ratings are thus made by providing them with filaments having differing electrical resistances.",
						"Figure I6 illustrates the classical Wien's Displacement Law, which reveals the spectral power distribution of filaments heated to various temperatures (shown by the different curves in Kelvins, K). It will be observed that the higher the filament temperature the greater the amount of energy it radiates, represented by the area under each curve.  The dashed line indicates a general trend that the hotter the filament, the further its peak emission wavelength is shifted from the infrared towards the visible region. It will thus be appreciated that the most efficient lamps are those having the highest possible filament operating temperatures.",
						"Most metals are molten at the desired filament operating temperature, and there are very few materials which make suitable lamp filaments. Swan and Edison chose carbon because it has the highest working temperature of any of the known chemical elements – it sublimes at about 3825°C. However its vapour pressure is rather high and before this temperature is reached, it evaporates away rapidly. To reduce the rate of evaporation and obtain satisfactory life performance, carbon must be operated at considerably lower temperatures. Nevertheless it served as the only mass-produced filament material until the introduction of osmium in 1906 (melting point 3033°C) and tantalum in 1907 (melting point 3017°C). Despite having lower melting temperatures, these metals feature much lower vapour pressures than carbon. Consequently for a given rate of filament evaporation, and hence lamp life, they can be operated at higher temperatures than carbon. Owing to the higher temperature they produce more light as already explained with Wien's Displacement Curves. In 1907 lamps having pressed tungsten filaments were introduced, having a melting point of 3417°C and a still lower vapour pressure. Tungsten remains the metal of choice today, but the fragile filaments made from pressed tungsten powder were superseded in 1909 by drawn tungsten wire, which is stronger and easier to handle.",
						"Despite the very high operating temperature that the tungsten filament permits, the efficacy with which it converts electrical energy into visible light remains pitifully low. The energy balance diagram in Figure I7 to the right shows how the energy of a modern 100W GLS lamp is dissipated. Only some 5% is converted into visible light, this representing an efficacy of 13.4 lumens per watt. A massive 83% of the energy is wasted as radiant heat, while the remaining 12% is lost as heat conducted through the base and glass envelope. Indeed, these lamps are better described as very efficient electrical heaters which waste a small amount of their energy in the form of light!"
					]
				},
				{
					subhead: "Gas Filling Effects",
					imgs: ["/IN Cage Lamp BC_Min.jpg", "/IN Gas Loss_Min.jpg"],
					description: [
						"The mains voltage tungsten lamp requires a relatively long filament of very small diameter. A typical modern 240V 100W GLS lamp contains a filament finer than a human hair and a staggering 1152mm in length. In the first tungsten lamps the great length of this filament was accommodated by mounting it in a series of V-form hairpins, strung between two sets of supports at either end of the bulb. This is known as the 'Squirrel Cage' or S-1 filament mount construction, and is illustrated in Figure I8 to the right. The bulb encloses high vacuum as the hot filament is chemically very reactive and would soon oxidise in the presence of air.",
						"As already mentioned, filaments evaporate during their high temperature operation, and this results in the wire becoming thinner over time. Some parts of the filament always evaporate slightly faster than others, for instance due to microscopic defects in the tungsten wire which cannot be manufactured with a perfectly uniform diameter. These thinned regions lead to the formation of hot spots during operation. The higher temperature in the region of the hot spots accelerates the rate of evaporation, which proceeds until the wire either overheats and melts, or it becomes so thin that it can no longer support its own weight. In GLS lamp design it is customary to choose a filament temperature that will deliver an average lifetime of 1000 hours before failure.",
						"It is clearly desirable to find some method of retarding the rate of tungsten evaporation. This would allow lamps of much longer life to be manufactured, but the prospects of creating a more efficient lamp are even more interesting. If evaporation is slowed, it is possible to boost the filament temperature and bring life back down to the 1000 hour level. Hotter filaments generate light more efficiently, as explained on the previous page. Since lamps consume many times their own cost price in electric current over lifetime, high efficacy lamps make better financial sense to the customer than long life versions, in almost every case.",
						"One practical solution is to replace the vacuum in the bulb with an inert gas. The physical pressure of the gas acting on the filament then reduces the tendency for tungsten atoms to boil away from its surface, by exactly the same mechanism as the boiling point of water is increased in a pressure cooker. Unfortunately there is a snag - although the gas is effective in slowing filament evaporation, it of course has a higher thermal conductivity than vacuum. As a result it carries some heat away from the filament due to conduction and convection effects. This is clearly demonstrated in a pair of special squirrel-cage tungsten lamps manufactured by the author at the works of Victory Lighting, London. Both have identical filaments but one is vacuum and the other has an argon/nitrogen gas filling at a pressure of approximately 700 torr.",
						"These are illustrated in Figure I9, the lamp on the left being vacuum and on the right gas-filled. The vacuum lamp lights up brightly whereas the gas-filled version glows only dimly, even though they are both of the same wattage. It's easy to prove that the filament is losing heat to the gas-filling because if the tops of the two bulbs are touched, the glass on the gas-filled one is very much hotter - despite the fact that its filament is visibly so much colder. This often confuses people, but the reason for the colder filament is that the gas is conducting heat away and transferring it to the bulb wall above.",
						"The effect of the gas convection currents is also superbly visualised, because only the upper portion of the filament lights up due to the fact that heat rises. If the lamp is inverted the hot gases move to the other end of the bulb, and the glowing part of the filament also moves. A shimmering effect may be observed due to turbulence currents as the gas flows around the stem.",
						`It is well known that modern incandescent lamps are gas filled, so the problem of heat loss to the gas filling has clearly been solved. The mechanisms of preventing thermal losses to the gas filling are described in detail on the following page under the section "Filament Coiling Effects".`
					]
				},
				{
					subhead: "Filament Coiling Effects",
					imgs: [
						"/IN GLS Convection_Min.jpg",
						"/IN%20C-9%20Lamp%20BC_Min.jpg",
						"/IN%20CC%20Lamp%201924_Min.jpg",
						"/IN%20Langmuir%20Sheath_Min.jpg",
						"/TH%20Triple%20Coil_Min.jpg"
					],
					description: [
						"Although coiled filaments do still lose some heat to the gas by conduction and convection, for the vast majority of lamps the heat loss is reduced so tremendously that the benefits of reduced filament evaporation and hotter operation outweigh the remaining energy loss.  However it is important not to forget the importance of filament geometry and its desired operating temperature when designing a gas-filled lamp.",
						"A typical single coil gas-filled lamp is illustrated in Figure I11.  The coil is mounted in horizontal ring, known as the C-9 Wreath configuration, so that the cooling effect of the gas is the same over its entire length when the lamp is operated in the most common vertical position.  If it was mounted axially as with the earlier vacuum lamps, then given the long length of a typical single coil filament, the upper end would run hotter because hot gas rises upwards, and the temperature gradient would cause the top of the filament burn out prematurely.  See Figure I9 on the previous page for a visualisation of this effect. This is partly why ordinary single coil incandescent lamps deliver the longest life and best performance when they are operated vertically cap-up or cap-down, because then no part of the filament is overheated by convection currents.\n\t\tThe introduction of coiled filaments simplified production - owing to its reduced length a number of support wires could be eliminated, and the bulb volume was reduced.  Thus it brought not only a performance improvement, but also a cost reduction.",
						"The first experimental general service lamp to employ a coiled-coil filament is illustrated in Figure I12.  This was developed in 1924 at the Hirst Research Laboratory of the Osram-GEC Wembley Works in London.  It is believed to be a high voltage GLS lamp of approximately 100W rating.  But there were still many technical difficulties which delayed the market launch for almost another decade, until 1933 in Britain and Europe, and 1936 in America.",
						"The effects of coiling and heat losses to the gas filling are visualised in the demonstration lamp of Figure I13, made by the author at the works of GE Lighting, Leicester.  The filament is an ordinary 240V 60W coiled-coil type, but part of it has been stretched out to a single coil, and the remaining portion completely unwound to a straight wire.  The entire filament is made from the same piece of tungsten wire, all the same diameter.  The bulb is filled with the standard 85:15 Argon:Nitrogen mixture.  When switched on at quite a low voltage, the coiled-coil lights up brightly.  As current is increased the single coil begins to glow, but even at 240V the straight wire produces no light at all.",
						"In recent years there has been some activity to develop a triple coil filament, and such a product has been commercialised in Japan by Toshiba.  This offers no significant increase in luminous efficacy, but coil dimensions are reduced such that it approaches a point-source, and outstanding optical control can be attained in small reflectors.  Controlling the degree of filament sag by modification of the tungsten metallurgy was a key challenge that had to be overcome, while in parallel limiting the concentration of potassium dopant in the tungsten wire to avoid problems of arcing due to the unusually high voltage gradient between adjacent coils."
					]
				},
				{
					subhead: "Vacuum vs Gas Filled Lamps",
					imgs: ["/IN%20Vac-GF_Min.jpg"],
					description: [
						"There are some lamp types for which gas filling may actually reduce performance, or offers no advantage at all.  For example in very low wattage lamps, the filament is so fine that even when coiled it is still quite thin and has a large surface area to volume ratio, thus heat losses to the gas will always remain high.  It is not possible to coil such thin wires around a larger diameter mandrel and correct this surface area to volume ratio, due to practical constraints in relation to the dimensional stability of such coils.  When the mandrel ratio is too great the filament will suffer sag problems.\n\t\tConsequently an assessment must be made as to whether or not a given lamp design will actually benefit from being gas-filled or not, and in most cases the low wattage versions are produced as vacuum types.  The filament is still coiled, but this is done purely to reduce its length and to make the filament easier to mount on the stem assembly.  Even coiled-coil vacuum types are in existence for the same reasons.  Naturally in vacuum the coiling has no effect whatsoever, since there is no gas flow around the filament and no heat loss to the internal atmosphere.",
						"Because tungsten evaporation is unrestrained in vacuum lamps, the filament must be run at a lower temperature of around 2100°C so that the standard life of 1000 hours can be maintained.  Vacuum lamps are thus less efficient than gas-filled types.  In practical terms, the changeover point at which it makes sense to switch from gas-filled to vacuum types occurs at about 25 Watts.  For miniature lamps, whose filaments are made from thicker wire on account of the low voltage operation, the changeover is at about 3 Watts.\n\t\tIncandescent striplights are also vacuum types, even in the larger ratings of 150W.  This is simply because the filament must extend over the whole length of the luminous tube and therefore cannot be tightly coiled.  If such lamps were gas filled the heat losses over such a long filament would be very high.  It is clear from the photograph in Figure I13 that the most efficient coils in a gas filling are those which are tightly coiled, and the filaments in striplight lamps are so long that they can never be efficient in a gas atmosphere.\n\t\tMany single ended tubular lamps also require long filaments, and these must be vacuum types as well.  If the filament is long and it is intended for vertical burning, the problem of gas convection currents will return.  The hot gases will rise to the upper end of the bulb, overheating one end of the filament and leading to premature failure.\n\t\tBefore coming to a final decision about whether a particular lamp design should be gas-filled or vacuum to deliver optimum performance, consideration must also be given to the application.  One of the principal applications of coloured GLS lamps is in festive outdoor illumination, and these are also made with vacuum atmosphere even for wattages that would generally be gas-filled.  It has already been seen that the bulb wall temperature is much higher for gas-filled lamps, due to the conduction and convection of heat from the filament to the bulb wall.  When coupled with coloured coatings still more heat is absorbed at the bulb wall, and its temperature can become very high.  Since these lamps are used outdoors, incident rain or snow will be encountered and it is likely to lead to thermal shock of the bulb envelope with the consequence of glass cracks.  Such lamps must therefore be made with vacuum simply in order to keep the glass sufficiently cool."
					]
				},
				{
					subhead: "Choice of Gas Type",
					imgs: ["/Choice of Gas Type1_Min.png", "/Choice of Gas Type2_Min.png"],
					description: [
						"Gases used for filling incandescent lamps must be chemically inert, i.e. they should not react with the hot filament (with the exception of halogen lamps).  This means that they also need to be extremely pure, as very small amounts of some substances can have disastrous effects.  For example, a single drop of water in a gas cylinder capable of filling half a million GLS lamps would cause every one of those lamps to blacken and fail early!  The following table shows the gases that are inert to tungsten and make suitable fillings:",
						"The molecular weight is the weight of one atom or molecule of the gas.  The heavier atoms are more effective in reducing filament evaporation, making the lamp last longer.  It can be seen that they also feature lower thermal conductivity, reducing gas losses so the filament will run hotter and produce light more efficiently.\n\t\tConsequently for incandescent lamps it would appear that xenon would be the best choice of fill gas.  But this is only present in very small quantities in the atmosphere, which makes it expensive.  Krypton is about ten times cheaper but still too scarce, so we generally use argon which is roughly 500 times cheaper.  However the first gas-filled lamps had to use nitrogen, because at the turn of the century there were no argon distillation factories in existence.  When argon lamps were eventually introduced, it was found that its lower electrical ionisation potential resulted in problems of arcing between the lead wires.  This was overcome by the admixture of a small amount of nitrogen, and an 85:15 argon:nitrogen mixture is common in European lamps.  Lower voltage American lamps can get away with a 95:5 gas and thus are slightly more efficient.  The fill pressure is about 0.8 atmospheres which normally rises to just above atmospheric pressure when the lamp is in operation.\n\t\tBy the 1930s the price of krypton had reduced considerably as new distillation plants were opened, and in 1936 Tungsram of Hungary put the first krypton-filled GLS lamp on the market.  To reduce the required volume of this expensive gas, a new glass bulb shape was designed.  The result was a lamp having a mushroom shaped envelope, which is still produced today.  The Krypton Mushroom lamps usually offer a combination of about 5% more light and 50% longer life than ordinary argon-filled bulbs.  Alternatively an energy-saving range of lamps producing the same light but with 10% lower wattage is available.  It is also standard practice to employ krypton in high efficiency miniature lamps, because the benefits of krypton are much more pronounced for lower voltage types.  Miners' cap lamps are an important application, since a smaller battery can provide the same light level.  Even xenon is sometimes found in today's miniature halogen capsules where a very high efficacy or long life is called for, especially in automotive and projection lamps.\n\t\tThe only other gas which has been commercially employed in incandescent lamps is hydrogen.  It is characterised by a very high thermal conductivity making it inefficient for general lighting, but it has been employed in special signal lamps because it cools the filament more rapidly between pulses.  The faster nigrescence time permits higher speed signalling by light pulses.  The table below shows the main applications of the available lamp filling gases:"
					]
				},
				{
					subhead: "Getters",
					description: [
						"During the exhausting process in which the lamp is evacuated and perhaps also gas-filled, it is impossible to remove all traces of air even with high speed vacuum pumping equipment.  Additionally small amounts of air and moisture will adhere to internal glass and metal components, and if nothing was done to remove these, the lamp would have an unacceptably short and inefficient life.  It is for this reason that a special chemical called the GETTER is included inside every lamp.  A getter is a chemical which will remove specific impurities form the lamp atmosphere both to assist in the achievement of vacuum during manufacture, and to maintain purity during lamp life.",
						"One of the most damaging phenomena to plague the incandescent lamp is the water cycle.  This will occur if there is insufficient getter to remove all remaining moisture inside the bulb.  When the filament is lighted the high temperature breaks the water vapour down into hydrogen and oxygen. The free oxygen then reacts with the hot filament to produce tungsten oxide. The tungsten oxide has a low vapour pressure and boils off the surface of the filament, then being deposited on the cooler bulb wall or the filament support wires.  It is then reduced by the hydrogen which was freed when the water decomposed.  Effectively, the hydrogen takes the oxygen back from the tungsten, producing water again. The tungsten metal remains as a dark film over internal components, and the water can go back to the filament and attack it again.  The water cycle causes rapid darkening of incandescent lamp bulbs, and when enough of the filament has been removed it will burn out causing premature failure.",
						"Red phosphorus was the first getter, introduced by Malignani in 1893 to remove oxygen and water vapour from the lamps made in his Italian laboratory.  Today it helps to combat the water cycle, a chemical process which destroys the filaments of poorly processed incandescent lamps (see below).  Immediately before sealing into the bulb, the filament is dipped into or sprayed with getter suspended in an organic solvent.\n\t\tWhen the filament is first lighted, the phosphorus is evaporated and reacts with any residual oxygen while it is travelling away from the filament.  This forms phosphorus pentoxide, sometimes seen as a ginger coating on the glass bulb.  This chemical is hydroscopic and goes on to remove water vapour.  The getter is only active for the first few minutes after the initial light up.  It is not an especially good getter, but is very cheap and is adequate for GLS lamps which are processed well.  Many inferior manufacturers still have to rely on additional getters to make up for poorly controlled stem making, mounting and exhausting operations.\n\t\tIf the getter is added in excess (or lamps of unusually high purity are made, such that not all of the phosphorus pentoxide is consumed) then a ginger coating will appear on the bulb wall.  This is especially problematic in miniature lamps since it absorbs a significant proportion of the already small light output.  Cryolite is often added to the phosphorus mixture for vacuum and miniature lamps, and its reaction with the getter produces a coating that is much more transparent, but still just as effective.\n\t\tRed phosphorus cannot always stand the high temperatures encountered on Sealex machines, and its alcohol solvent can also carry water into the lamp.  Thus today, it has been largely superseded by the new series of Phosphorus Pentanitrile (P3N5) getters, which are more stable and are based on amyl acetate solvent.  They are also less flammable, and reduce the occurrence of spontaneous fires on the lampmaking machinery that can sometimes erupt from old deposits of dried-out red phosphorus getter.\n\t\tLastly, in the case of some high value GLS lamps a second getter may be employed.  This consists of zirconium-aluminium paint which is applied to the lead wires, or some other component which will operate at about 400-500°C.  It forms an effective hydrogen getter which further helps to fight the water cycle.  It is often required for inside white-coated lamps.  The surface area of the powder particles can be as much as 2000 square metres in a typical GLS lamp, and this is very difficult to thoroughly outgas on high speed lines."
					]
				},
				{
					subhead: "Effect of Burning Position",
					imgs: ["/IN%20Blackening_Min.jpg"],
					description: [
						"GLS lamps are designed to be burned in the pendant position, with the cap upwards.  When operated horizontally, gas convection currents cause local overheating of the upper portion of filament and this can have an adverse effect on life.  In the pendant position, the filament also lies in the single-wire part of the pigtail loop in the supports.  When operated in other positions, the filament may fall to the opposite side of the support loop where there are sometimes two parallel wires, and this can cause short-circuiting of filament coils with a subsequent reduction in life  - particularly for the C-9 flat-wreath design in Figure I10.  Short-circuiting of turns is less likely for the CC-9 pendant wreath design in Figure I1 where support wires are inclined at an angle to the filament.\n\tThe traditional pear-shaped glass bulb envelope is the result of many decades of scientific development, to realise a bulb shape which provides the longest lifetime and highest lumen maintenance.  The fundamental shape provides adequate cooling of the heated gas without raising the temperature of the glass or cap cement beyond safe working limits.  High wattage lamps may incorporate a metal or mica heat shield in the neck area to block the rise of hot gases, and keep the cap temperature within limits.\n\tDuring operation tungsten is continuously evaporated from the filament and this is carried upwards by the hot gas and deposited on the bulb wall.  In the pendant position the tungsten is deposited inside the neck area, where it has very little effect on the light output.  Lumen outputs are always quoted for lamps burned in this orientation.  For lamps operated cap down or horizontally, the evaporated material will darken the part of the bulb which is vertically above the filament and this can absorb considerable amounts of light.  The area of blackening is illustrated in Figure I16.",
						"In recent years there has been a trend to reduce the size of the standard 60mm GLS lamps to smaller 55 or 50mm diameter bulbs.  Although this results in a smaller size with reduced packaging and transportation costs, it comes with the penalty of accelerated lumen depreciation because the evaporated tungsten is deposited over a smaller area, and forms a darker light-absorbing coating.\n\t\tIn vacuum type lamps there are no gas convection currents, and the glass bulb will darken over its entire surface, regardless of operating position.  It will also blacken much more rapidly because there is no gas filling to reduce the rate of filament evaporation.  However vacuum lamps are still intended primarily for pendant use because of the formation of the filament support wires.\n\t\tMany commercial and domestic lighting fittings are designed to operate lamps upside down or sideways, mainly for compactness or aesthetic reasons.  In these applications the slight reduction in lamp life and performance is considered to be acceptable and outweighed by the other advantages.  The worst situation is to operate the candle and golfball-size lamps in the horizontal position because they are so small that the light output depreciates more rapidly, and the gas does not have sufficient circulation volume to be fully cooled.  The bulb frequently also bears an internal decorative coating, which will release gaseous impurities when overheated.  In such applications these lamps may achieve as little as half the rated lifetime."
					]
				},
				{
					subhead: "Voltage Variation Effects",
					imgs: ["/IN%20Nomograph_Min.jpg"],
					description: [
						"Within the normal range of supply voltage variations the light output will change by about 3.5% for a 1% change of voltage.  The effect of voltage on life is much more pronounced; 5% over-voltage will roughly halve the lamp life, whereas 5% under-voltage will approximately double it.  If it is found that lamps are consistently failing prematurely then the first thing to investigate is the agreement between the voltage marked on the lamp, and the actual voltage at the supply terminals.  In certain cases, it might seem attractive to operate 240V lamps on a 230V circuit to secure the increased lamp life, until it is realised that in doing so the light output will fall considerably more than the corresponding reduction in electricity consumption.\n\tIt is generally unwise to operate a lamp at anything other than its design voltage, but there are some exceptions.  For instance under-volting can be justified for aircraft obstruction lights at the top of a tower where the cost of replacement is very high.  By contrast, over-volting is regularly practised in studio lighting, where the extra light output permits fewer projectors on simpler mounting structures, and this is a worthwhile exchange for renewing lamps before each filming session rather than after, say, a year of service.\n\tThe nomograph in Figure I17 shows the relation between supply voltage variation and the performance of gas-filled incandescent lamps.  It applies only approximately to vacuum lamps and to tungsten-halogen types."
					]
				},
				{
					subhead: "Starting Characteristics",
					imgs: ["/IN%20Inrush_Min.jpg"],
					description: [
						"All lamps based on incandescent technology produce light immediately after switch-on.  The delay is of the order of a few thousandths of a second for the standard sizes, whereas high wattage types may take up to a maximum of about one second to heat their filaments to the full operating temperature.\n\t\tWhen normally alight, the lamp's electrical resistance in ohms is given by the voltage squared, divided by the watts.  But before the lamp is switched on the cold filament has a very much lower electrical resistance.  Due to the low cold resistance a very large current will flow at the instant of switching on, typically around 14 times the normal current.  As the filament warms up, its resistance increases and the current falls until the two stabilise.  Typical inrush current curves are illustrated in Figure I18 below.  For a low wattage lamp such as the 230V 100W rating, it closely approaches the nominal current within about 0.05 seconds.  For higher wattage lamps the process can take much longer.  In the case of the 240V 500W lamp illustrated, even after 1 second its current has not fallen to the nominal level.  Full stability is reached only once the filament as well as its lead-in wires have reached their normal operating temperature - a process which may take several minutes.",
						"The inrush current does not persist for sufficient time to cause most ordinary fuses or circuit breakers to operate, and it has generally been ignored by switch manufacturers since a switch is more likely to fail when breaking a circuit rather than making it.  However, in practice it may be found that some short-break designs do not stand up to the current surges associated with repeated switching, especially in the case of high wattage lamps such as used for projection and studio applications.\n\t\tIt is a fallacy that it is more economical to leave an incandescent lamp continuously burning than to switch it off for just a short period, so as to minimise energy consumption during the inrush current period.  The cost of electricity consumed during the very short time interval of the surge cannot possibly be as much as the cost of current saved by switching the lamp off even for a few seconds.\n\t\tIn addition it is found that the effect of repeated switching has very little effect on the life of a filament lamp.  A good example is found in the flashing roadway Belisha Beacons of British pedestrian crossings.  The filament is switched 'off' to black-heat in between flashes, and ordinary household GLS lamps still achieve the full rated life of 1000 hours in this application (in which they must endure more than 1.5 million flashes)."
					]
				},
				{
					subhead: "Lamp Life",
					imgs: ["/IN%20Life%20Survival_Min.jpg"],
					description: [
						"The nominal life of all European GLS lamps has been standardised at 1000 hours, almost since their introduction.  On numerous occasions queries have arisen as to whether this really is the most economic life, but such are the variations in users' requirements and in the prices they pay for electricity and lamps that there can be no universal optimum life which will suit everybody.\n\t\tIncandescent lamps are manufactured according to British Standard BS 161 (IEC 60064), and the committee responsible for this includes representatives from a wide cross-section of interests such as government departments, professional institutions, organisations representing large users, electrical contractors and the lighting industry.  They review all the factors involved such as lamp cost, electricity cost, cost of replacing a lamp, lamp efficiencies at different rated lives etc. and on each occasion they have concluded that the long established life of 1000 hours should remain the standard rating.  In fact to minimise customer complaints, the standard filament with a declared life of 1000 hours typically has an average design life of 1200 hours.\n\t\tRigid control of the lamp manufacturing processes has lead to great uniformity in the lives of individual lamps, but absolute uniformity is unattainable.  For example if one hundred similar lamps were all put on test under identical conditions, they would not simply run for 1000 hours and then all fail simultaneously.  Instead lamp lives are expressed in the form of a Survival Curve, shown in Figure I19 below.  For incandescent lamps it is customary to state the rated life as being when 70% of the sample is still burning.",
						"In some installations where the cost of lamp replacement is particularly high, for example above a staircase, in a traffic signal or some other difficult location, it is beneficial to the user to have a lamp life of greater than 1000 hours.  To satisfy this need the Doublelife GLS lamp is also manufactured, having a declared life of 2000 hours.  These are similar in construction to standard GLS lamps but the filament is run at a lower temperature.  This reduces the rate of evaporation so the filament lasts longer.  The lower filament temperature also means that the lamp will not produce light as efficiently, and the customer must accept a light output reduction of around 15-20%.  Some companies also market ultra-long life 16,000 hour lamps but in practice these are a false economy.  They are so dim and inefficient to be of little use, and are certainly not economically viable for most lighting installations owing to the considerably greater electricity consumption that is required to maintain a given light level.\n\t\tIn other applications, such as photographic and studio lamps, a large amount of light is required and the lamp life is not so important.  This is taken to extremes in the case of Photoflood GLS lamps, which are over-run to produce a brighter and whiter light but have a rated life sometimes as short as only two hours."
					]
				},
				{
					subhead: "End of Lamp Life",
					imgs: [
						"/IN%20GLS%20Arc_Min.jpg",
						"/IN%20Fuses%201_Min.jpg",
						"/IN%20Fuses%202_Min.jpg",
						"/IN%20Cap%20Puncture_Min.jpg",
						"/IN%20Fuses%203_Min.jpg",
						"/IN%20Ballotini_Min.jpg"
					],
					description: [
						"When the filament fails in an ordinary incandescent lamp, the high temperatures and high voltage present may be sufficient to allow an electric arc to jump the gap between the broken pieces of filament.  This quickly develops into a high current discharge, illustrated in Figure I20.  Very high currents in excess of 200A can be passed, creating a dangerous situation that can have destructive consequences before a fuse blows somewhere in the circuit.  The offending bulb may well explode, and damage to the lamp holder is possible.  House wiring can also be damaged and it may start a fire.",
						"House wiring fuses are heavy duty devices which do not act quickly enough.  To ensure consumer safety, it has therefore been customary to build fast-acting fuses into every gas-filled GLS lamp since the 1930s.  However price pressures have resulted in an increasing number of lamps being found on the market with poor or inadequate fusing.\n\t\tThe efficiency of a fuse depends in part on its length, but often there is not enough space to fit a fuse of the required dimensions inside a GLS lamp.  For this reason two short fuses are generally used.  The fuses are located inside the glass stem, and can be seen in Figure I21.  Figure I22 illustrates an inferior lamp having only one fuse, and the lamp in Figure I23 is a dangerous design with no fusing at all.  Figure I24 illustrates a lamp having the alternative Ballotini type of fuse.",
						"When the fuses fail, a secondary arc can form between the broken fuse wires and the metal shell of the cap.  The heat it produces causes the trapped volume of air inside the cap to expand, elevating its pressure to the kind of levels found in a car tyre.  If the quality of the capping cement has deteriorated over life, the glass part of the bulb will be forcibly ejected like a bullet, leaving its metal cap hanging in the luminaire.  It is accompanied by a shower of sparks, with the possibility for personal injury or fire. In good quality lamps, the bond between the bulb and its cap is strong enough to avoid this kind of violent failure.  However the evidence of arcing can be witnessed as small holes melted in the side of the cap, known as cap puncture (Fig. I25).  Similar holes occur in the lampholder, sometimes firmly welding the bulb into its socket.  Invariably the whole lighting circuit will be tripped due to a failed house-wiring fuse.",
						"Double fusing alone is not enough to protect the consumer, if no measures are taken to prevent this dangerous arcing inside the cap.  For instance the lamp shown in Figure I26a is double fused, but still represents a dangerous design.  When the fuses fail, any secondary arcing will go for the exposed metal area inside the cap shell.  Also the shape of the glass neck mould is poor, indicated by a red line, so the bulb could easily be blown out of its cap.  To prevent this arcing, one of the three methods below is required, to provide some kind of insulation between the fuses and the metal cap shell.",
						"Also known as glass-lined caps, the black glass insulator between the contact terminals is extended right up the side walls of the cap, until it meets with the cement.  It is clear from Figure I26b that there is no bare metal at all inside this cap.  Therefore the secondary arcing cannot occur, and this lamp will fail safely at end of life.  Also note the excellent contour lines of the neck moulding of the glass bulb.  The cement can easily grip this indented style bulb, and in the rare event that arcing does still occur, the chances of the bulb being ejected from its cap are minimised.",
						"High vitrite caps are quite expensive, and a cheaper option is possible simply by filling the entire space inside the cap with a special foaming organic compound, shown in Figure I26c.  When the fuses fail the arc is quickly quenched by the surrounding material, and any destructive arcing to the cap shell is prevented.  However these organic foam materials gradually deteriorate at high temperatures.  For long-life or high temperature service lamps, the foam cannot be relied upon to work at end of life, and then one of the alternative insulation methods must be employed.",
						"This is the safest and most reliable fuse type - but also the most expensive.  The fuse wire is encapsulated in a small glass tube filled with tiny glass beads called Ballotini, named after Potters Ballotini, the Italian producer.  Should a secondary arc form between the broken pieces of fuse wire, its heat will melt the glass beads to form an electrically insulating barrier which contains and rapidly quenches the arc.  It is so efficient that only one fuse is required, but on account of their higher price they are generally employed only in the more expensive special lamps, or decorative lamps which are too small to be able to accommodate two sufficiently long bare fuses (e.g. candle and globe lamps)."
					]
				},
				{
					subhead: "Premature Failure",
					description: [
						"Some of the more common abnormal failure mechanisms of incandescent lamps are detailed below:",
						"The lamp has a milky yellow-white deposit on the inside of the glass.  This is tungsten trioxide, and it is formed when the hot filament reacts with air inside the bulb and completely burns up.  Cracks in the glass are the usual culprits.  Most commonly the crack is in the stem near the pinch, and is due to inadequate stress relief after stem making.  If the crack is in the capping cement area, it is usually indicative that too much cement is employed.  Only very rarely are bulb cracks seen.  These are due to exceptionally poor fire control on the sealex machines, or due to hot glass coming into contact with cold surfaces, with the possibility to cause thermal stress damage.",
						"A very slow air leak is sometimes observed, and this will lead to the formation of the lower tungstic oxide, usually W205, which has a smoky dark blue coloration.  A poor glass-to-metal seal is usually responsible.",
						"Lamp has a grey-black appearance on the inside of the bulb (rare).  Blackening or sooting will be especially prevalent on the lead wires and filament support wires.  The process responsible for this is the water cycle, in which water removes tungsten from the filament and deposits it on cooler regions.",
						"Filament squirming is normally due to oil contamination inside the lamp.  Oil may also be broken down into hydrocarbon vapours which conduct heat away from the filament and lead to excessively dim bulbs.",
						"A tangled or stretched filament indicates that the lamp has been under excessive vibration whilst alight, or has received a direct blow.  Shock damage when unlit leads to a clean brittle fracture of the filament.",
						"A heat tarnished cap and charred cement indicate that the lamp has been used in an inadequately ventilated fitting or in abnormally high temperatures.  May also lead to glass cracking and air lamps.",
						"Lead wires melted near the filament, or support wires melted at pigtail loop.  Fuse wires also destroyed.",
						"A sparkling or crystallised filament is typical of a lamp which has served a normal useful life.  If this characteristic is observed in early failure, it is nearly always evidence of over-voltage.",
						"Every lampmakers worst fear, this dangerous failure mechanism occurs when the gas fires on the sealex machines are poorly set, introducing a sharp ring of stress into the glass in the neck area.  The defect usually does not manifest itself until some time after the lamp has been shipped from the factory, when at a later time the glass can crack in a ring all around the neck.  The bulb becomes separated from the lamp and exposing potentially live internal wires.",
						"This is not strictly a failure mechanism, but is nonetheless troublesome.  They are found especially on small mains voltage lamps, such as C35 candle and G45 ball lamps, and only on lamps having a white internal coating of titanium dioxide powder.  One or two dark spots up to about a centimetre diameter may form on the bulb side during life.  Analysis shows that the position of the spots always coincides directly with the position of one or other of the molybdenum filament support wires.  The basic process is that if the coating runs too hot and yields water vapour, or was not adequately outgassed, a chemical transport cycle is established between coating and molybdenum supports.  This leads to the formation of a low molybdenum oxide in the coating material, which manifests itself as an unsightly dark coloured spot."
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
					title: "白炽灯",
					subhead: "简介",
					imgs: ["/IN GLS Lamp ES_Min.jpg", "/Lamp Efficacies_Min.jpg"],
					description: [
						"白炽灯是最古老的仍在普遍使用的电灯类型。其实用形式于1879年同时由英国的约瑟夫·斯旺爵士和美国的托马斯·爱迪生发明。在过去的130年中，它在材料和制造方面经历了许多变化，以达到其当前作为光源的性能和便利性。图I1展示了一种典型现代白炽灯的构造。",
						"直到最近，白炽灯几乎被用于所有应用场合。尽管它是将电能转化为可见光的效率最低的技术，并且尽管已经开发出几种效率明显更高的替代灯具类型，直到2010年，白炽灯的年产量仍高于其他任何灯具类型。也许这证明了在消费者眼中，其设计的有效性、受欢迎程度和简单性是如此突出，以至于没有其他光源显示出足够强大的技术特点来真正取代白炽灯照明。多年来，普通民众一直愿意为其低效率付出代价，以享受它的其他好处。最终，只有通过政治干预，通过禁止白炽灯以减少全球能源消耗，才有可能强制向更节能的光源过渡。然而，白炽灯技术以略微更高效的钨卤素灯的形式继续存在。",
						"卷绕的钨丝是灯具的核心，光就在这里产生。它通过两根细钼丝在两个中间点得到支撑，这些钼丝具有必要的耐火特性，同时又略带弹性。电流通过一对镀镍钢引线导入灯丝，灯丝尾部被夹在这些引线中。这些引线的每一端都焊接有一段特殊的合金——杜美丝，杜美丝能在玻璃和引线之间形成气密密封。杜美丝的另一端焊接在镀铜钢引线上，镀铜钢引线则与灯座相连，完成电气连接。在这些外引线中的一根或两根上，有一个保险丝段，通常套有玻璃套管并填充有玻璃微珠（ballotini），这确保了灯具在其使用寿命结束时能够安全地失效。引线固定在一个称为灯脚的玻璃组件中，一根较小的玻璃管——排气管也密封在灯脚中。排气管在灯脚的顶部保持开口，这使得在密封后可以将空气从灯泡中抽出。灯座通过一种特殊的热固化水泥固定在灯泡上，镀铜引线穿过灯座末端的眼孔，用助焊剂处理后焊接在黄铜接触片上。端子之间由一种特殊的黑色玻璃——维特玻璃（vitrite）绝缘，即使在高温下，维特玻璃也能提供高电阻。",
						"与其他光源相比，白炽灯的光效最低。然而，在其130年的发展过程中，设计和材料发生了许多变化，确保了其性能每几年就会有所提升，直到20世纪40年代，针对普通照明灯具的进一步技术开发实际上已经停止。",
						"图I2比较了白炽灯与其他光源在光效方面的技术进步。每瓦流明只是灯具性能的一个方面，白炽灯确实还有许多其他优点——主要是它们可以直接从电源供电，无需任何变压器或镇流器，它们提供了完美的显色指数100，它们是易于调光的明亮光源，而且成本极其低。"
					]
				},
				{
					subhead: "灯座命名",
					imgs: ["/Cap Nomenclature_Min.png"],
					description: [
						"由于灯座的种类繁多，国际电工委员会开发了一套完整的命名系统。它以一个字母开头，表示灯座的一般类型，后面可能跟着额外的字母来表示一个子类别。第二部分是一个数字，表示灯座的外壳直径（或插脚间距）以毫米为单位。代码的第三部分是一个小写字母，用来表示接触片（或插脚）的数量。基本设计的特殊修改可以用一个破折号后的字符来表示。这三到四部分通常足以定义灯座，以满足最终用户在兼容性方面的需要。然而，为了提供完整的定义，可能还需要某些其他尺寸，这些尺寸跟在一个正斜杠后面（例如，灯座的长度）。所有普通照明灯座类型的列表都保留在国际标准IEC 60061中。"
					]
				},
				{
					subhead: "灯泡命名",
					imgs: [
						"/IN Glass Bulb Shapes_Min.jpg",
						"/Bulb Nomenclature1_Min.png",
						"/Bulb Nomenclature2_Min.png"
					],
					description: [
						"每个玻璃灯泡都用一个独特的代码来分类，以确定其大小和形状。灯泡的形状用字母（或字母组合）表示，后面跟着一个数字，表示最大直径。在世界上的大多数国家，直径是以毫米为单位表示的。然而，在美洲，这个数字代表最大直径是八分之一英寸的倍数（例如，A19灯泡的直径是19个八分之一英寸，即2.375英寸或60毫米）。在公制国家，对于某些灯泡形状，特别是PAR和MR反射型灯泡，以及荧光灯管，有时也会遇到这种英制单位。"
					]
				},
				{
					subhead: "灯丝命名",
					imgs: ["/IN Filament Mount Shapes_Min.jpg"],
					description: [
						"多年来，已经形成了几种不同的灯丝安装风格标准。这些风格没有在任何国家或国际标准中规定，但通用电气公司在1910年左右引入了一套完整的命名系统。大多数其他灯具制造商都采用了这种系统，因此它成为了一种工业标准。",
						"该系统由两部分编码组成。第一个字母标识所使用的灯丝线类型（S = 直线，C = 单圈，CC = 双圈，FC = 平圈，R = 带状，B = 编织）。第二部分是一个数字，表示安装后的灯丝形状，如图I4所示的插图。"
					]
				},
				{
					title: "工艺",
					subhead: "工作原理",
					imgs: ["/IN Wiens Curves_Min.jpg", "/IN Glowing_Min.jpg", "/IN GLS Energy_Min.jpg"],
					description: [
						"白炽灯基于温度辐射原理——即物体在被加热到高温时会发出光。这是一种众所周知的现象，每天都能观察到，例如炉火中煤炭的发光，或者熔化的钢水在倒入模具时发出的明亮黄色光芒。现代灯具中的发光体是一根细金属丝，通过电流流过它来加热。电子被迫沿着狭窄的导线流动所产生的摩擦使其温度升高，电流越大，加热程度越高。",
						"如果加热到大约500°C以上，灯丝会开始微弱发光，但要获得有用的光量，需要在超过2500°C的温度下工作，此时它会发出白炽光。灯丝实际达到的温度取决于它所消耗的功率，即瓦数。瓦数又取决于灯丝导线的电阻和电源的电压。因此，通过为它们提供具有不同电阻的灯丝，可以制造出各种功率等级的灯具。",
						"图I6展示了经典的维恩位移定律，揭示了被加热到各种温度的灯丝的光谱功率分布（由不同的曲线以开尔文温度K表示）。可以看出，灯丝温度越高，它辐射的能量就越多，由每条曲线下的面积表示。虚线表明了一个普遍趋势，即灯丝温度越高，其峰值发射波长就越从红外区域向可见光区域移动。因此，可以理解为效率最高的灯具是那些具有尽可能高的灯丝工作温度的灯具。",
						"大多数金属在所需的灯丝工作温度下会熔化，只有很少的材料可以作为合适的灯丝。斯旺和爱迪生选择了碳，因为它是所有已知化学元素中工作温度最高的——它在大约3825°C时升华。然而，它的蒸汽压相当高，在达到这个温度之前，它就会迅速蒸发。为了降低蒸发速率并获得令人满意的使用寿命，碳必须在明显较低的温度下工作。尽管如此，它仍然是直到1906年引入锇（熔点3033°C）和1907年引入钽（熔点3017°C）之前唯一的量产灯丝材料。尽管这些金属的熔点较低，但它们的蒸汽压比碳低得多。因此，对于给定的灯丝蒸发速率，以及因此的灯具寿命，它们可以在比碳更高的温度下工作。由于温度更高，它们产生的光更多，这已经通过维恩位移曲线解释过了。1907年，引入了具有压铸钨丝的灯具，其熔点为3417°C，蒸汽压更低。钨至今仍然是首选金属，但从压铸钨粉制成的易碎灯丝在1909年被拉制钨丝取代，后者更强韧，更易于操作。",
						"尽管钨丝允许的极高工作温度，其将电能转化为可见光的效率仍然低得可怜。图I7右侧的能量平衡图显示了现代100W普通照明灯的能量是如何耗散的。只有大约5%的能量转化为可见光，这相当于每瓦13.4流明的光效。高达83%的能量以辐射热的形式浪费掉，而剩余的12%则以通过灯座和玻璃外壳传导的热量形式散失。事实上，这些灯具更像是高效的电加热器，只是浪费了少量能量以光的形式散发出去！"
					]
				},
				{
					subhead: "充气效果",
					imgs: ["/IN Cage Lamp BC_Min.jpg", "/IN Gas Loss_Min.jpg"],
					description: [
						"主电源电压的白炽灯需要一根相对较长且直径非常小的灯丝。典型的现代240V、100W普通照明灯的灯丝比人的头发还细，长度却达到了惊人的1152毫米。在最初的白炽灯中，灯丝的这种巨大长度是通过将其安装成一系列V形发夹来容纳的，这些发夹连接在灯泡两端的两组支撑之间。这种结构被称为“松鼠笼”或S-1灯丝安装结构，如右侧的图I8所示。灯泡内是高真空环境，因为高温下的灯丝在化学上非常活泼，如果暴露在空气中，很快就会被氧化。",
						"正如前面提到的，灯丝在高温工作时会蒸发，这导致灯丝逐渐变细。灯丝的某些部分总是比其他部分蒸发得稍快一些，例如由于钨丝存在微观缺陷，而钨丝无法制造出完全均匀的直径。这些变薄的区域会导致在工作时形成热点。热点区域的温度更高，这加速了蒸发速率，直到灯丝过热熔化，或者变得如此之细，以至于无法支撑自身的重量。在普通照明灯的设计中，通常选择一种灯丝温度，使其平均寿命达到1000小时。",
						"显然，找到一种减缓钨蒸发速率的方法是很有必要的。这不仅可以制造出寿命更长的灯泡，而且制造出更高效灯泡的可能性更加令人感兴趣。如果减缓了蒸发，就可以提高灯丝温度，并将寿命重新降低到1000小时的水平。更热的灯丝产生光的效率更高，这在前面的页面中已经解释过了。由于灯泡在其使用寿命内消耗的电流成本是其自身成本的许多倍，因此高效率的灯泡在几乎所有情况下都比长寿命版本对客户更有经济意义。",
						"一个实际的解决方案是用惰性气体替换灯泡内的真空。气体对灯丝施加的物理压力可以减少钨原子从其表面蒸发的倾向，其原理与压力锅中水的沸点升高完全相同。不幸的是，有一个问题——尽管气体在减缓灯丝蒸发方面是有效的，但它的导热性当然比真空高。因此，由于传导和对流效应，它会从灯丝带走一些热量。这一点在作者在伦敦胜利照明公司制造的两盏特殊的松鼠笼式白炽灯中得到了清晰的展示。这两盏灯的灯丝完全相同，但一盏是真空的，另一盏充有大约700托的压力的氩气/氮气混合气体。",
						"这些灯如图I9所示，左边的是真空灯，右边的是充气灯。真空灯亮得很亮，而充气灯却只发出微弱的光，尽管它们的功率相同。很容易证明灯丝正在向气体充气散热，因为如果触摸两个灯泡的顶部，充气的那个玻璃会明显更热——尽管它的灯丝看起来明显更冷。这常常让人们感到困惑，但灯丝更冷的原因是气体正在传导热量，并将其传递到灯泡上方的壁上。",
						"气体对流的效果也得到了极好的可视化，因为只有灯丝的上部会发光，这是由于热量上升。如果将灯倒置，热气体会移动到灯泡的另一端，灯丝发光的部分也会随之移动。由于气体在灯脚周围流动时产生的湍流，可能会观察到闪烁的效果。",
						"众所周知，现代白炽灯是充气的，因此气体充气导致的热量损失问题显然已经得到了解决。关于防止热量损失到气体充气的机制将在下一页的“灯丝卷绕效果”部分中详细描述。"
					]
				},
				{
					subhead: "灯丝绕组效应",
					imgs: [
						"/IN GLS Convection_Min.jpg",
						"/IN%20C-9%20Lamp%20BC_Min.jpg",
						"/IN%20CC%20Lamp%201924_Min.jpg",
						"/IN%20Langmuir%20Sheath_Min.jpg",
						"/TH%20Triple%20Coil_Min.jpg"
					],
					description: [
						"尽管绕组灯丝仍然会通过传导和对流将部分热量传递给气体，但对于大多数灯泡来说，热量损失大幅减少，减少灯丝蒸发和高温运行带来的好处远远超过了剩余的能量损失。然而，在设计充气灯时，不应忘记灯丝几何形状及其期望工作温度的重要性。",
						"典型的单绕组充气灯如图 I11 所示。灯丝安装在水平环上，称为 C-9 花环配置，这样当灯泡以最常见的垂直位置运行时，整个长度上的气体冷却效果相同。如果像早期的真空灯那样轴向安装，那么鉴于典型单绕组灯丝的较长长度，由于热气向上流动，上端会运行得更热，温度梯度会导致灯丝的顶部过早烧毁。请参阅上一页的图 I9 以直观了解这种效果。这也是普通单绕组白炽灯在垂直向上或向下运行时寿命最长、性能最佳的部分原因，因为此时灯丝的任何部分都不会因对流气流而过热。",
						"采用双绕组灯丝的第一种实验性普通服务灯如图 I12 所示。这是 1924 年在伦敦 Osram-GEC Wembley 工厂的 Hirst 研究实验室开发的。据信这是一种大约 100W 额定功率的高压 GLS 灯。但仍有诸多技术难题，使得其市场推出时间推迟了近十年，直到 1933 年在英国和欧洲上市，1936 年在美国上市。",
						"图 I13 所示的演示灯可视化了绕组和向气体填充的热损失。该灯由作者在 GE 照明公司莱斯特工厂制作。灯丝是一种普通的 240V 60W 双绕组类型，但其中一部分被拉伸成单绕组，剩余部分完全展开成直线。整个灯丝由同一根钨丝制成，直径相同。灯泡内填充了标准的 85:15 氩气:氮气混合物。在以相当低的电压开启时，双绕组部分亮起。随着电流增加，单绕组开始发光，但即使在 240V 时，直线部分也完全不发光。",
						"近年来，人们一直在开发三绕组灯丝，这种产品已在日本由东芝商业化。这并没有显著提高发光效率，但灯丝尺寸缩小，接近点光源，可以在小型反光镜中获得出色的光学控制。通过改变钨的冶金学来控制灯丝下垂程度是一个必须克服的关键挑战，同时还要限制钨丝中钾掺杂剂的浓度，以避免因相邻绕组之间不寻常的高电压梯度而产生电弧问题。"
					]
				},
				{
					subhead: "真空灯与充气灯",
					imgs: ["/IN%20Vac-GF_Min.jpg"],
					description: [
						"有些灯型，充气实际上可能会降低性能，或者根本没有任何优势。例如在功率极低的灯中，灯丝非常细，即使绕成螺旋形，仍然很薄，表面积与体积比很大，因此向气体的热量损失始终很高。由于实际限制，无法将如此细的灯丝绕在更大直径的芯轴上，以改善这种表面积与体积比，因为这与这种线圈的尺寸稳定性有关。当芯轴比过大时，灯丝会出现下垂问题。",
						"因此，必须评估某一特定灯型设计是否真的能从充气中受益，大多数情况下，低功率版本是作为真空型生产的。灯丝仍然绕成螺旋形，但这是纯粹为了缩短其长度，使灯丝更容易安装在灯脚组件上。甚至双螺旋真空型也出于同样的原因存在。当然，在真空中，绕组没有任何作用，因为灯丝周围没有气体流动，也没有向内部大气的热量损失。",
						"由于在真空灯中钨的蒸发不受限制，灯丝必须在大约2100°C的较低温度下运行，以保持1000小时的标准寿命。因此，真空灯的效率低于充气型。在实际应用中，从充气型转换为真空型的转折点大约在25瓦。对于由于低电压运行而使用较粗灯丝的微型灯，转换点约为3瓦。",
						"白炽灯条也是真空型的，即使是150瓦的大功率灯也是如此。这仅仅是因为灯丝必须延伸到整个发光管的长度，因此不能紧密绕组。如果这种灯充气，那么如此长的灯丝的热量损失会非常高。从图I13中的照片可以看出，充气中最高效的线圈是紧密绕组的，而灯条灯的灯丝太长，永远无法在气体环境中高效运行。",
						"许多单端管状灯也需要长灯丝，这些也必须是真空型的。如果灯丝很长并且是用于垂直燃烧的，气体对流的问题又会回来。热气会上升到灯泡的上端，使灯丝的一端过热，导致提前失效。",
						"在决定某一特定灯型设计是否应该充气或真空以实现最佳性能之前，还必须考虑应用。彩色GLS灯的主要应用之一是节日户外照明，即使是通常会充气的功率，这些灯也是用真空制成的。已经看到，由于灯丝向灯泡壁的传导和对流热量，充气灯的灯泡壁温度要高得多。当与彩色涂层结合时，灯泡壁吸收的热量更多，其温度可能会变得非常高。由于这些灯用于户外，会遇到雨水或降雪，这可能会导致灯泡外壳的热冲击，从而导致玻璃破裂。因此，这些灯必须制成真空型，以保持玻璃足够凉爽。"
					]
				},
				{
					subhead: "气体类型",
					imgs: ["/Choice of Gas Type1_Min.png", "/Choice of Gas Type2_Min.png"],
					description: [
						"用于填充白炽灯的气体必须化学惰性，即它们不应与炽热的灯丝发生反应（卤素灯除外）。这意味着它们还需要极其纯净，因为极少量的某些物质可能会产生灾难性的影响。例如，在一个能够填充五十万只普通灯泡的气缸中，仅仅一滴水就会导致所有这些灯泡变黑并提前失效！下表显示了对钨惰性的气体以及适合作为填充气体的气体：",
						"气体的分子量是一个原子或分子的重量。原子越重，减少灯丝蒸发的效果越好，从而使灯的寿命更长。可以看出，它们还具有较低的热导率，减少了气体损失，因此灯丝会运行得更热，更有效地产生光。\n\t\t因此，对于白炽灯来说，氙气似乎是最佳的填充气体选择。但这种气体在大气中的含量极少，这使得它价格昂贵。氪气的价格大约便宜十倍，但仍然稀缺，因此我们通常使用氩气，其价格大约便宜500倍。然而，第一批充气灯不得不使用氮气，因为在世纪之交，还没有氩气蒸馏厂。当氩气灯最终推出时，人们发现其较低的电离电势导致引线之间出现电弧问题。通过添加少量氮气克服了这一问题，欧洲灯泡中常见的是一种85:15的氩气:氮气混合物。美国的低电压灯泡可以使用95:5的气体，因此效率略高。填充压力约为0.8个大气压，在灯泡运行时通常会上升到略高于大气压。\n\t\t到了20世纪30年代，随着新的蒸馏厂开业，氪气的价格大幅下降。1936年，匈牙利的Tungsram公司推出了第一款氪气填充的普通灯泡。为了减少这种昂贵气体所需的体积，设计了一种新的玻璃灯泡形状。结果是一种具有蘑菇形外壳的灯泡，这种灯泡至今仍在生产。氪气蘑菇灯通常比普通氩气填充灯泡多提供约5%的光，并且寿命延长50%。或者，还可以提供一种节能型灯泡系列，以相同的光输出但功率低10%。在高效率的微型灯泡中使用氪气也是一种标准做法，因为对于低电压类型，氪气的好处要明显得多。矿工帽灯是一个重要的应用领域，因为较小的电池可以提供相同的光水平。即使在今天的微型卤素灯泡中，有时也会发现氙气，特别是在需要极高效率或长寿命的汽车灯和投影灯中。\n\t\t唯一另一种在白炽灯中商业应用过的气体是氢气。它以极高的热导率而著称，使其对于普通照明来说效率低下，但由于它在脉冲之间能更快地冷却灯丝，因此在特殊的信号灯中得到了应用。更快的变黑时间允许通过光脉冲进行更高速的信号传输。下表显示了可用灯泡填充气体的主要应用："
					]
				},
				{
					subhead: "除气剂",
					description: [
						"在灯泡抽真空以及可能充气的过程中，即使使用高速真空泵设备，也无法完全去除空气的痕迹。此外，少量的空气和水分会附着在内部的玻璃和金属部件上，如果不对这些进行处理，灯泡的寿命将会很短且效率低下，无法令人接受。因此，每只灯泡内部都包含了一种特殊的化学物质——除气剂。除气剂是一种可以去除灯泡内特定杂质的化学物质，它既有助于在制造过程中实现真空，也有助于在灯泡使用寿命期间保持纯净度。",
						"对白炽灯危害最大的现象之一是水循环。如果除气剂不足以去除灯泡内所有剩余的水分，就会发生这种情况。当灯丝被点亮时，高温会使水蒸气分解成氢气和氧气。自由的氧气随后会与炽热的灯丝发生反应，生成三氧化钨。三氧化钨的蒸汽压较低，会从灯丝表面蒸发，然后沉积在较冷的灯泡壁或灯丝支撑线上。随后，它会被水解时释放出的氢气还原。实际上，氢气从三氧化钨中夺回了氧气，再次生成水。钨金属会以一层黑色薄膜的形式残留在内部部件上，而水则会再次回到灯丝并侵蚀它。水循环会导致白炽灯灯泡迅速变黑，当灯丝被侵蚀到一定程度后，灯泡就会烧毁，导致提前失效。",
						"红磷是最早的除气剂，由马利阿尼于1893年引入，用于去除他在意大利实验室制造的灯泡中的氧气和水蒸气。如今，它有助于对抗水循环，这是一种破坏加工不良的白炽灯灯丝的化学过程（见下文）。在密封到灯泡之前，灯丝会被浸入或喷上悬浮在有机溶剂中的除气剂。\n\t\t当灯丝首次被点亮时，磷会蒸发，并在离开灯丝的过程中与任何残留的氧气发生反应。这会形成五氧化二磷，有时会在玻璃灯泡上形成一层姜黄色的涂层。这种化学物质具有吸湿性，能够去除水蒸气。除气剂仅在首次点亮后的最初几分钟内有效。它并不是特别好的除气剂，但成本很低，对于加工良好的普通灯泡来说已经足够。许多质量较差的制造商仍然需要依赖额外的除气剂来弥补灯脚制作、安装和抽气操作控制不佳的问题。\n\t\t如果除气剂添加过量（或者制造出异常纯净的灯泡，使得并非所有的五氧化二磷都被消耗掉），那么灯泡壁上就会出现姜黄色的涂层。这在微型灯中尤其成问题，因为它会吸收已经很小的光输出的相当大一部分。在真空和微型灯中，通常会在磷混合物中添加冰晶石，它与除气剂的反应会产生一种更透明的涂层，但仍然同样有效。\n\t\t红磷并不总是能够承受Sealex机器上遇到的高温，而且它的酒精溶剂也会将水分带入灯泡。因此，如今它已被新的磷化三氮五（P₃N₅）除气剂系列所取代，这种除气剂更稳定，基于戊酸乙酯溶剂。它们也不易燃，减少了由于旧的干燥红磷除气剂沉积物而有时会在灯泡制造机器上引发的自发火灾的发生。\n\t\t最后，在一些高价值的普通灯泡中，可能会使用第二种除气剂。它由涂在引线或将在大约400-500°C下工作的其他部件上的锆铝漆组成。它形成了一种有效的氢气除气剂，进一步有助于对抗水循环。它通常用于内涂白的灯泡。在一只典型的普通灯泡中，粉末颗粒的表面积可以达到2000平方米，这在高速生产线上很难彻底排气。"
					]
				},
				{
					subhead: "燃烧位置的影响",
					imgs: ["/IN%20Blackening_Min.jpg"],
					description: [
						"普通灯泡（GLS）是设计为悬挂式使用的，灯头朝上。当水平使用时，气体对流会使灯丝上部局部过热，从而对灯泡寿命产生不利影响。在悬挂式位置，灯丝位于灯脚支撑的单线尾部环路中。在其他位置使用时，灯丝可能会掉到支撑环路的另一侧，那里有时会有两根平行的电线，这可能会导致灯丝线圈短路，从而缩短寿命——尤其是图I10中的C-9扁平花环设计。对于图I1中的CC-9悬挂花环设计，由于支撑线与灯丝呈一定角度，灯丝匝间短路的可能性较小。\n\t传统的梨形玻璃灯泡外壳是经过数十年的科学发展的结果，旨在实现一种能够提供最长寿命和最高光通维持率的灯泡形状。其基本形状能够在不使玻璃或灯头胶水的温度超过安全工作限度的情况下，为加热后的气体提供足够的冷却。高功率灯泡可能在颈部区域安装有金属或云母隔热罩，以阻挡热气上升，将灯头温度控制在一定范围内。\n\t在使用过程中，灯丝会持续蒸发钨，这些钨被热气向上携带并沉积在灯泡壁上。在悬挂式位置，钨沉积在颈部区域，对光输出的影响非常小。光通量输出始终是针对以这种方向燃烧的灯泡而言的。对于灯头朝下或水平使用的灯泡，蒸发的物质会使位于灯丝正上方的灯泡部分变暗，这可能会吸收相当数量的光。图I16所示为变暗的区域。",
						"近年来，标准60毫米普通灯泡的尺寸有缩小的趋势，出现了直径为55毫米或50毫米的灯泡。尽管这使得灯泡体积变小，包装和运输成本降低，但代价是光通量衰减加速，因为蒸发的钨沉积在更小的面积上，形成了更暗的吸光涂层。\n\t\t在真空型灯泡中，不存在气体对流，无论使用位置如何，整个玻璃灯泡都会变暗。由于没有气体填充来降低灯丝蒸发的速度，它还会更快地变黑。然而，真空灯仍然主要用于悬挂式，因为灯丝支撑线的形状。\n\t\t许多商业和家用灯具是设计为倒置或侧向使用灯泡的，主要是出于紧凑性或美观的考虑。在这些应用中，灯泡寿命和性能的轻微降低被认为是可接受的，并且被其他优势所抵消。最糟糕的情况是将蜡烛形和高尔夫球形灯泡水平使用，因为它们体积小，光输出衰减更快，气体没有足够的循环空间来充分冷却。灯泡通常还带有内部装饰涂层，当过热时会释放出气体杂质。在这些应用中，这些灯泡的实际使用寿命可能只有额定寿命的一半。"
					]
				},
				{
					subhead: "电压变化的影响",
					imgs: ["/IN%20Nomograph_Min.jpg"],
					description: [
						"在正常的电源电压变化范围内，光输出会随着电压变化1%而变化约3.5%。电压对寿命的影响要明显得多；电压升高5%会使灯泡寿命大致减半，而电压降低5%则会使寿命大致增加一倍。如果发现灯泡总是提前失效，首先要检查灯泡上标注的电压与电源端子处的实际电压是否一致。在某些情况下，似乎可以将240V的灯泡接在230V的电路上以延长灯泡寿命，直到意识到这样做的结果是光输出会显著下降，而电力消耗的减少却远没有那么多。\n\t一般来说，将灯泡运行在除其设计电压之外的任何电压上都是不明智的，但也有例外。例如，对于塔顶的航空障碍灯，更换成本非常高，因此可以采用欠压运行。相比之下，在演播室照明中，经常采用过压运行，额外的光输出可以减少投影仪的数量并简化安装结构，这种做法比在一年后更换灯泡更值得，因为每次拍摄前都需要更换灯泡。\n\t图I17中的诺模图显示了电源电压变化与充气白炽灯性能之间的关系。它只适用于真空灯和钨卤素灯的近似情况。"
					]
				},
				{
					subhead: "启动特性",
					imgs: ["/IN%20Inrush_Min.jpg"],
					description: [
						"所有基于白炽技术的灯泡在打开开关后都会立即产生光。对于标准尺寸的灯泡，延迟时间仅为几千分之一秒，而高功率类型的灯泡可能需要长达约一秒的时间才能将灯丝加热到完全工作温度。\n\t\t当灯泡正常亮起时，其电阻（以欧姆为单位）由电压的平方除以功率得出。但在灯泡打开之前，冷灯丝的电阻要低得多。由于冷电阻较低，在打开开关的瞬间会有很大的电流通过，通常约为正常电流的14倍。随着灯丝变热，其电阻增加，电流下降，直到两者稳定下来。典型的浪涌电流曲线如下面的图I18所示。对于像230V 100W这样的低功率灯泡，其电流在大约0.05秒内就接近额定电流。对于高功率灯泡，这个过程可能需要更长的时间。以图中所示的240V 500W灯泡为例，即使在1秒后，其电流仍未降至额定水平。只有当灯丝及其引线达到正常工作温度时，才能达到完全稳定——这个过程可能需要数分钟。",
						"浪涌电流持续的时间不足以使大多数普通保险丝或断路器动作，开关制造商通常也忽略了它，因为开关更有可能在断开电路时而不是接通电路时出现故障。然而，在实践中可能会发现，一些短路断开设计无法承受与重复开关相关的电流冲击，尤其是在用于投影和演播室应用的高功率灯泡的情况下。\n\t\t认为让白炽灯持续亮着比短暂关闭以减少浪涌电流期间的能耗更经济，这是一种谬论。在浪涌期间消耗的电能成本绝对不可能像通过关闭灯泡几秒钟所节省的电流成本那么多。\n\t\t此外，还发现反复开关对灯丝灯泡的寿命影响甚微。一个很好的例子是英国行人过街天桥上的闪烁道路Belisha灯标。灯丝在闪烁间隔期间被切换到“关闭”状态，普通家用GLS灯泡在这种应用中（它们必须承受超过150万次闪烁）仍能达到1000小时的额定寿命。"
					]
				},
				{
					subhead: "灯泡寿命",
					imgs: ["/IN%20Life%20Survival_Min.jpg"],
					description: [
						"所有欧洲普通灯泡（GLS）的标称寿命已标准化为1000小时，几乎自其推出以来一直如此。多次有人质疑这是否真的是最经济的寿命，但由于用户需求的差异以及他们支付的电费和灯泡价格的差异，不可能有一个普遍适用的最优寿命，适合每个人。\n\t\t白炽灯是按照英国标准BS 161（IEC 60064）制造的，负责该标准的委员会包括来自广泛利益相关方的代表，如政府部门、专业机构、代表大用户组织、电气承包商和照明行业。他们审查了所有相关因素，如灯泡成本、电费、更换灯泡的成本、不同额定寿命下的灯泡效率等，每次他们都得出结论，长期以来的1000小时寿命应保持为标准额定值。事实上，为了尽量减少客户投诉，标称为1000小时寿命的标准灯丝通常平均设计寿命为1200小时。\n\t\t对灯泡制造过程的严格控制使得单个灯泡的寿命非常一致，但绝对的一致性是无法实现的。例如，如果将一百个相似的灯泡在相同的条件下进行测试，它们不会简单地运行1000小时然后同时全部失效。相反，灯泡寿命是以生存曲线的形式表示的，如下面的图I19所示。对于白炽灯，习惯上将额定寿命定义为样本中有70%仍在燃烧的时候。",
						"在某些安装中，灯泡更换成本特别高，例如在楼梯上方、交通信号灯或其他难以到达的地方，对于用户来说，拥有超过1000小时的灯泡寿命是有益的。为了满足这一需求，也制造了双倍寿命的普通灯泡，其标称寿命为2000小时。这些灯泡在结构上与标准普通灯泡相似，但灯丝的运行温度较低。这降低了蒸发速率，从而使灯丝寿命更长。较低的灯丝温度也意味着灯泡的发光效率会降低，客户必须接受约15-20%的光输出减少。有些公司还销售超长寿命的16000小时灯泡，但在实践中，这些灯泡是虚假的经济选择。它们非常暗且效率低下，几乎没有什么用处，而且由于维持给定光水平所需的电力消耗大大增加，对于大多数照明安装来说，它们肯定不是经济可行的选择。\n\t\t在其他应用中，例如摄影灯和演播室灯，需要大量的光，而灯泡寿命则不太重要。在光泛灯普通灯泡的情况下，这种需求被推向了极致，这些灯泡被过度驱动以产生更亮、更白的光，但其额定寿命有时只有短短两小时。"
					]
				},
				{
					subhead: "灯泡寿命终结",
					imgs: [
						"/IN%20GLS%20Arc_Min.jpg",
						"/IN%20Fuses%201_Min.jpg",
						"/IN%20Fuses%202_Min.jpg",
						"/IN%20Cap%20Puncture_Min.jpg",
						"/IN%20Fuses%203_Min.jpg",
						"/IN%20Ballotini_Min.jpg"
					],
					description: [
						"当普通白炽灯的灯丝断裂时，存在的高温和高电压可能足以使电弧在断裂的灯丝碎片之间跳跃。这种电弧会迅速发展成高电流放电，如图I20所示。可能会通过超过200A的极高电流，这会在电路中的某个保险丝熔断之前造成危险情况。故障灯泡可能会爆炸，灯座可能会损坏。房屋布线也可能会损坏，并且可能会引发火灾。",
						"房屋布线保险丝是重型设备，动作不够迅速。因此，为了确保消费者安全，自20世纪30年代以来，通常在每个充气普通灯泡中都安装了快速动作保险丝。然而，价格压力导致市场上发现越来越多的灯泡配备的保险丝质量差或不足。",
						"保险丝的效率部分取决于其长度，但通常没有足够的空间在普通灯泡内安装所需尺寸的保险丝。因此，通常使用两个短保险丝。保险丝位于玻璃灯脚内，可以在图I21中看到。图I22展示了一个只有一根保险丝的劣质灯泡，而图I23中的灯泡是一种危险的设计，完全没有保险丝。图I24展示了一种具有替代性Ballotini型保险丝的灯泡。",
						"当保险丝熔断时，可能会在断裂的保险丝线和灯头的金属外壳之间形成二次电弧。它产生的热量会使灯头内被困的空气体积膨胀，使其压力达到汽车轮胎中发现的那种水平。如果灯头胶水的质量在使用寿命期间已经恶化，灯泡的玻璃部分可能会像子弹一样被强行弹出，留下其金属灯头悬挂在灯具中。伴随着火花四溅，可能会造成人身伤害或火灾。在质量良好的灯泡中，灯泡与其灯头之间的粘结足够牢固，可以避免这种暴力故障。然而，可以在图I25中看到电弧的证据，即灯头上熔化出的小孔，称为灯头穿孔。类似的孔也会出现在灯座中，有时会将灯泡牢固地焊在其插座中。不可避免的是，整个照明电路会因房屋布线保险丝熔断而跳闸。",
						"如果不对灯头内这种危险的电弧采取措施，仅靠双重保险丝是无法保护消费者的。例如，图I26a所示的灯泡是双重保险丝的，但仍然是一种危险的设计。当保险丝熔断时，任何二次电弧都会指向灯头外壳内的暴露金属区域。此外，玻璃灯颈模具的形状也很差，用红线标出，因此灯泡很容易从其灯头中被吹出。为了防止这种电弧，需要以下三种方法之一，以在保险丝和金属灯头外壳之间提供某种绝缘。",
						"这种灯头也被称为玻璃衬里灯头，黑色玻璃绝缘体位于接触端子之间，并一直延伸到灯头的侧壁，直到与胶水相遇。从图I26b可以看出，这种灯头内根本没有裸露的金属。因此，不会发生二次电弧，这种灯泡在寿命终结时会安全地失效。注意玻璃灯泡颈部模具的优良轮廓线。这种凹陷式灯泡很容易被胶水固定住，即使在罕见的情况下仍然发生电弧，灯泡从其灯头中被弹出的可能性也最小。",
						"高硼硅灯头成本相当高，可以通过简单地用一种特殊的发泡有机化合物填充灯头内的整个空间来选择更便宜的方案，如图I26c所示。当保险丝熔断时，周围的材料会迅速熄灭电弧，防止对灯头外壳的任何破坏性电弧。然而，这些有机泡沫材料在高温下会逐渐恶化。对于长寿命或高温服务的灯泡，不能依赖泡沫在寿命终结时发挥作用，然后必须采用其他替代绝缘方法。",
						"这是最安全、最可靠的保险丝类型，但也是最昂贵的。保险丝线被封装在一个装有微小玻璃珠（称为Ballotini，以意大利生产商Potters Ballotini命名）的小玻璃管中。如果在断裂的保险丝碎片之间形成二次电弧，其热量会使玻璃珠熔化，形成一个电绝缘屏障，将电弧包含并迅速熄灭。它非常高效，只需要一根保险丝，但由于价格较高，它们通常只用于更昂贵的特种灯泡，或者装饰灯泡（如蜡烛形和球形灯泡）太小，无法容纳两根足够长的裸保险丝。"
					]
				},
				{
					subhead: "提前失效",
					description: [
						"白炽灯一些较为常见的异常失效机制如下所述：",
						"灯泡玻璃内侧有乳白色偏黄的沉积物。这是三氧化钨，当炽热的灯丝与灯泡内的空气发生反应并完全燃烧时形成。玻璃裂纹通常是罪魁祸首。最常见的裂纹位于灯脚附近的捏合处，是由于灯脚制作后应力释放不足造成的。如果裂纹出现在灯头胶水区域，通常表明使用了过多的胶水。只有极少数情况下才会看到灯泡裂纹。这通常是由于封口机上极差的火焰控制，或者是热玻璃接触到冷表面，可能会导致热应力损坏。",
						"有时会观察到非常缓慢的漏气，这将导致形成低阶氧化钨，通常是W₂O₅，它呈现一种烟熏的深蓝色。玻璃与金属之间的密封不良通常是造成这种现象的原因。",
						"灯泡内侧呈现灰黑色（罕见）。在引线和灯丝支撑线上，变黑或积碳现象会尤为明显。造成这种现象的过程是水循环，其中水从灯丝中去除钨，并将其沉积在较冷的区域。",
						"灯丝扭动通常是由于灯泡内部受到油污染。油也可能分解成碳氢化合物蒸汽，这些蒸汽会从灯丝传导热量，导致灯泡异常昏暗。",
						"灯丝缠绕或拉伸表明灯泡在点亮时受到过大的振动，或者受到了直接的撞击。未点亮时受到的冲击损坏会导致灯丝出现干净的脆性断裂。",
						"灯头被热灼烧，胶水被烧焦，表明灯泡在通风不良的灯具中使用，或者处于异常高的温度环境中。也可能会导致玻璃破裂和空气泄漏。",
						"引线在靠近灯丝处熔化，或者支撑线在尾部环路处熔化。保险丝也被破坏。",
						"灯丝出现闪烁或结晶现象，表明灯泡已经正常使用了一段正常使用寿命。如果在早期失效时观察到这种特征，几乎总是过压的证据。",
						"这是每一个灯泡制造商最害怕的危险失效机制。当封口机上的火焰调节不当，在颈部区域的玻璃中引入一个尖锐的应力环时，就会发生这种情况。这种缺陷通常不会在灯泡从工厂运出后立即显现出来，而是在后来某个时候，玻璃可能会在颈部周围裂开一个环。灯泡与灯泡主体分离，暴露了可能带电的内部电线。",
						"这严格来说并不是一种失效机制，但确实令人烦恼。它们尤其出现在小型市电电压灯泡上，如C35蜡烛形灯泡和G45球形灯泡，而且只出现在有二氧化钛粉末内涂层的灯泡上。在使用寿命期间，灯泡侧面可能会形成一两个直径约一厘米的暗斑。分析表明，这些斑点的位置总是与钼灯丝支撑线的位置完全一致。基本过程是，如果涂层运行温度过高并产生水蒸气，或者没有充分排气，就会在涂层和钼支撑之间建立一个化学传输循环。这导致涂层材料中形成低阶钼氧化物，表现为一个难看的深色斑点。"
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
