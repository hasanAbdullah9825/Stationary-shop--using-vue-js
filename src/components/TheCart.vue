<template>
	<div class="row">
		<table class="table ">
			<thead>
				<tr>
					<th scope="col">Product</th>
					<th scope="col">Price</th>
					<th scope="col"></th>
				</tr>
			</thead>
			<tbody>

				<tr v-for="(item,index) in carts" :key="item.id">
					<td>{{item.title}}</td>
					<td>{{item.price}}</td>
					<td><button class="btn btn-sm btn-danger" @click="$emit('delete',index)" >X</button></td>
				</tr>
			</tbody>
			<tfoot>
				<tr><td> Total ${{totalCost}}</td></tr>
			</tfoot>
		</table>
		
	</div>
</template>
<script>
	export default {
		inject:['carts'],
		props:['totalCost']
		
		
		
		
	};
</script>