<script setup></script>

<template>
	<h3 class="text-xl font-bold">Transactions</h3>
	<ul id="list" class='flex flex-col gap-3'>
		<li class="relative flex justify-between px-5 py-1 rounded shadow group shadow-red-500">
			Cash <span>-€400.00</span><button class="absolute text-red-500 transition-all duration-1000 opacity-0 -left-5 group-hover:opacity-100">&#10006;</button>
		</li>
		<li class="relative flex justify-between px-5 py-1 rounded shadow group shadow-red-500">
			Cash <span>-€40.00</span><button class="absolute text-red-500 transition-all duration-1000 opacity-0 -left-5 group-hover:opacity-100">&#10006;</button>
		</li>
		<li class="relative flex justify-between px-5 py-1 rounded shadow group shadow-green-500">
			Paycheck <span>+€400.00</span
			><button class="absolute text-red-500 transition-all duration-1000 opacity-0 -left-5 group-hover:opacity-100">&#10006;</button>
		</li>
	</ul>
</template>
