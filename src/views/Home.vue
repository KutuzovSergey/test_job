<template>
	<div class="home container-fluid">
		<SliderSection />
		<ContentSection />
	</div>
</template>

<script>
import SliderSection from '@/components/SliderSection.vue'
import ContentSection from '@/components/ContentSection.vue'
export default {
	name: 'Home',
	components: {
		SliderSection,
		ContentSection,
	}
}
</script>
<style scoped lang="scss">
	@import '@/scss/style.scss';
	@import '@/scss/fonts.scss';

	.home{
		height: auto;
	}

</style>