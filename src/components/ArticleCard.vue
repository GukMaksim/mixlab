<script setup>
defineProps({
	article: {
		type: Object,
		required: true,
		validator: (value) => {
			return value.date && value.title && value.description && value.link && value.image;
		}
	}
});
</script>

<template>
	<article class="article-card" :aria-label="`Article: ${article.title}`">
		<a :href="article.link" class="article-image-link" :aria-label="`Read article: ${article.title}`">
			<img :src="article.image" :alt="article.title" class="article-image" width="384" height="238" loading="lazy">
		</a>
		<div class="article-content">
			<time :datetime="article.date" class="article-date">
				{{ article.date }}
			</time>
			<h3 class="article-title">
				<a :href="article.link" class="article-title-link" :aria-label="`Read article: ${article.title}`">
					{{ article.title }}
				</a>
			</h3>
			<p class="article-description">{{ article.description }}</p>
			<div class="spacer"></div>
			<a :href="article.link" class="article-link" :aria-label="`Read the article: ${article.title}`">
				Read the article
			</a>
		</div>
	</article>
</template>

<style scoped>
.article-card {
	background-color: var(--color-background, #ffffff);
	border-radius: 0.5rem;
	box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
	overflow: hidden;
	max-width: 24rem;
	display: flex;
	flex-direction: column;
	transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.article-card:hover {
	transform: translateY(-0.25rem);
	box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15);
}

.article-card:focus-within {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 0.5rem;
}

.article-image-link {
	display: block;
	overflow: hidden;
}

.article-image {
	width: 100%;
	height: auto;
	object-fit: cover;
	transition: transform 0.3s ease;
}

.article-card:hover .article-image {
	transform: scale(1.05);
}

.article-content {
	display: flex;
	flex-direction: column;
	flex: 1;
	padding: 2.25rem;
	text-align: left;
}

.article-date {
	color: var(--color-accent, #F7A500);
	font-size: 0.9375rem;
	margin-bottom: 1rem;
	font-weight: 500;
}

.article-title {
	font-size: clamp(1.25rem, 2vw, 1.5rem);
	line-height: 1.32;
	margin-bottom: 0.75rem;
}

.article-title-link {
	color: var(--color-text-dark, #1A1A1A);
	text-decoration: none;
	transition: color 0.3s ease;
}

.article-title-link:hover {
	color: var(--color-accent, #F7A500);
}

.article-title-link:focus-visible {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 2px;
}

.article-description {
	font-size: 0.6875rem;
	line-height: 1.42;
	color: var(--color-text, #4A4A4A);
}

.spacer {
	flex-grow: 1;
}

.article-link {
	margin-top: 2rem;
	display: inline-block;
	color: var(--color-purple);
	text-decoration: none;
	font-weight: 500;
	transition: color 0.3s ease;
	position: relative;
}

.article-link::after {
	content: '';
	position: absolute;
	bottom: -2px;
	left: 0;
	width: 100%;
	height: 1px;
	background-color: currentColor;
	transform: scaleX(0);
	transform-origin: right;
	transition: transform 0.3s ease;
}

.article-link:hover {
	color: var(--color-purple-dark);
}

.article-link:hover::after {
	transform: scaleX(1);
	transform-origin: left;
}

.article-link:focus-visible {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 2px;
}

@media (max-width: 768px) {
	.article-content {
		padding: 1.5rem;
	}

	.article-date {
		font-size: 0.875rem;
	}

	.article-description {
		font-size: 0.75rem;
	}
}

@media (max-width: 480px) {
	.article-content {
		padding: 1.25rem;
	}
}

@media (prefers-reduced-motion: reduce) {
	.article-card,
	.article-image,
	.article-title-link,
	.article-link::after {
		transition: none;
	}

	.article-card:hover {
		transform: none;
	}

	.article-card:hover .article-image {
		transform: none;
	}

	.article-link:hover::after {
		transform: none;
	}
}
</style>