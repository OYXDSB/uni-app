<template>
	<view class="box">{{title}}</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style scoped lang="scss">
	.box{
		width: 100%;
		height: 300px;
		background: blue;
	}
</style>
