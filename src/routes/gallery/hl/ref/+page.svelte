<script lang="ts">
	import { onMount } from "svelte";
	import { goto } from "$app/navigation";
	import TranslationBox from "$lib/TranslationBox.svelte";

	const translations = {
		en: {
			boxes: [
				{
					title: "Tungsten Halogen - Reflector",
					description: [
						"Following the development of the Single-Ended tungsten halogen lamp, it became considerably easier to extend the domain of halogen lamps with new reflector types. At first these were offered for photographic and projection applications, but their superb optical efficacy, due to the compact filament design and the possibility to accurately align the filament at the focus of the optical system, later saw the range being extended to general lighting lamps.",
						"Both non-directional as well as reflector halogen lamps continue to be popular. In the most professional applications the luminaire manufacturers often prefer to employ non-directional halogen capsules and to add value to their equipment by separating the optics from the lamp, however the reflector lamps with all optical control being integrated offer a low cost and easy solution for the wider base of luminaire manufacturers who do not have their own internal optical competencies. They also offer the advantage of factory-focussed optics with every lamp, with a clean and new reflective surface being provided at each lamp change."
					]
				},
				{
					subhead: "Low Voltage Glass Reflector",
					intros: [
						["GE", "150W", "First MR16 Halogen Reflector Lamp - EJM", "1967"],
						["Sylvania", "300W", "Early MR16 with Peened Reflector - ELH", "1972"],
						["GE", "50W", "Early MR16 with Facetted Reflector - ENL", "1976"],
						["Thorn", "50W", "Lightstream MR16 display lamp - M50 EXZ", "1985"],
						["Osram", "50W", "Halostar KLR51 (MR16) - 41870FL M50 EXZ", "1986"],
						["Philips", "50W", "Cool Beam Low Voltage MR16 - 6440 FPF", "1989"],
						["Sylvania", "42W", "Tru-Aim Energy Saver MR16 - EYR", "1986"],
						["Sylvania", "50W", "Tru-Aim Professional Sealed MR16 - EXZ", "1987"],
						["Sylvania", "20W", "Professional DeLuxe Sealed MR16 - BAB", "1992"],
						["Philips", "49W", "MR16 high efficiency with square reflector", "1990"],
						["Philips", "50W", "Masterline MR16 high efficiency - EXN", "1990"],
						["Thorn", "50W", "Lightstream MR16 with Bayonet Cap - M57 GBT", "1988"],
						["Thorn", "20W", "Lightstream MR11 - M52 FTB", "1986"],
						["GE", "50W", "Twist-and-Lock MR16 - TAL423", "1993"]
					],
					pictures: [
						"/t TH RM GE EJM.jpg",
						"/t TH RM Sylvania ELH.jpg",
						"/t TH RM GE ENL.jpg",
						"/t TH RM Thorn Q50MR16O-12 EXZ.jpg",
						"/t TH RM Q50MR16O-12 EXZ Osram.jpg",
						"/t TH RM Philips FPF.jpg",
						"/t TH RM Q42MR16O-12 EYR Sylvania.jpg",
						"/t TH RM Q50MR16S-12 EXZ Sylvania Prof.jpg",
						"/t TH RM Q20MR16S-12 BAB Sylvania PDL.jpg",
						"/t TH RM Philips MR16SQ.jpg",
						"/t TH RM Philips Masterline EXN.jpg",
						"/t TH RM Q50MR16SP-B15d-12 M57 Thorn.jpg",
						"/t TH RM Thorn M52.jpg",
						"/t TH RM GE TAL423.jpg"
					]
				},
				{
					subhead: "Low Voltage Metal Reflector",
					intros: [
						["Philips", "35W", "Aluminium Reflector AR56 Bayonet - GBG", "1979"],
						["Philips", "50W", "Aluminium Reflector AR56 Bayonet - GBK", "1986"],
						["Thorn", "20W", "Aluminium Reflector AR48 Bayonet - M/53", "1986"],
						["Osram-GEC", "50W", "Aluminium Reflector AR58 Bayonet - M/84", "1990"],
						["Osram", "50W", "Aluminium Reflector AR70 Antiglare", "1980"],
						["Wotan", "75W", "Halostar Maxi Spot AR70 - 41980FL M/160", "1986"],
						["Sylvania", "20W", "Professional Metal Reflector AR70", "1989"]
					],
					pictures: [
						"/t TH RA Philips GBG.jpg",
						"/t TH RA Q50AR56FL-B15d-12 GBK Philips.jpg",
						"/t TH RA Q20AR48SP-B15d-12 Thorn M53.jpg",
						"/t TH RA Osram AR58 M84.jpg",
						"/t TH RA Osram AR70.jpg",
						"/t TH RA Q75AR70SP-B15d-12 Wotan.jpg",
						"/t TH RA Sylvania AR70 Professional.jpg"
					]
				},
				{
					subhead: "Mains Voltage",
					intros: [
						["Sylvania", "50W", "Hi-Spot ES50 - The Original GU10 Lamp", "1997"],
						["Osram", "40W", "DecoPin Aluminium Reflector G9 Base", "2006"],
						["Philips", "20W", "MasterPAR20 Electronic Integrated Transformer", "1999"],
						["Sylvania", "90W", "ReptiStar PAR30 Infrared Gold Reflector", "2006"]
					],
					pictures: [
						"/t TH RM Q50MR16FL-GU10-230 Sylvania.jpg",
						"/t TH RA Q40AR40FL-G9-230 Osram Decopin.jpg",
						"/t TH RP Q20PAR20S Electronic Philips 2.jpg",
						"/t TH RP Sylvania 120-90PAR30SP-E26 Gold.jpg"
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
					title: "钨丝卤素灯-反射灯",
					description: [
						"在单端钨卤素灯开发之后，卤素灯的领域得以通过新的反射器类型进一步拓展。最初，这些反射器被用于摄影和投影应用，但由于其出色的光学效率——这得益于紧凑的灯丝设计以及能够精确地将灯丝对准光学系统的焦点——其应用范围后来被扩展到普通照明灯。",
						"无论是非定向卤素灯还是反射型卤素灯都持续受到欢迎。在最专业的应用中，灯具制造商通常更倾向于使用非定向卤素灯泡，并通过将光学元件与灯分离来为其设备增值。然而，对于那些没有自身内部光学能力的灯具制造商来说，集成了所有光学控制的反射型灯提供了一种低成本且简单的解决方案。它们还具有在每次更换灯泡时提供经过工厂聚焦的光学元件以及干净、全新的反射表面的优势。"
					]
				},
				{
					subhead: "低压玻璃反射灯",
					intros: [
						["GE", "150W", "First MR16 Halogen Reflector Lamp - EJM", "1967"],
						["Sylvania", "300W", "Early MR16 with Peened Reflector - ELH", "1972"],
						["GE", "50W", "Early MR16 with Facetted Reflector - ENL", "1976"],
						["Thorn", "50W", "Lightstream MR16 display lamp - M50 EXZ", "1985"],
						["Osram", "50W", "Halostar KLR51 (MR16) - 41870FL M50 EXZ", "1986"],
						["Philips", "50W", "Cool Beam Low Voltage MR16 - 6440 FPF", "1989"],
						["Sylvania", "42W", "Tru-Aim Energy Saver MR16 - EYR", "1986"],
						["Sylvania", "50W", "Tru-Aim Professional Sealed MR16 - EXZ", "1987"],
						["Sylvania", "20W", "Professional DeLuxe Sealed MR16 - BAB", "1992"],
						["Philips", "49W", "MR16 high efficiency with square reflector", "1990"],
						["Philips", "50W", "Masterline MR16 high efficiency - EXN", "1990"],
						["Thorn", "50W", "Lightstream MR16 with Bayonet Cap - M57 GBT", "1988"],
						["Thorn", "20W", "Lightstream MR11 - M52 FTB", "1986"],
						["GE", "50W", "Twist-and-Lock MR16 - TAL423", "1993"]
					],
					pictures: [
						"/t TH RM GE EJM.jpg",
						"/t TH RM Sylvania ELH.jpg",
						"/t TH RM GE ENL.jpg",
						"/t TH RM Thorn Q50MR16O-12 EXZ.jpg",
						"/t TH RM Q50MR16O-12 EXZ Osram.jpg",
						"/t TH RM Philips FPF.jpg",
						"/t TH RM Q42MR16O-12 EYR Sylvania.jpg",
						"/t TH RM Q50MR16S-12 EXZ Sylvania Prof.jpg",
						"/t TH RM Q20MR16S-12 BAB Sylvania PDL.jpg",
						"/t TH RM Philips MR16SQ.jpg",
						"/t TH RM Philips Masterline EXN.jpg",
						"/t TH RM Q50MR16SP-B15d-12 M57 Thorn.jpg",
						"/t TH RM Thorn M52.jpg",
						"/t TH RM GE TAL423.jpg"
					]
				},
				{
					subhead: "低压金属反射灯",
					intros: [
						["Philips", "35W", "Aluminium Reflector AR56 Bayonet - GBG", "1979"],
						["Philips", "50W", "Aluminium Reflector AR56 Bayonet - GBK", "1986"],
						["Thorn", "20W", "Aluminium Reflector AR48 Bayonet - M/53", "1986"],
						["Osram-GEC", "50W", "Aluminium Reflector AR58 Bayonet - M/84", "1990"],
						["Osram", "50W", "Aluminium Reflector AR70 Antiglare", "1980"],
						["Wotan", "75W", "Halostar Maxi Spot AR70 - 41980FL M/160", "1986"],
						["Sylvania", "20W", "Professional Metal Reflector AR70", "1989"]
					],
					pictures: [
						"/t TH RA Philips GBG.jpg",
						"/t TH RA Q50AR56FL-B15d-12 GBK Philips.jpg",
						"/t TH RA Q20AR48SP-B15d-12 Thorn M53.jpg",
						"/t TH RA Osram AR58 M84.jpg",
						"/t TH RA Osram AR70.jpg",
						"/t TH RA Q75AR70SP-B15d-12 Wotan.jpg",
						"/t TH RA Sylvania AR70 Professional.jpg"
					]
				},
				{
					subhead: "市电电压",
					intros: [
						["Sylvania", "50W", "Hi-Spot ES50 - The Original GU10 Lamp", "1997"],
						["Osram", "40W", "DecoPin Aluminium Reflector G9 Base", "2006"],
						["Philips", "20W", "MasterPAR20 Electronic Integrated Transformer", "1999"],
						["Sylvania", "90W", "ReptiStar PAR30 Infrared Gold Reflector", "2006"]
					],
					pictures: [
						"/t TH RM Q50MR16FL-GU10-230 Sylvania.jpg",
						"/t TH RA Q40AR40FL-G9-230 Osram Decopin.jpg",
						"/t TH RP Q20PAR20S Electronic Philips 2.jpg",
						"/t TH RP Sylvania 120-90PAR30SP-E26 Gold.jpg"
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
