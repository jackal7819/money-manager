<script setup>
	import { ref } from 'vue';
	import { nanoid } from 'nanoid';
	import { useToast } from 'vue-toastification';

	const emit = defineEmits(['addTransaction']);

	const text = ref('');
	const amount = ref(0);
	const toast = useToast();

	const onSubmit = () => {
		if (!text.value || !amount.value) {
			toast.error('Both fields must be filled');
			return;
		}

		const transactionData = {
			id: nanoid(),
			text: text.value,
			amount: amount.value,
		};

		emit('addTransaction', transactionData);

		text.value = '';
		amount.value = 0;
	};
</script>

<template>
	<h3 class="text-xl font-bold">Add New Transactions</h3>
	<form id="form" @submit.prevent="onSubmit">
		<div>
			<label for="text" class="text-xl">Text</label>
			<input
				type="text"
				id="text"
				v-model="text"
				placeholder="Enter text..."
				class="w-full px-5 py-2 my-5 rounded outline-none focus:shadow-violet-500 focus:shadow-inner"
			/>
		</div>
		<div>
			<label for="amount" class="text-xl"
				>Amount <br />
				(negative - expense, positive - income)</label
			>
			<input
				type="number"
				id="amount"
				v-model="amount"
				placeholder="Enter amount..."
				class="w-full px-5 py-2 mt-5 rounded outline-none focus:shadow-violet-500 focus:shadow-inner"
			/>
		</div>
		<button
			class="w-full px-5 py-2 mt-8 duration-300 rounded bg-violet-500 text-slate-200 hover:bg-violet-600"
		>
			Add Transaction
		</button>
	</form>
</template>
