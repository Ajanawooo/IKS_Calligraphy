<script>
	import { goto } from '$app/navigation';
	import Definition1 from '$lib/assets/Definition1.jpg';
	import Definition2 from '$lib/assets/Definition2.jpg';
	import Definition3 from '$lib/assets/Definition3.jpg';
	import Definition4 from '$lib/assets/Definition4.jpg';
	
	let currentIndex = 0;
	const images = [Definition1, Definition2, Definition3, Definition4];
	
	function nextSlide() {
		currentIndex = (currentIndex + 1) % images.length;
	}
	
	function prevSlide() {
		currentIndex = (currentIndex - 1 + images.length) % images.length;
	}
	
	function goToSlide(index) {
		currentIndex = index;
	}
	
	function handleNext() {
		goto('/ersteUebung');
	}
</script>

<div class="container">
	<div class="content">
		<div class="slider">
			<button class="arrow arrow-left" on:click={prevSlide}>
				<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
					<polyline points="15 18 9 12 15 6"></polyline>
				</svg>
			</button>
			
			<div class="slider-content">
				<img src={images[currentIndex]} alt="Definition {currentIndex + 1}" />
			</div>
			
			<button class="arrow arrow-right" on:click={nextSlide}>
				<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
					<polyline points="9 18 15 12 9 6"></polyline>
				</svg>
			</button>
		</div>
		
		<div class="dots">
			{#each images as _, index}
				<button 
					class="dot" 
					class:active={index === currentIndex}
					on:click={() => goToSlide(index)}
				></button>
			{/each}
		</div>
		
		<button class="next-button" on:click={handleNext}>Weiter</button>
	</div>
</div>

<style>
	.container {
		min-height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		background: #f5f5f5;
		padding: 2rem;
	}
	
	.content {
		max-width: 900px;
		width: 100%;
		padding: 2rem;
		background: white;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
	}
	
	.slider {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		margin-bottom: 1.5rem;
	}
	
	.slider-content {
		flex: 1;
		display: flex;
		justify-content: center;
		align-items: center;
		max-width: 100%;
		overflow: hidden;
	}
	
	.slider-content img {
		max-width: 100%;
		max-height: 60vh;
		object-fit: contain;
		border-radius: 4px;
	}
	
	.arrow {
		background: #007bff;
		border: none;
		border-radius: 50%;
		width: 40px;
		height: 40px;
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
		transition: all 0.3s ease;
		color: white;
		flex-shrink: 0;
	}
	
	.arrow:hover {
		background: #0056b3;
		transform: scale(1.1);
	}
	
	.dots {
		display: flex;
		justify-content: center;
		gap: 0.5rem;
		margin-bottom: 2rem;
	}
	
	.dot {
		width: 12px;
		height: 12px;
		border-radius: 50%;
		border: 2px solid #007bff;
		background: white;
		cursor: pointer;
		transition: all 0.3s ease;
		padding: 0;
	}
	
	.dot:hover {
		transform: scale(1.2);
	}
	
	.dot.active {
		background: #007bff;
	}
	
	.next-button {
		font-size: 1rem;
		color: #fff;
		background: #007bff;
		border: none;
		border-radius: 4px;
		padding: 0.75rem 2rem;
		cursor: pointer;
		transition: background 0.3s ease;
		display: block;
		margin: 0 auto;
	}
	
	.next-button:hover {
		background: #0056b3;
	}
	
	@media (max-width: 768px) {
		.container {
			padding: 1rem;
		}
		
		.content {
			padding: 1.5rem;
		}
		
		.arrow {
			width: 36px;
			height: 36px;
		}
		
		.slider-content img {
			max-height: 50vh;
		}
	}
</style>