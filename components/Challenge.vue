<template>
	<div class="challenge">
		<Playground class="playground" :eventBus="evtBus" position="left" />
		<Playground class="playground" :eventBus="evtBus" position="right" />
	</div>
</template>

<script>
import Vue from "vue";

import Playground from "./Playground";

export default {
	name: "Challenge",

	components: { Playground },

	data: () => ({
		evtBus: new Vue() // Creat a global event bus
	})
};
</script>

<style scoped>
	.challenge {
		display: flex;
		justify-content: space-around;
		align-items: center;
	}

	.playground {
		text-align: center;
	}
</style>
