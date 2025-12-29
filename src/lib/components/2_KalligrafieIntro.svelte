<script>
	import { goto } from '$app/navigation';
	
	const text = 'Kalligrafie ist die handwerkliche Kunst des bewussten Schreibens. Sie verbindet präzise Technik, Materialkenntnis und jahrelange Übung mit gestalterischem Ausdruck. Historisch diente sie nicht der Dekoration, sondern der Standardisierung von Schrift: Lesbarkeit, Rhythmus und Proportion standen im Zentrum. Schriftarten folgten klaren Regeln, die über Generationen weitergegeben und verfeinert wurden. Jede Kultur entwickelte ihre Schrift anders und jede Region und Zeit hatte ihre eigenen Werkzeuge und Bräuche dafür.';
	
	function handleNext() {
		goto('/maobi');
	}
</script>

<div class="container">
	<div class="content">
		<p>{text}</p>
		<button on:click={handleNext}>Weiter</button>
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
		max-width: 800px;
		padding: 2rem;
		background: white;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
	}
	
	p {
		font-size: 1.1rem;
		color: #333;
		line-height: 1.6;
		margin: 0 0 2rem 0;
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
			padding: 1rem;
		}
		
		.content {
			padding: 1.5rem;
		}
		
		p {
			font-size: 1rem;
		}
	}
</style>