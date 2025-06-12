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
		<img :src="article.image" alt="" class="article-image">
		<div class="article-content">
				<p class="article-date">{{ article.date }}</p>
				<h3 class="article-title">{{ article.title }}</h3>
				<p class="article-description">{{ article.description }}</p>
				<div class="spacer"></div>
			<a :href="article.link" class="article-link">Read the article</a>
		</div>
	</div>
</template>

<style scoped>
.article-card {
	background-color: #ffffff;
	border-radius: 8px;
	box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1 );
	overflow: hidden;
	max-width: 384px;
	display: flex;
	flex-direction: column;
}
.article-image {
	width: 100%;
	height: 238px;
	object-fit: cover;
}

.article-content {
	display: flex;
	flex-direction: column;
	flex: 1;
	padding: 36px;
	text-align: left;
}

.article-date {
	color: #F7A500;
	font-size: 15px;
	margin-bottom: 16px;
}

.article-title {
	font-size: 24px;
	line-height: 31.68px;
	margin-bottom: 12px;
}

.article-description {
	font-size: 11px;
	line-height: 22.72px;
}

.spacer {
	flex-grow: 1;
}

.article-link {
	margin-top: 32px;
	display: inline-block;
}
</style>