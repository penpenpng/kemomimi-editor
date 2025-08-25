<script lang="ts">
	let { bottom = 100, height = 100 }: { bottom: number; height: number } = $props();

	const box = 100;
	const viewBox = `0 0 ${box} ${box}`;
	const scale = (value: number) => (value * box) / 100;

	const top = $derived(`${box / 2},${box - scale(height)}`);
	const left = $derived(`${(box + scale(bottom)) / 2},${box}`);
	const right = $derived(`${(box - scale(bottom)) / 2},${box}`);
	const points = $derived(`${top} ${left} ${right}`);
</script>

<svg {viewBox} xmlns="http://www.w3.org/2000/svg">
	<polygon {points} />
</svg>

<style>
	svg {
		--kemomimi-size-default: 100px;
		--kemomimi-color-default: pink;

		width: var(--kemomimi-size, var(--kemomimi-size-default));
		height: var(--kemomimi-size, var(--kemomimi-size-default));
		fill: var(--kemomimi-color, var(--kemomimi-color-default));
	}
</style>
