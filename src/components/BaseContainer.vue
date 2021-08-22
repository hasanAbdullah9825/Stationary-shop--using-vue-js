<template>
	<div class="container">
		<div class="row">
			<div class="col-md-8">
				<div class="row">
					<slot name="product"> </slot>
				</div>
			</div>
			<div class="col-md-4">
				<ul class="list-group list-group-flush">
					<slot name="cart"> </slot>
				</ul>
			</div>
		</div>
	</div>
</template>