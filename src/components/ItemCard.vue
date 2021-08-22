<template>
	<div class="col-md-4">
		<div class="card m-1">
			<img class="card-img-top" :src="photo" alt="Card image cap" />
			<div class="card-body">
				<h5 class="card-title">
					<slot name="title">{{ title }}</slot>
				</h5>
				<h1>
					<p class="card-text text-success font-weight-bold">
						price: $ <slot name="price">{{ price }}</slot>
					</p>
				</h1>
	
				<button class="btn btn-primary" @click="addCart(id)">
                Add To Cart
				</button>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: ["id", "title", "photo", "price"],
		inject:['addCart'],
		
		
	};
</script>

st