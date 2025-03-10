<script lang="ts">
	export let translations;
	export let language;

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
			<h1>{box.title}</h1>
		{/if}
		{#each Object.keys(box) as key}
			{#if key.includes("subhead")}
				<h2>{box[key]}</h2>
			{/if}
			{#if key.includes("imgs")}
				<div class="img">
					<img src={box[key][0]} alt={box[key][0]} />
					<div>
						<button on:click={() => fullImage(0, boxIndex)}
							>{translations[language].viewFullImage}</button
						>
					</div>
				</div>
			{/if}
			{#if key.includes("description")}
				{#each box[key] as desc}
					<p>{desc}</p>
				{/each}
			{/if}
		{/each}
	</div>
{/each}

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
