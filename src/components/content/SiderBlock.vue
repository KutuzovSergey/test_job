<template>
	<div class="row element">
		<div class="col-3 element__image">
			<img :src="img_src_1" alt="">
		</div>
		<div class="col-6">
			<div class="element__image">
				<img :src="img_src_2" alt="">
			</div>
		</div>
		<div class="col-3 element__image">
			<img :src="img_src_3" alt="">
		</div>
	</div>
</template>

<script>

export default {
	name: 'SiderBlock',
	components: {
	},
	props: {
		img_src_1: {
			type: String,
			required: true,
		},
		img_src_2: {
			type: String,
			required: true,
		},
		img_src_3: {
			type: String,
			required: true,
		},
	},
	data(){
		return{}
	},
	computed: {
	},
	watch: {
	},
	mounted(){
	},
	methods:{
	},
}
</script>

<style scoped lang="scss">
	@import '~bootstrap/dist/css/bootstrap.min.css';
	@import '@/scss/_mixins.scss';
	@import '@/scss/style.scss';

	.element{
		&__image>img{
			width: 100%;
			height: auto;
		}
	}
</style>
