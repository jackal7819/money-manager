<script setup>
	defineProps({
		transactions: {
			type: Array,
			required: true,
		},
	});
	
	const emit = defineEmits(['deleteTransaction']);
	const deleteTransaction = (id) => {
		emit('deleteTransaction', id);
	}
</script>

<template>
	<h3 class="text-xl font-bold">Transactions</h3>
	<ul id="list" class="flex flex-col gap-3">
		<li
			v-for="transaction in transactions"
			:key="transaction.id"
			:class="
				transaction.amount > 0 ? 'shadow-green-500' : 'shadow-red-500'
			"
			class="relative flex justify-between px-5 py-1 rounded shadow group"
		>
			{{ transaction.text }}
			<span>{{ transaction.amount.toFixed(2) }}€</span
			><button
				@click="deleteTransaction(transaction.id)"
				class="absolute text-red-500 transition-all duration-1000 opacity-0 -left-5 group-hover:opacity-100"
			>
				&#10006;
			</button>
		</li>
	</ul>
</template>
