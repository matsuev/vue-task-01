<template>
	<h2>Messages View Component</h2>
	<div>Selected user ID: {{ selectedUserId }}</div>
	<user-list @userSelect="onUserSelect" :users="users"></user-list>
	<message-list :msgs="filteredMessages"></message-list>
</template>

<script>
import UserList from "../components/UserList.vue";
import MessageList from "../components/MessageList.vue";

import { users } from "../dataset/users";
import { messages } from "../dataset/messages";

export default {
	data() {
		return {
			selectedUserId: 0,
			users: users,
			messages: messages,
		};
	},

	components: {
		UserList,
		MessageList,
	},

	computed: {
		filteredMessages() {
			return this.messages.filter(
				(item) => item.from == this.selectedUserId
			);
		},
	},

	methods: {
		onUserSelect(id) {
			this.selectedUserId = id;
		},
	},
};
</script>



