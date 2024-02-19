<script setup>
	import { ref, computed, onMounted } from 'vue';
	import { useToast } from 'vue-toastification';
	import Header from './components/Header.vue';
	import Balance from './components/Balance.vue';
	import IncomeExpenses from './components/IncomeExpenses.vue';
	import TransactionsList from './components/TransactionsList.vue';
	import AddTransactions from './components/AddTransactions.vue';

	const toast = useToast();
	const transactions = ref([]);

	const addTransaction = (transactionData) => {
		transactions.value.push(transactionData);
		localStorage.setItem('transactions', JSON.stringify(transactions.value));
		toast.success('Transaction added');
	};

	const deleteTransaction = (id) => {
		transactions.value = transactions.value.filter(
			(transaction) => transaction.id !== id
		);
		localStorage.setItem('transactions', JSON.stringify(transactions.value));
		toast.error('Transaction deleted');
	};

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

	onMounted(() => {
		transactions.value = JSON.parse(localStorage.getItem('transactions')) || [];
	})
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
			<TransactionsList
				:transactions="transactions"
				@deleteTransaction="deleteTransaction"
			/>
			<AddTransactions @addTransaction="addTransaction" />
		</div>
	</main>
</template>
