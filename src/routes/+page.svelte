<script lang="ts">
	import { KemomimiComposer, KnobSlider } from '$lib';

	let kemomimiBottom = $state(100);
	let kemomimiHeight = $state(100);
	let iconSize = $state(100);
	let kemomimiSize = $state(100);
	let theta = $state(60);
	let phi = $state(0);
	let radius = $state(50);
</script>

<KnobSlider label="アイコンの大きさ" min={10} max={200} bind:value={iconSize} />
<KnobSlider label="ミミの大きさ" min={10} max={200} bind:value={kemomimiSize} />
<KnobSlider label="ミミの角度" min={0} max={90} bind:value={theta} />
<KnobSlider label="ミミの角度2" min={-90} max={90} bind:value={phi} />
<KnobSlider label="ミミの底辺 (割合)" min={0} max={100} bind:value={kemomimiBottom} />
<KnobSlider label="ミミの高さ (割合)" min={0} max={100} bind:value={kemomimiHeight} />
<KnobSlider label="アイコン-ミミ間距離" min={10} max={100} bind:value={radius} />

<KemomimiComposer
	{kemomimiBottom}
	{kemomimiHeight}
	{iconSize}
	{kemomimiSize}
	{theta}
	{phi}
	{radius}
	iconColor="lightblue"
	kemomimiColor="lightpink"
/>
