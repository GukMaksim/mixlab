<script setup>
import Button from '@/components/buttons/Button.vue';

const steps = [
	{
		id: 1,
		title: 'We receive your prescription',
		text: 'Either your veterinarian sends us a prescription or we reach out to them for you. Whatever is easiest!',
		image: './works-1.png',
		icon: '📋',
		iconLabel: 'Prescription icon'
	},
	{
		id: 2,
		title: 'We deliver your care package',
		text: 'Fast and free next-day delivery, straight to your door. Same-day in NYC and LA.',
		image: './works-2.png',
		icon: '📦',
		iconLabel: 'Delivery package icon'
	},
	{
		id: 3,
		title: 'You treat your pet',
		text: 'Give your pet the care they need to feel better. Plus they can play with our included toy!',
		image: './works-3.png',
		icon: '🐾',
		iconLabel: 'Pet care icon'
	}
];
</script>

<template>
	<section class="how-it-works" aria-labelledby="how-it-works-title">
		<div class="container">
			<div class="how-it-works__inner">
				<h2 id="how-it-works-title" class="how-it-works__title">
					How it works
				</h2>

				<div class="how-it-works__items" role="list" aria-label="Steps to get started">
					<div v-for="step in steps" :key="step.id" class="how-it-works__item" role="listitem"
						:aria-label="`Step ${step.id}: ${step.title}`">
						<div class="how-it-works__item-img-wrapper" :aria-label="step.iconLabel">
							<img :src="step.image" :alt="step.title" class="how-it-works__item-img" width="120" height="120"
								loading="lazy">
							<span class="how-it-works__item-icon" aria-hidden="true" role="img" :aria-label="step.iconLabel">
								{{ step.icon }}
							</span>
						</div>
						<div class="how-it-works__item-info">
							<h3 class="how-it-works__item-title">
								{{ step.title }}
							</h3>
							<p class="how-it-works__item-text">
								{{ step.text }}
							</p>
						</div>
					</div>
				</div>

				<Button text="Learn More" class="how-it-works__button" aria-label="Learn more about our service"
					variant="primary" size="large" />
			</div>
		</div>
	</section>
</template>

<style scoped>
.how-it-works {
	background-color: var(--color-background-light, #FAF9F6);
	padding: 4rem 0;
}

.container {
	max-width: 90rem;
	margin: 0 auto;
	padding: 0 1rem;
}

.how-it-works__inner {
	width: 100%;
	text-align: center;
}

.how-it-works__title {
	font-size: clamp(2rem, 4vw, 3rem);
	line-height: 1.2;
	margin-bottom: 4rem;
	color: var(--color-text-dark, #1A1A1A);
	font-weight: 700;
}

.how-it-works__items {
	display: flex;
	justify-content: center;
	gap: 2.5rem;
	margin-bottom: 4rem;
	flex-wrap: wrap;
}

.how-it-works__item {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 1.5rem;
	text-align: center;
	width: 100%;
	max-width: 22.4375rem;
	padding: 1.5rem;
	background-color: var(--color-background, #ffffff);
	border-radius: 1rem;
	box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
	transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.how-it-works__item:hover {
	transform: translateY(-0.3125rem);
	box-shadow: 0 8px 12px rgba(0, 0, 0, 0.1);
}

.how-it-works__item:focus-within {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 1rem;
}

.how-it-works__item-img-wrapper {
	background-color: var(--color-accent-light, #FFF7C2);
	width: 12rem;
	height: 12rem;
	border-radius: 50%;
	display: flex;
	align-items: center;
	justify-content: center;
	position: relative;
	transition: transform 0.3s ease, background-color 0.3s ease;
}

.how-it-works__item:hover .how-it-works__item-img-wrapper {
	transform: scale(1.05);
	background-color: var(--color-accent, #F7A500);
}

.how-it-works__item-img {
	width: 14rem;
	height: 13rem;
	position: absolute;
	object-fit: contain;
	transition: transform 0.3s ease;
}

.how-it-works__item:hover .how-it-works__item-img {
	transform: scale(1.1);
}

.how-it-works__item-icon {
	position: absolute;
	bottom: 0.5rem;
	right: 0.5rem;
	font-size: 1.5rem;
	background-color: var(--color-background, #ffffff);
	width: 2rem;
	height: 2rem;
	border-radius: 50%;
	display: flex;
	align-items: center;
	justify-content: center;
	box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	transition: transform 0.3s ease;
}

.how-it-works__item:hover .how-it-works__item-icon {
	transform: rotate(10deg);
}

.how-it-works__item-info {
	display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 40%;
}

.how-it-works__item-title {
	color: var(--color-purple);
	font-size: clamp(1.25rem, 2vw, 1.5rem);
	line-height: 1.3;
	margin-bottom: 0.5rem;
}

.how-it-works__item-text {
	font-size: clamp(1rem, 1.5vw, 1.125rem);
	line-height: 1.5;
	color: var(--color-text, #4A4A4A);
}

.how-it-works__button {
	margin-top: 2rem;
}

@media (max-width: 1024px) {
	.how-it-works__items {
		gap: 2rem;
	}
}

@media (max-width: 768px) {
	.how-it-works {
		padding: 3rem 0;
	}

	.how-it-works__title {
		margin-bottom: 3rem;
	}

	.how-it-works__items {
		gap: 1.5rem;
	}

	.how-it-works__item {
		max-width: 20rem;
	}
}

@media (max-width: 480px) {
	.how-it-works {
		padding: 2rem 0;
	}

	.how-it-works__title {
		margin-bottom: 2rem;
	}

	.how-it-works__items {
		gap: 1rem;
	}

	.how-it-works__item {
		padding: 1rem;
	}

	.how-it-works__item-img-wrapper {
		width: 10rem;
		height: 10rem;
	}

	.how-it-works__item-img {
		width: 6.25rem;
		height: 6.25rem;
	}
}

@media (prefers-reduced-motion: reduce) {

	.how-it-works__item,
	.how-it-works__item-img-wrapper,
	.how-it-works__item-img,
	.how-it-works__item-icon {
		transition: none;
	}

	.how-it-works__item:hover {
		transform: none;
	}

	.how-it-works__item:hover .how-it-works__item-img-wrapper,
	.how-it-works__item:hover .how-it-works__item-img,
	.how-it-works__item:hover .how-it-works__item-icon {
		transform: none;
	}
}
</style>
