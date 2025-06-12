<script setup>
</script>

<template>
	<footer class="footer">
		<div class="footer-top">
			<div class="footer-logos">
				<img src="@/assets/icons/footer-logo-1.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-2.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-3.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-4.png" alt="footer-logo">
				<img src="@/assets/icons/footer-logo-5.png" alt="footer-logo">
			</div>
		</div>
		
		<div class="container">
		<div class="footer-content">
			<div class="footer-column">
				<h4>Quick Links</h4>
				<ul>
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
				<h4>Call or Text</h4>
				<p>(888) 901-4480</p>
				<h4>Email</h4>
				<p>hello@mixlabrx.com</p>
				<h4>Fax</h4>
				<p>(212) 967-0892</p>
			</div>

			<div class="footer-column">
				<h4>New York City</h4>
				<p>336 West 37th St<br />Suite 850<br />New York, NY 10018</p>
				<p>Mon–Sat 10am – 8pm ET<br />Sun 10am – 2pm ET</p>
			</div>

			<div class="footer-column">
				<h4>Los Angeles</h4>
				<p>2223 Federal Ave<br />Los Angeles, CA 90064</p>
				<p>Mon–Sat 9am – 7pm PT<br />Sun 9am – 1pm PT</p>
			</div>

			<div class="footer-column">
				<h4>Social</h4>
				<div class="social-icons">
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
			<div class="container">
			<p>©2021 Mixlab, Inc.</p>
			<div class="footer-links">
				<a href="#">Privacy Policy</a>
				<a href="#">Terms of Service</a>
			</div>

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
.footer-top {
	background-color: var(--color-purple);
	padding: 20px 0;
	text-align: center;
}
.footer-logos img {
	margin: 0 10px;
	height: 40px;
}
.footer-content {
	display: flex;
	fwwrap: wrap;
	padding: 40px 60px;
	justify-content: space-between;
	gap: 30px;
}
.footer-column {
	min-width: 160px;
	max-width: 220px;
}
.footer-column h4 {
	text-transform: uppercase;
	font-size: 12px;
	color: #C282F0;
	margin-bottom: 8px;
}
.footer-column ul {
	margin: 0;
	padding: 0;
}
.footer-column li {
	list-style: none;
}
.footer-column p, .footer-column a {
	color: #ffffff;
	text-decoration: none;
	margin-bottom: 6px;
	display: block;
}
.footer-column a:hover {
  text-decoration: underline;
}
.social-icons {
	display: flex;
	flex-wrap: wrap;
}
.social-icons a img {
	width: 24px;
	height: 24px;
	object-fit: contain;
	margin-right: 10px;
}
.footer-bottom {
	border-top: 1px solid #5e2d94;
	display: flex;
	justify-content: space-between;
	padding: 20px 60px;
	font-size: 12px;
	flex-wrap: wrap;
}
.footer-links a {
	margin-left: 16px;
	color: #ffffff;
	text-decoration: none;
}
</style>