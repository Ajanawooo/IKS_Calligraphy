<script>
	import { goto } from '$app/navigation';
	
	let showText = false;
	
	function handleNext() {
		showText = true;
	}
	
	function handleTryMe() {
		goto('/maobi/try');
	}
</script>

<div class="container">
	<div class="left-panel">
		<h1>Platziere folgenden Pinsel im vorgegebenen Bereich</h1>
				<h2>Chinesischer Kalligrafiepinsel (毛笔 Máobǐ)</h2>

		<div class="ellipse"></div>
		<button class="weiter-button" on:click={handleNext}>Weiter</button>
	</div>
	
	<div class="right-panel">
		{#if showText}
			<div class="content">
				<section>
					<h2>Herkunft</h2>
					<p>China (auch in Japan und Korea verbreitet)</p>
				</section>
				
				<section>
					<h2>Material & Aufbau</h2>
					<ul>
						<li>Griff aus Bambus oder Holz</li>
						<li>Pinselhaar aus Tierhaaren (z. B. Ziege, Wolf, Marder)</li>
					</ul>
				</section>
				
				<section>
					<h2>Besonderheiten</h2>
					<ul>
						<li>Sehr flexibel → ermöglicht dicke und dünne Linien in einem Strich</li>
						<li>Wird mit Tusche und Reibstein verwendet</li>
					</ul>
				</section>
				
				<section>
					<h2>Kulturelle Bedeutung</h2>
					<ul>
						<li>Zentrale Kunstform in China seit über 2.000 Jahren</li>
						<li>Kalligrafie gilt als Ausdruck von Charakter und Geist des Schreibenden</li>
					</ul>
				</section>
				
				<button on:click={handleTryMe}>try me</button>
			</div>
		{/if}
	</div>
</div>

<style>
	.container {
		min-height: 100vh;
		display: flex;
		background: #f5f5f5;
	}
	
	.left-panel {
		width: 50%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		padding: 4rem 2rem;
		background: white;
	}
	
	.right-panel {
		width: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem;
	}
	
	.ellipse {
		width: 50px;
		height: 400px;
		background: #007bff;
		border-radius: 50%;
		flex-shrink: 0;
	}
	
	.weiter-button {
		font-size: 1rem;
		color: #fff;
		background: #007bff;
		border: none;
		border-radius: 4px;
		padding: 0.75rem 2rem;
		cursor: pointer;
		transition: background 0.3s ease;
	}
	
	.weiter-button:hover {
		background: #0056b3;
	}
	
	.content {
		max-width: 600px;
		padding: 2rem;
		background: white;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
		width: 100%;
	}
	
	h1 {
		font-size: 1.8rem;
		color: #333;
		margin: 0;
		text-align: center;
	}
	
	section {
		margin-bottom: 1.5rem;
	}
	
	section:last-of-type {
		margin-bottom: 2rem;
	}
	
	h2 {
		font-size: 1.3rem;
		color: #007bff;
		margin: 0 0 0.75rem 0;
	}
	
	p {
		font-size: 1.1rem;
		color: #333;
		line-height: 1.6;
		margin: 0;
	}
	
	ul {
		margin: 0;
		padding-left: 1.5rem;
	}
	
	li {
		font-size: 1.1rem;
		color: #333;
		line-height: 1.6;
		margin-bottom: 0.5rem;
	}
	
	li:last-child {
		margin-bottom: 0;
	}
	
	button {
		font-size: 1rem;
		color: #fff;
		background: #007bff;
		border: none;
		border-radius: 4px;
		padding: 0.75rem 2rem;
		cursor: pointer;
		transition: background 0.3s ease;
	}
	
	button:hover {
		background: #0056b3;
	}
	
	@media (max-width: 768px) {
		.container {
			flex-direction: column;
		}
		
		.left-panel,
		.right-panel {
			width: 100%;
		}
		
		.left-panel {
			padding: 2rem 1rem;
			min-height: 50vh;
		}
		
		.right-panel {
			padding: 1rem;
		}
		
		.content {
			padding: 1.5rem;
		}
		
		h1 {
			font-size: 1.5rem;
		}
		
		h2 {
			font-size: 1.2rem;
		}
		
		p, li {
			font-size: 1rem;
		}
	}
</style>
