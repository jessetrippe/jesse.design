---
layout: invoice
title: "Charles Perry - 08-06-2021"
---

<header class="grid grid-cols-4 mb-6">
	<div class="col-span-2 col-start-2 flex flex-col items-center">
		<span class="text-white bg-black rounded-full p-1 mb-2">{% include jt.svg class="h-16 w-16" %}</span>
		<span class="font-bold uppercase">Jesse Trippe</span>
	</div>
	<p class="">
		Jesse Trippe<br>
		3019 62nd Ave SW, Unit D<br>
		Seattle, WA 98116<br>
		734-649-6602<br>
		jesse@jessetrippe.com
	</p>
</header>
<div class="mb-6">
	<h1 class="font-bold uppercase mb-2">Invoice #3</h1>
	<div>August 06, 2021</div>
	<div>Charles Perry</div>
	<div>RelaNet LLC</div>
	<div>12175 Visionary Way Suite 950</div>
	<div>Fishers, IN 46038</div>
</div>
<table class="w-full mb-6">
	<thead>
		<tr>
			<th class="py-2 px-3 text-left bg-gray-200">Description</th>
			<th class="py-2 px-3 text-left bg-gray-200">Hours</th>
			<th class="py-2 px-3 text-left bg-gray-200">Price</th>
			<th class="py-2 px-3 text-left bg-gray-200">Total</th>
		</tr>
	</thead>
	<tbody id="invoice-tbody">
		<tr class="border-gray-200 border-b-2">
			<td class="py-2 px-3">Theme setup and install</td>
			<td class="py-2 px-3 text-right" data-value="quantity">.25</td>
			<td class="py-2 px-3 text-right" data-value="price">75.00</td>
			<td class="py-2 px-3 text-right font-bold" data-value="total"></td>
		</tr>
		<tr class="border-gray-200 border-b-2">
			<td class="py-2 px-3">Investigate console errors</td>
			<td class="py-2 px-3 text-right" data-value="quantity">1.00</td>
			<td class="py-2 px-3 text-right" data-value="price">75.00</td>
			<td class="py-2 px-3 text-right font-bold" data-value="total"></td>
		</tr>
		<tr class="border-gray-200 border-b-2">
			<td class="py-2 px-3">Implement and test solution</td>
			<td class="py-2 px-3 text-right" data-value="quantity">.25</td>
			<td class="py-2 px-3 text-right" data-value="price">75.00</td>
			<td class="py-2 px-3 text-right font-bold" data-value="total"></td>
		</tr>
	</tbody>
	<tfoot id="invoice-tfoot">
		<tr>
			<th></th>
			<th colspan="2" class="py-2 px-3 text-left border-gray-200 border-b-2">Subtotal</th>
			<th class="py-2 px-3 text-right border-gray-200 border-b-2">0</th>
		</tr>
		<tr>
			<th></th>
			<th colspan="2" class="py-2 px-3 text-left border-gray-200 border-b-2">Tax</th>
			<th class="py-2 px-3 text-right border-gray-200 border-b-2">$0.00</th>
		</tr>
		<tr>
			<th></th>
			<th colspan="2" class="py-2 px-3 text-left border-gray-200 border-b-2">Total</th>
			<th class="py-2 px-3 text-right border-gray-200 border-b-2">0</th>
		</tr>
	</tfoot>
</table>
<div class="mb-6">
	<h2 class="font-bold uppercase mb-2">Payment Terms</h2>
	<p class="max-w-4xl">Please remit payment within 60 days to the address above. If you have any questions please contact me. Thanks a ton, I really appreciate your present (and future) business.</p>
</div>
<div>
	<h2 class="font-bold uppercase mb-2">Payment Information</h2>
	<p>
		Paypal: paypal.me/jessetrippe<br>
		Venmo: @JesseTrippe<br>
		Square Cash: $jessetrippe
	</p>
</div>
<script>
	const tbody = document.getElementById("invoice-tbody");
	let totalAmount = 0;

	Array.from(tbody.rows).forEach((row) => {
	   let quantity = parseFloat(row.cells[1].innerHTML);
	   let price = 75; // hourly rate
	   let total = quantity * price;
	   totalAmount = parseFloat(total + totalAmount);
	   row.cells[3].innerHTML = "$" + total.toFixed(2);
	   row.cells[2].innerHTML = "$" + price.toFixed(2);
	});

	const tfoot = document.getElementById("invoice-tfoot");

	tfoot.rows[0].cells[2].innerHTML = "$" + totalAmount.toFixed(2);
	tfoot.rows[2].cells[2].innerHTML = "$" + totalAmount.toFixed(2);
</script>
