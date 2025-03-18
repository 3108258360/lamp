<script lang="ts">
	export let translations;
	export let language;
	export let showContents: boolean;
	let contents = true;

	let fullImageViewState = {
		isVisible: false,
		boxIndex: 0,
		imageIndex: 0
	};

	const fullImage = (direction = 0, boxIndex: number) => {
		if (!fullImageViewState.isVisible) {
			fullImageViewState.imageIndex = 0;
		}
		if (direction === -1) {
			fullImageViewState.imageIndex =
				(fullImageViewState.imageIndex - 1 + translations[language].boxes[boxIndex].imgs.length) %
				translations[language].boxes[boxIndex].imgs.length;
		} else if (direction === 1) {
			fullImageViewState.imageIndex =
				(fullImageViewState.imageIndex + 1) % translations[language].boxes[boxIndex].imgs.length;
		} else {
			fullImageViewState.isVisible = !fullImageViewState.isVisible;
			fullImageViewState.boxIndex = boxIndex;
		}
	};

	const closeFullImage = () => {
		fullImageViewState.isVisible = false;
	};
</script>

{#each translations[language].boxes as box, boxIndex}
	<div class="box">
		{#if box.title}
			<h1 id={box.title}>{box.title}</h1>
		{/if}
		{#if box.subhead}
			<h2 id={box.subhead}>{box.subhead}</h2>
		{/if}
		{#if box.imgs}
			<div class="img">
				<img src={box.imgs[0]} alt={box.imgs[0]} />
				<div>
					<button on:click={() => fullImage(0, boxIndex)}
						>{translations[language].viewFullImage}</button
					>
				</div>
			</div>
		{/if}
		{#if box.description}
			{#each box.description as desc}
				<p>{desc}</p>
			{/each}
		{/if}
	</div>
{/each}

{#if showContents}
	<div class="contents">
		{#each translations[language].boxes as box}
			{#if box.title}
				<a href={"#" + box.title}><h1>{box.title}</h1></a>
			{/if}
			{#if box.subhead}
				<a href={"#" + box.subhead}><h2>{box.subhead}</h2></a>
			{/if}
		{/each}
	</div>
{/if}

{#if fullImageViewState.isVisible}
	<div class="full-image">
		<button on:click={() => fullImage(-1, fullImageViewState.boxIndex)} class="nav-button"
			>{"<"}</button
		>
		<img
			src={translations[language].boxes[fullImageViewState.boxIndex].imgs[
				fullImageViewState.imageIndex
			].replace(/_Min/, "")}
			alt={translations[language].boxes[fullImageViewState.boxIndex].imgs[
				fullImageViewState.imageIndex
			].replace(/_Min/, "")}
		/>
		<button on:click={() => fullImage(1, fullImageViewState.boxIndex)} class="nav-button"
			>{">"}</button
		>
		<button on:click={closeFullImage} class="close-button">{translations[language].close}</button>
	</div>
{/if}
