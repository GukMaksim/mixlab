<script setup>
import TheButton from '@/components/buttons/TheButton.vue';
</script>

<template>
	<section class="how-it-works">
		<div class="container">
			<div class="how-it-works__inner">
				<h2 class="how-it-works__title">How it works</h2>
				<div class="how-it-works__items">
					<div class="how-it-works__item">
						<div class="how-it-works__item-img-wrapper">
							<img src="@/assets/works-1.png" alt="How it works" class="how-it-works__item-img">
						</div>
						<div class="how-it-works__item-info">
							<h3 class="how-it-works__item-title">We receive your prescription</h3>
							<p class="how-it-works__item-text">Either your veterinarian sends us a prescription or we reach out to
								them for you. Whatever is easiest!</p>
						</div>
					</div>
					<div class="how-it-works__item">
						<div class="how-it-works__item-img-wrapper">
							<img src="@/assets/works-2.png" alt="How it works" class="how-it-works__item-img">
						</div>
						<div class="how-it-works__item-info">
							<h3 class="how-it-works__item-title">We deliver your care package</h3>
							<p class="how-it-works__item-text">Fast and free next-day delivery, straight to your door. Same-day in NYC
								and LA.</p>
						</div>
					</div>
					<div class="how-it-works__item">
						<div class="how-it-works__item-img-wrapper">
							<img src="@/assets/works-3.png" alt="How it works" class="how-it-works__item-img">
						</div>
						<div class="how-it-works__item-info">
							<h3 class="how-it-works__item-title">You treat your pet</h3>
							<p class="how-it-works__item-text">Give your pet the care they need to feel better. Plus they can play
								with our included toy!</p>
						</div>
					</div>
				</div>
				<TheButton text="Learn More" />
			</div>
		</div>
	</section>
</template>

<style scoped>
.how-it-works {
	background-color: #FAF9F6;
	padding: 60px 0 76px 0;
}

.how-it-works__inner {
	width: 100%;
	text-align: center;
}

.how-it-works__title {
	margin-bottom: 65px;
}

.how-it-works__items {
	display: flex;
	justify-content: center;
	gap: 40px;
	margin-bottom: 64px;
}

.how-it-works__item {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
	text-align: center;
	width: 359px;
	height: 329px;
}

.how-it-works__item-img-wrapper {
	background-color: #FFF7C2;
	width: 192px;
	height: 192px;
	border-radius: 50%;
	display: flex;
	align-items: center;
	justify-content: center;
}

.how-it-works__item-title {
	color: var(--color-purple);
	font-size: 24px;
	line-height: 32px;
	margin-bottom: 8px;
}
</style>
