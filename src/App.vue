<script setup>
	import { ref, computed } from 'vue';
	import Header from './components/Header.vue';
	import Balance from './components/Balance.vue';
	import IncomeExpenses from './components/IncomeExpenses.vue';
	import TransactionsList from './components/TransactionsList.vue';
	import AddTransactions from './components/AddTransactions.vue';

	const transactions = ref([
		{ id: 1, text: 'Flower', amount: -20.99 },
		{ id: 2, text: 'Salary', amount: 300.67 },
		{ id: 3, text: 'Book', amount: -10 },
		{ id: 4, text: 'Camera', amount: 150 },
	]);

	const total = computed(() => {
		return transactions.value.reduce((acc, curr) => {
			return acc + curr.amount;
		}, 0);
	});

	const income = computed(() => {
		return transactions.value
			.filter((transaction) => transaction.amount > 0)
			.reduce((acc, curr) => {
				return acc + curr.amount;
			}, 0);
	});

	const expenses = computed(() => {
		return transactions.value
			.filter((transaction) => transaction.amount < 0)
			.reduce((acc, curr) => {
				return acc + curr.amount;
			}, 0);
	});
</script>

<template>
	<main
		class="flex items-center justify-center min-h-screen text-slate-400 bg-slate-900"
	>
		<div
			class="flex flex-col w-4/5 max-w-xl gap-5 p-10 mx-auto my-10 text-center rounded shadow-lg shadow-slate-400"
		>
			<Header />
			<Balance :total="total" />
			<IncomeExpenses :income="income" :expenses="expenses" />
			<TransactionsList :transactions="transactions" />
			<AddTransactions />
		</div>
	</main>
</template>
