<template>
	<div class="tabs">
		<div class="tab" :class="{active : tabActiveIndex == 0}" @click="changeTab(0)">Speedy Bookmarking</div>
		<div class="tab" :class="{active : tabActiveIndex == 1}"  @click="changeTab(1)">Speedy Searching</div>
		<div class="tab" :class="{active : tabActiveIndex == 2}"  @click="changeTab(2)">Easy Sharing</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			tabActiveIndex: 0
		}
	},
	methods: {
		changeTab(val){
			this.tabActiveIndex = val
			this.$emit("tabchange", this.tabActiveIndex)
		}
	}
}
</script>