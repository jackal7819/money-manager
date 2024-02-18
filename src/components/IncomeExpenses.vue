<script setup>
	defineProps({
		income: {
			type: Number,
			required: true,
		},
		expenses: {
			type: Number,
			required: true,
		},
	});
</script>

<template>
	<div
		class="flex items-center gap-5 p-3 text-center border-b shadow border-slate-400 justify-evenly"
	>
		<div>
			<h4 class="uppercase">Income</h4>
			<p id="money-plus" class="text-green-500">
				+{{ income.toFixed(2) }}€
			</p>
		</div>
		<div class="w-[1px] bg-slate-400 h-10"></div>
		<div class="text">
			<h4 class="uppercase">Expense</h4>
			<p id="money-minus" class="text-red-500">
				-{{ Math.abs(expenses).toFixed(2) }}€
			</p>
		</div>
	</div>
</template>
