<script setup lang="ts">
import type { Comment } from '../model/Comment';
import PublishDate from 'shared/ui/PublishDate.vue';

const { comment } = defineProps<{ comment: Comment }>();

defineSlots<{ remove: () => void }>();
</script>

<template>
	<article class="card">
		<div class="avatar" />

		<div class="content">
			<div class="user-name">{{ comment.user.fullName }}</div>

			<div class="body">{{ comment.body }}</div>

			<div class="footer">
				<PublishDate :date="comment.date" />

				<slot name="remove" />
			</div>
		</div>
	</article>
</template>

<style scoped>
.card {
	display: flex;
	gap: 8px;
	color: var(--color-text);
}
.avatar {
	height: 46px;
	width: 46px;
	border-radius: 50%;
	border: 3px solid var(--color-text);
	flex-shrink: 0;
}
.user-name {
	font-size: var(--text-size-primary);
	font-weight: bold;
}
.body {
	font-size: var(--text-size-primary);
	margin-top: 12px;
}
.footer {
	margin-top: 16px;
	display: flex;
	gap: 20px;
	align-items: center;
}
</style>
