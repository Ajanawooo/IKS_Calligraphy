<script>
	import { goto } from '$app/navigation';
	import maobiGif from '$lib/assets/Maobi.gif';
	
	function handleSkip() {
		goto('/zwischenstep');
	}
	
	function handleTryOther() {
		goto('/qalam');
	}
</script>

<div class="container">
	<img src={maobiGif} alt="Maobi Brush" />
	<div class="button-group">
		<button on:click={handleSkip}>skip</button>
		<button on:click={handleTryOther}>try other utensil</button>
	</div>
</div>

<style>
	.container {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background: #ffffff;
		padding: 2rem;
		gap: 2rem;
	}
	
	img {
		max-width: 100%;
		max-height: 70vh;
		object-fit: contain;
	}
	
	.button-group {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
		justify-content: center;
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
</style>
