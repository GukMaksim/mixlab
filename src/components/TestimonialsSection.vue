<script setup>
import 'vue3-carousel/carousel.css'
import { Carousel, Slide } from 'vue3-carousel'

const carouselConfig = {
	itemsToShow: 1.3,
	gap: 80,
	autoplay: 4000,
	pauseAutoplayOnHover: true,
	wrapAround: true,
	snapAlign: 'center',
	transition: 500,
	modelValue: 0,
	breakpointMode: 'carousel',
	breakpoints: {
		1700: {
			itemsToShow: 1.8
		}
	}
}

const slides = [
	{
		id: 1,
		img: './testimonials-slide1.png',
		text: 'Tootsie just received her Mixlab order and she\'s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it\'s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can\'t wait to place her next order now!',
		author: 'Tootsie, CA',
		rating: 5
	},
	{
		id: 2,
		img: './testimonials-slide1.png',
		text: 'Tootsie just received her Mixlab order and she\'s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it\'s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can\'t wait to place her next order now!',
		author: 'Tootsie, CA',
		rating: 5
	},
	{
		id: 3,
		img: './testimonials-slide1.png',
		text: 'Tootsie just received her Mixlab order and she\'s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it\'s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can\'t wait to place her next order now!',
		author: 'Tootsie, CA',
		rating: 5
	}
]
</script>

<template>
	<section class="testimonials" aria-labelledby="testimonials-title">
		<img class="testimonials__img-right" src="@/assets/testimonials-img.png" alt="Decorative hearts" width="100"
			height="100" loading="lazy">

		<h2 id="testimonials-title" class="testimonials__title">
			Pets love Mixlab!
		</h2>

		<p class="testimonials__subtitle">
			See why we're 5 stars on
			<a href="#" class="testimonials__link" aria-label="Read our reviews on Yelp">Yelp</a>,
			<a href="#" class="testimonials__link" aria-label="Read our reviews on Google">Google</a> and
			<a href="#" class="testimonials__link" aria-label="Read our reviews on Facebook">Facebook</a>
		</p>

		<div class="testimonials__carousel-wrapper" role="region" aria-label="Customer testimonials">
			<Carousel v-bind="carouselConfig" aria-label="Customer testimonials">
				<Slide v-for="slide in slides" :key="slide.id" class="testimonials__slide">
					<div class="slide__item" :aria-label="`Testimonial from ${slide.author}`">
						<img class="slide__img" :src="slide.img" :alt="`${slide.author}'s pet`" width="240" height="240"
							loading="lazy">
						<div class="slide__info">
							<div class="slide__rating" :aria-label="`${slide.rating} out of 5 stars`">
								<span v-for="n in slide.rating" :key="n" class="slide__star" aria-hidden="true">
									★
								</span>
							</div>
							<blockquote class="slide__text">
								{{ slide.text }}
							</blockquote>
							<p class="slide__author">
								<img src="@/assets/icons/icon_insta.png" alt="Instagram icon" class="slide__author-icon" width="22"
									height="22" loading="lazy">
								{{ slide.author }}
							</p>
						</div>
					</div>
				</Slide>
			</Carousel>
		</div>
	</section>
</template>

<style scoped>
.testimonials {
	padding: 4rem 0;
	position: relative;
	text-align: center;
	background-color: var(--color-background, #ffffff);
}

.testimonials__title {
	font-size: clamp(2rem, 4vw, 3rem);
	line-height: 1.2;
	font-weight: 700;
	color: var(--color-text-dark, #1A1A1A);
}

.testimonials__subtitle {
	margin-top: 1.5rem;
	font-size: clamp(1rem, 1.5vw, 1.25rem);
	color: var(--color-text, #4A4A4A);
}

.testimonials__link {
	color: var(--color-purple);
	text-decoration: none;
	transition: color 0.3s ease;
	position: relative;
	font-weight: 500;
}

.testimonials__link::after {
	content: '';
	position: absolute;
	bottom: -2px;
	left: 0;
	width: 0;
	height: 1px;
	background-color: var(--color-purple);
	transition: width 0.3s ease;
}

.testimonials__link:hover {
	color: var(--color-purple-hover);
}

.testimonials__link:hover::after {
	width: 100%;
}

.testimonials__link:focus-visible {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 2px;
}

.testimonials__img-right {
	position: absolute;
	top: 2.5rem;
	right: 4rem;
	z-index: 2;
	width: auto;
	height: auto;
	max-width: 6.25rem;
}


.testimonials__carousel-wrapper {
	margin-top: 3rem;
	padding: 1.5rem 0 6.5rem;
}

.testimonials__slide {
	padding: 0 1rem;
}

.slide__item {
	display: flex;
	align-items: center;
	background-color: var(--color-background-light, #DFF5F6);
	border-radius: 1rem;
	padding: 2rem;
	box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
	transition: transform 0.3s ease, box-shadow 0.3s ease;
}



.slide__item:focus-within {
	outline: 2px solid var(--color-purple);
	outline-offset: 4px;
	border-radius: 1rem;
}

.slide__img {
	width: 15rem;
	height: 15rem;
	border-radius: 50%;
	object-fit: cover;
	box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
	transition: transform 0.3s ease;
}

.slide__info {
	padding-left: 2rem;
	text-align: left;
	flex: 1;
}

.slide__rating {
	margin-bottom: 1rem;
}

.slide__star {
	color: var(--color-accent, #F7A500);
	font-size: 1.25rem;
	margin-right: 0.25rem;
}

.slide__text {
	font-size: clamp(1rem, 1.5vw, 1.125rem);
	line-height: 1.5;
	color: var(--color-text, #4A4A4A);
	margin-bottom: 1rem;
	font-style: italic;
}

.slide__author {
	font-size: 1.25rem;
	line-height: 1.5;
	display: flex;
	align-items: center;
	gap: 1rem;
	color: var(--color-text-dark, #1A1A1A);
	font-weight: 500;
}

.slide__author-icon {
	width: 1.375rem;
	height: 1.375rem;
	transition: transform 0.3s ease;
}


@media (max-width: 1024px) {
	.testimonials__img-right {
		right: 2rem;
	}
}

@media (max-width: 768px) {
	.testimonials {
		padding: 3rem 0;
	}

	.testimonials__img-right {
		display: none;
	}

	.slide__item {
		flex-direction: column;
		text-align: center;
		padding: 1.5rem;
	}

	.slide__info {
		padding-left: 0;
		padding-top: 1.5rem;
		text-align: center;
	}

	.slide__img {
		width: 12rem;
		height: 12rem;
	}
}

@media (max-width: 480px) {
	.testimonials {
		padding: 2rem 0;
	}

	.testimonials__carousel-wrapper {
		margin-top: 2rem;
		padding: 1rem 0 4rem;
	}

	.slide__item {
		padding: 1rem;
	}

	.slide__img {
		width: 10rem;
		height: 10rem;
	}

	.slide__text {
		font-size: 0.875rem;
	}
}

@media (prefers-reduced-motion: reduce) {

	.testimonials__img-right,
	.testimonials__link::after,
	.slide__item,
	.slide__img,
	.slide__author-icon {
		transition: none;
	}


}
</style>