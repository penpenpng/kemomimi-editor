<script lang="ts">
	let {
		value = $bindable(),
		min,
		max,
		label
	}: { value: number; min: number; max: number; label: string } = $props();
</script>

<div>
	<label>
		<span class="label-text">{label}</span>
		<input type="range" {min} {max} bind:value />
	</label>
	{value}
</div>

<style>
	label {
		display: inline flow-root;
	}

	.label-text {
		display: inline flow-root;
		width: 200px;
		text-align: right;
	}
</style>
