<template>
	<h3>Messages List</h3>
	<hr />
	<div>
		<message-frame v-for="item in msgs" :key="item.id" :msg="item" />
	</div>
</template>

<script>
import MessageFrame from "./MessageFrame.vue";
export default {
	props: ["msgs"],
	components: {
		MessageFrame,
	},
};
</script>