<script setup>
defineProps({
	article: {
		type: Object,
		required: true
	}
});
</script>

<template>
	<div class="article-card">
		<img :src="article.image" alt="">
		<div class="article-info">
			<div class="article-info-inner">
				<p class="article-date">{{ article.date }}</p>
				<h3 class="article-title">{{ article.title }}</h3>
				<p class="article-description">{{ article.description }}</p>
			</div>
			<a :href="article.link">Read the article</a>
		</div>
	</div>
</template>

<style scoped>
.article-card {
	max-width: 384px;
}

.article-info {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	height: 247px;
	text-align: left;
	background-color: #FFFFFF;
	padding: 36px;
}

.article-date {
	color: #F7A500;
	font-size: 15px;
	margin-bottom: 16px;
}

.article-title {
	font-size: 24px;
	line-height: 31.68px;
}

.article-description {
	font-size: 11px;
	line-height: 22.72px;
}
</style>