<template>
	<div class="content">
		<header>
			<h1 class="header">
				<NuxtLink class="header-link" href="/">ikakprosto.ru</NuxtLink>
			</h1>
		</header>

		<main class="main">
			<slot />
		</main>
	</div>
</template>

<style scoped>
.content {
	padding: 16px 24px 64px;
	display: flex;
	align-items: center;
	flex-direction: column;
}
.header {
	font-size: var(--text-size-h1);
}
.header-link {
	color: var(--color-accent-primary);
	text-decoration: none;
}
.main {
	max-width: 676px;
	margin-top: 58px;
}
</style>
