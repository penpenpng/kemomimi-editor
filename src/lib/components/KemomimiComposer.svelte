<script lang="ts">
	import DummyIcon from './DummyIcon.svelte';
	import Kemomimi from './Kemomimi.svelte';

	let {
		theta,
		phi,
		radius,
		iconSize,
		iconColor,
		kemomimiSize,
		kemomimiBottom: bottom,
		kemomimiHeight: height,
		kemomimiColor
	}: {
		theta: number;
		phi: number;
		radius: number;
		iconSize: number;
		iconColor: string;
		kemomimiSize: number;
		kemomimiBottom: number;
		kemomimiHeight: number;
		kemomimiColor: string;
	} = $props();
</script>

<div
	class="kemomimi-composer"
	style:--icon-size={`${iconSize}px`}
	style:--icon-color={iconColor}
	style:--kemomimi-size={`${kemomimiSize}px`}
	style:--kemomimi-color={kemomimiColor}
	style:--radius={`${radius}px`}
	style:--theta={`${theta}deg`}
	style:--phi={`${phi}deg`}
>
	<div class="kemomimi centering kemomimi-right">
		<Kemomimi {bottom} {height} />
	</div>
	<div class="kemomimi centering kemomimi-left">
		<Kemomimi {bottom} {height} />
	</div>
	<div class="icon centering">
		<DummyIcon />
	</div>
</div>

<style>
	.kemomimi-composer {
		--box-size: 100px;

		position: relative;
		width: var(--box-size);
		height: var(--box-size);
		margin: 200px;
	}

	.icon {
		--obj-size: var(--icon-size);
	}

	.kemomimi {
		--obj-size: var(--kemomimi-size);
	}

	.centering {
		position: absolute;
		top: calc((var(--box-size) - var(--obj-size)) / 2);
		left: calc((var(--box-size) - var(--obj-size)) / 2);
	}

	.kemomimi-left {
		transform: rotate(var(--theta)) translateX(calc(-1 * var(--radius)))
			rotate(calc(-1 * (90deg + var(--phi))));
	}

	.kemomimi-right {
		transform: rotate(calc(-1 * var(--theta))) translateX(calc(1 * var(--radius)))
			rotate(calc(1 * (90deg + var(--phi))));
	}
</style>
