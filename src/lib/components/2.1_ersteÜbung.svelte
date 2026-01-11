<script>
	import { goto } from '$app/navigation';
		import Strichübung from '$lib/assets/Strichübung.jpg';

	function handleNext() {
		goto('/maobi');
	}
</script>

<div class="container">
	<div class="content">
		<h2>Nimm den Stift in die Hand und zeichne die Linien nach.</h2>
		<img src={Strichübung} alt="Strichübung" />
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
	}
	
	.content {
		text-align: center;
		padding: 2rem;
	}
	
	h1 {
		font-size: 2rem;
		color: #333;
		margin: 0 0 2rem 0;
	}
	
	img {
		max-width: 100%;
		height: auto;
		border-radius: 8px;
		margin: 0 0 2rem 0;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
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
		h1 {
			font-size: 1.5rem;
		}
		
		button {
			font-size: 0.9rem;
			padding: 0.6rem 1.5rem;
		}
	}
</style>
