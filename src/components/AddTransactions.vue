<script setup></script>

<template>
	<h3 class="text-xl font-bold">Add New Transactions</h3>
	<form id="form">
		<div>
			<label for="text" class="text-xl">Text</label>
			<input
				type="text"
				id="text"
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
				placeholder="Enter amount..."
				class="w-full px-5 py-2 mt-5 rounded outline-none focus:shadow-violet-500 focus:shadow-inner"
			/>
			<button
				class="w-full px-5 py-2 mt-8 duration-300 rounded bg-violet-500 text-slate-200 hover:bg-violet-600"
			>
				Add Transaction
			</button>
		</div>
	</form>
</template>
