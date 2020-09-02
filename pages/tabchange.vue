<template>
  <div class="container">
	  <div class="navbar">
	  </div>
	  <div class="body">
		  <div class="tabs-container">
			  <TabIndex @tabchange="changeTab($event)" />
		  </div>
			<div class="tab-contents">
				<div class="tab-content" v-show="tabActiveIndex == 0">
					<div class="image-container" style="background-image: url('/1.svg');"></div>
					<div class="text-container">
						<h1>Bookmark in One Click</h1>
						<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur atque amet laboriosam culpa expedita dolor harum, eius similique odio porro!</p>
						<button>Click me</button>
					</div>
				</div>
				<div class="tab-content" v-show="tabActiveIndex == 1">
					<div class="image-container" style="background-image: url('/2.svg');"></div>
					<div class="text-container">
						<h1>Intelligent Search</h1>
						<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur atque amet laboriosam culpa expedita dolor harum, eius similique odio porro!</p>
						<button>Click me</button>
					</div>
				</div>
				<div class="tab-content" v-show="tabActiveIndex == 2">
					<div class="image-container" style="background-image: url('/3.svg');"></div>
					<div class="text-container">
						<h1>Share Your Bookmarks</h1>
						<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur atque amet laboriosam culpa expedita dolor harum, eius similique odio porro!</p>
						<button>Click me</button>
					</div>
				</div>
			</div>
	  </div>
  </div>
</template>

<script>
import TabIndex from "~/components/TabIndex.vue";
export default {
	components: {
		TabIndex
	},
	data() {
		return {
			tabActiveIndex: 0
		}
	},
	methods: {
		changeTab(val) {
			this.tabActiveIndex = val
		}
	}
}
</script>

<style>

* {
	box-sizing: border-box;
}
.container {
	display: grid;
	grid-template: "navbar"  50px
					"body"  1fr;
	height: 100vh;
}

.navbar{
	background: green;
	grid-area: "navbar";
}

.body {
	grid-area: "body";
	overflow-y: auto;
}

.tabs-container{
	display: flex;
	align-items: center;
	justify-content: center;
	height: 3rem;
	margin-top: 2rem;
}

.tabs{
	display: flex;
	align-items: center;
	padding-left: 2rem;
	padding-right: 2rem;
	width: 80%;
	height: 100%;
}

.tab{
	height: 100%;
	text-align: center;
	flex: 1;
	display: flex;
	align-items: center;
	justify-content: center;
	cursor:pointer ;
	border-bottom: 1px solid rgba(128, 128, 128, 0.53);
	--active-color: orange;
}

.tab.active {
	color: var(--active-color);
	border-bottom: 2px solid var(--active-color);
}

.tab-contents{
	padding-left: 2rem;
	padding-right: 2rem;
}

.tab-content {
	display: grid;
	grid-template-columns: 1fr 1fr;
	gap: 2rem;
	margin-top: 1rem;
	margin-bottom: 1rem;
	height: calc(100vh - 300px);
}

.tab-content .image-container {
	background-position: center center;
	background-size: contain;
	background-repeat: no-repeat;
}

.tab-content .text-container{
	padding: 1rem;
}

.tab-content .text-container h1,
.tab-content .text-container p
{
	margin-bottom: 1rem;
}

.tab-content .text-container button {
	background: #0084ff;
	color: white;
	padding-right: 1rem;
	padding-left: 1rem;
	padding-top: 0.5rem;
	padding-bottom: 0.5rem;
	border:none;
	border-radius: 5px;
}
</style>