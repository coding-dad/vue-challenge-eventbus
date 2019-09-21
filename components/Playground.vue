<template>
	<div class="playground">
		<canvas @click="canvasClicked" ref="myCanvas"></canvas>
	</div>
</template>

<script>
export default {
	name: "Playground",

	props: ["position", "eventBus"],

	data: () => ({
		canvasWidth: 260,
		canvasHeight: 200,
		ctx: null
	}),

	methods: {
		/**
		 * If canvas was clicked, send an event along the event bus
		 * The actual event handling takes place when we ourselves
		 * receive the event from the bus
		 */
		canvasClicked(evt) {
			this.eventBus && this.eventBus.$emit("canvasClick", evt);
		},

		/**
		 * Handles the drawing
		 * Will be called, whenever an 'canvasClick' event was received
		 */
		onEventBusClickEvent(evt) {
			if (this.position === "left") {
				this.ctx.fillStyle = "#ff0000";
				this.ctx.fillRect(evt.offsetX - 6, evt.offsetY - 6, 12, 12);
			} else {
				this.ctx.fillStyle = "#0000ff";
				this.ctx.beginPath();
				this.ctx.arc(evt.offsetX, evt.offsetY, 6, 0, 2 * Math.PI);
				this.ctx.fill();
			}
		}
	},

	mounted() {
		this.eventBus &&
			this.eventBus.$on("canvasClick", evt => {
				this.onEventBusClickEvent(evt);
			});

		this.$refs.myCanvas.width = this.canvasWidth;
		this.$refs.myCanvas.height = this.canvasHeight;

		this.ctx = this.$refs.myCanvas.getContext("2d");

		this.ctx.fillStyle = "#e2e2e2";
		this.ctx.fillRect(0, 0, this.canvasWidth, this.canvasHeight);
	}
};
</script>

<style scoped>
	.playground {
		box-sizing: border-box;
	}
</style>