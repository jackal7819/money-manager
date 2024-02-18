<script setup>
	defineProps({
		total: {
			type: Number,
			required: true,
		},
	});
</script>

<template>
	<h4 class="text-xl font-bold underline uppercase underline-offset-4">
		Your Balance
	</h4>
	<h1 class="text-3xl font-semibold">{{ total.toFixed(2) }}€</h1>
</template>
