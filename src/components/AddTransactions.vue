<script setup></script>

<template>
	<h3 class="text-xl font-bold">Add New Transactions</h3>
	<form id="form">
		<div class="-mt-5">
			<label for="text">Text</label>
			<input
				type="text"
				id="text"
				placeholder="Enter text..."
				class="rounded outline-none focus:shadow-violet-500 focus:shadow-inner"
			/>
		</div>
		<div>
			<label for="amount"
				>Amount <br />
				(negative - expense, positive - income)</label
			>
			<input
				type="number"
				id="amount"
				placeholder="Enter amount..."
				class="rounded outline-none focus:shadow-violet-500 focus:shadow-inner"
			/>
			<button
				class="w-full px-5 py-2.5 mt-8 duration-300 rounded bg-violet-500 text-slate-200 hover:bg-violet-600"
			>
				Add Transaction
			</button>
		</div>
	</form>
</template>
