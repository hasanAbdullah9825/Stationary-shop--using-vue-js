<template>
	<base-container>
		<template #product>
			<item-card
				v-for="(product, index) in products"
				:key="product.id"
				:id="index"
				:title="product.title"
				:photo="product.photo"
				:price="product.price"
			>
			</item-card>
		</template>

		<template #cart>
			<the-cart @delete="deteteFromCart" :totalCost="this.totalCost">
			</the-cart>
		</template>
	</base-container>
</template>
<script>
	import ItemCard from "./ItemCard.vue";
	import BaseContainer from "./BaseContainer.vue";
	import TheCart from "./TheCart.vue";

	export default {
		components: {
			ItemCard,
			BaseContainer,
			TheCart
		},
		data() {
			return {
				products: [
					{
						id: 1,
						title:
							"sunt aut facere repellat provident occaecati excepturi optio reprehenderit",

						photo: "https://via.placeholder.com/600/771796",
						price: "6.08",
						Cart: false
					},
					{
						id: 2,
						title: "qui est esse",

						photo: "https://via.placeholder.com/600/771796",
						price: "20",
						Cart: false
					},
					{
						id: 3,
						title: "ea molestias quasi exercitationem repellat qui ipsa sit aut",

						photo: "https://via.placeholder.com/600/771796",
						price: "80",
						Cart: false
					},
					{
						id: 4,
						title: "eum et est occaecati",

						photo: "https://via.placeholder.com/600/771796",
						price: "21",
						Cart: false
					},
					{
						id: 5,
						title: "nesciunt quas odio",

						photo: "https://via.placeholder.com/600/771796",
						price: "23",
						Cart: false
					},
					{
						id: 6,
						title: "dolorem eum magni eos aperiam quia",

						photo: "https://via.placeholder.com/600/771796",
						price: "53",
						Cart: false
					},
					{
						id: 7,
						title: "magnam facilis autem",

						photo: "https://via.placeholder.com/600/771796",
						price: "31",
						Cart: false
					},
					{
						id: 8,
						title: "dolorem dolore est ipsam",

						photo: "https://via.placeholder.com/600/771796",
						price: "11",
						Cart: false
					},
					{
						id: 9,
						title: "nesciunt iure omnis dolorem tempora et accusantium",

						photo: "https://via.placeholder.com/600/771796",
						price: "21",
						Cart: false
					}
				],
				totalPrice: 0,
				cart: []
			};
		},
		computed: {
			totalCost() {
				let total = 0;
				this.cart.forEach(function(CartItem) {
					return (total += parseFloat(CartItem.price));
				});
				return total;
			}
		},
		methods: {
			addCart(index) {
				const product = this.products[index];
				const cartObj = {
					id: new Date().toISOString,
					title: product.title,
					photo: product.photo,
					price: product.price
				};
				this.cart.push(cartObj);
			},

			deteteFromCart(removeIndex) {
				this.totalPrice -= parseFloat(this.cart[removeIndex].price);
				this.cart.splice(removeIndex, 1);
			}
		},
		provide() {
			return {
				addCart: this.addCart,
				carts: this.cart
				
			};
		}
	};
</script>
<style scoped>
</style>