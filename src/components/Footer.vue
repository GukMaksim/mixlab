<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
	<footer class="footer" role="contentinfo">
		<div class="footer-top">
			<div class="footer-logos" role="list" aria-label="Partner logos">
				<img src="@/assets/icons/footer-logo-1.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-2.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-3.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-4.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-5.png" alt="footer-logo">
			</div>
		</div>

		<div class="footer-container">
			<div class="footer-content">
				<div class="footer-column">
					<h4 id="quick-links">Quick Links</h4>
					<ul aria-labelledby="quick-links">
						<li><a href="#">Veterinarians</a></li>
						<li><a href="#">Products</a></li>
						<li><a href="#">How it Works</a></li>
						<li><a href="#">About us</a></li>
						<li><a href="#">Blog</a></li>
						<li><a href="#">Shop</a></li>
						<li><a href="#">Careers</a></li>
						<li><a href="#">Veterinarian login</a></li>
						<li><a href="#">Contact us</a></li>
					</ul>
				</div>

				<div class="footer-column">
					<h4 id="contact-info">Contact Information</h4>
					<div aria-labelledby="contact-info">
						<div class="contact-item">
							<h5>Call or Text</h5>
							<p><a href="tel:8889014480">(888) 901-4480</a></p>
						</div>
						<div class="contact-item">
							<h5>Email</h5>
							<p><a href="mailto:hello@mixlabrx.com">hello@mixlabrx.com</a></p>
						</div>
						<div class="contact-item">
							<h5>Fax</h5>
							<p>(212) 967-0892</p>
						</div>
					</div>
				</div>

				<div class="footer-column">
					<h4 id="nyc-location">New York City</h4>
					<address aria-labelledby="nyc-location">
						<p>336 West 37th St<br>Suite 850<br>New York, NY 10018</p>
						<p>Mon–Sat 10am – 8pm ET<br>Sun 10am – 2pm ET</p>
					</address>
				</div>

				<div class="footer-column">
					<h4 id="la-location">Los Angeles</h4>
					<address aria-labelledby="la-location">
						<p>2223 Federal Ave<br>Los Angeles, CA 90064</p>
						<p>Mon–Sat 9am – 7pm PT<br>Sun 9am – 1pm PT</p>
					</address>
				</div>

				<div class="footer-column">
					<h4 id="social-links">Social</h4>
					<div class="social-icons" aria-labelledby="social-links">
						<a href="#"><img src="@/assets/icons/icon-instagram.png" alt="Instagram"></a>
						<a href="#"><img src="@/assets/icons/icon-facebook.png" alt="Facebook"></a>
						<a href="#"><img src="@/assets/icons/icon-twitter.png" alt="Twitter"></a>
						<a href="#"><img src="@/assets/icons/icon-yelp.png" alt="Yelp"></a>
						<a href="#"><img src="@/assets/icons/icon-google.png" alt="Google"></a>
					</div>
				</div>
			</div>
		</div>

		<div class="footer-bottom">
			<div class="footer-container footer-bottom-container">
				<p>&copy;{{ currentYear }} Mixlab, Inc.</p>
				<nav class="footer-links" aria-label="Legal links">
					<a href="#">Privacy Policy</a>
					<a href="#">Terms of Service</a>
				</nav>
			</div>
		</div>
	</footer>
</template>

<style scoped>
.footer {
	background-color: var(--color-purple-dark);
	color: #ffffff;
	font-size: 14px;
}

.footer-container {
	max-width: 1440px;
	margin: 0 auto;
	padding: 0 1rem;
}

.footer-top {
	background-color: var(--color-purple);
	padding: 1.25rem 0;
	text-align: center;
}

.footer-logos {
	height: 87px;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-wrap: wrap;
	gap: 1rem;
}

.footer-logos img {
	height: 100%;
	width: auto;
	transition: opacity 0.3s ease;
}

.footer-logos img:hover {
	opacity: 0.8;
}

.footer-content {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
	gap: 2rem;
	padding: 2.5rem 1rem;

}

.footer-column {
	min-width: 160px;
}

.footer-column h4 {
	text-transform: uppercase;
	font-size: 0.75rem;
	color: #C282F0;
	margin-bottom: 1rem;
}

.footer-column h5 {
	font-size: 0.875rem;
	color: #C282F0;
	margin: 1rem 0 0.25rem;
}

.footer-column ul {
	margin: 0;
	padding: 0;
	list-style: none;
}

.footer-column p,
.footer-column a {
	color: #ffffff;
	text-decoration: none;
	margin-bottom: 0.375rem;
	display: block;
	line-height: 1.5;
}

.footer-column a:hover {
	text-decoration: underline;
}

.contact-item {
	margin-bottom: 1rem;
}

.social-icons {
	display: flex;
	flex-wrap: wrap;
	gap: 1rem;
}

.social-icons a {
	display: inline-flex;
	align-items: center;
	justify-content: center;
	padding: 2px;
	transition: transform 0.3s ease;
}

.social-icons a:hover {
	transform: translateY(-2px);
	background-color: var(--color-accent);
	border-radius: 6px;
}

.social-icons img {
	width: 24px;
	height: 24px;
	object-fit: contain;
}

.footer-bottom {
	border-top: 1px solid #5e2d94;
	padding: 1.25rem 1rem;
	font-size: 0.75rem;
}

.footer-bottom-container {
	display: flex;
	justify-content: space-between;
	align-items: center;
	flex-wrap: wrap;
	gap: 1rem;
}

.footer-links {
	display: flex;
	gap: 1rem;
}

.footer-links a {
	color: #ffffff;
	text-decoration: none;
	transition: color 0.3s ease;
}

.footer-links a:hover {
	color: #C282F0;
}

@media (max-width: 768px) {
	.footer-content {
		grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
		gap: 1.5rem;
		padding: 2rem 1rem;
	}

	.footer-links {
		justify-content: center;
	}
}

@media (max-width: 480px) {
	.footer-logos {
		gap: 0.5rem;
	}

	.footer-logos img {
		height: 30px;
	}

	.footer-content {
		grid-template-columns: 1fr;
		text-align: center;
	}

	.social-icons {
		justify-content: center;
	}
}
</style>