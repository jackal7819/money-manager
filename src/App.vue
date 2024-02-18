<script setup>
	import Header from './components/Header.vue';
	import Balance from './components/Balance.vue';
	import IncomeExpenses from './components/IncomeExpenses.vue';
	import TransactionsList from './components/TransactionsList.vue';
	import AddTransactions from './components/AddTransactions.vue';
</script>

<template>
	<main class="flex items-center justify-center min-h-screen text-slate-400 bg-slate-900">
		<div
			class="flex flex-col w-4/5 max-w-xl gap-5 p-10 mx-auto my-10 text-center rounded shadow-lg shadow-slate-400"
		>
			<Header />
			<Balance />
			<IncomeExpenses />
			<TransactionsList />
			<AddTransactions />
		</div>
	</main>
</template>
