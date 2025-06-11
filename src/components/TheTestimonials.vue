<script setup>
import 'vue3-carousel/carousel.css'
import { Carousel, Slide } from 'vue3-carousel'

const carouselConfig = {
	itemsToShow: 1.3,
	gap: 80,
	autoplay: 4000,
	pauseAutoplayOnHover: true,
	wrapAround: true
}

const slides = [
	{
		id: 1,
		img: 'https://picsum.photos/240',
		text: '“Tootsie just received her Mixlab order and she’s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it’s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can’t wait to place her next order now!”',
		author: 'Tootsie, CA',
	},
	{
		id: 2,
		img: 'https://picsum.photos/240',
		text: '“Tootsie just received her Mixlab order and she’s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it’s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can’t wait to place her next order now!”',
		author: 'Tootsie, CA',
	},
	{
		id: 3,
		img: 'https://picsum.photos/240',
		text: '“Tootsie just received her Mixlab order and she’s so excited for it! Within two hours of ordering it got delivered to the house and its like she knew it was at the door. She absolutely hates taking her medicine but she truly loves her Mixlab box because it’s so informative, quick, easy to order but especially because includes a new toy each time! Thank you Mixlab for always taking care of her! She can’t wait to place her next order now!”',
		author: 'Tootsie, CA',
	},
]
</script>

<template>
	<section class="testimonials">
		<img class="testimonials__img-right" src="@/assets/testimonials-img.png" alt="hearts">
		<h2 class="testimonials__title">Pets love Mixlab!</h2>
		<p class="testimonials__subtitle">See why we're 5 stars on <a href="#">Yelp</a>, <a href="#">Google</a> and <a
				href="#">Facebook:)</a></p>

		<Carousel v-bind="carouselConfig">
			<Slide v-for="slide in slides" :key="slide.id">
				<div class="slide__item">
					<img class="slide__img" :src="slide.img" alt="image">
					<div class="slide__info">
						<p class="slide__text">{{ slide.text }}</p>
						<p class="slide__author">{{ slide.author }}</p>
					</div>
				</div>
			</Slide>
		</Carousel>

	</section>
</template>

<style scoped>
.testimonials {
	padding: 58px 0;
	position: relative;
	text-align: center;
}

.testimonials__subtitle {
	margin-top: 24px;
}

.testimonials__img-right {
	position: absolute;
	top: 40px;
	right: 65px;
	z-index: 2;
}

.carousel {
	padding: 24px 0 104px;
}

.slide__item {
	display: flex;
	align-items: center;
	background-color: #DFF5F6;
	border-radius: 10px;
	padding: 28px 40px;
}

.slide__img {
	/* padding: 30px 40px 30px 0; */
	width: 240px;
	height: 240px;
	border-radius: 50%;
}

.slide__info {
	padding-left: 30px;
	text-align: left;
}

.slide__text {
	margin-bottom: 16px;
}

.slide__author {
	font-size: 20px;
	line-height: 33px;
	position: relative;
	padding-left: 38px;
}

.slide__author:before {
	content: "";
	position: absolute;
	left: 0;
	top: 6px;
	width: 22px;
	height: 22px;
	background-image: url('@/assets/icons/icon_insta.png');
	background-size: 22px 22px;
}
</style>