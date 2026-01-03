<script lang="ts">
	import federkiel from '$lib/assets/Federkiel.png';
	import { goto } from '$app/navigation';
	
	function handleWeiter() {
		goto('/zwischenstep');
	}
</script>

<div class="container">
	<img src={federkiel} alt="Federkiel" />
	<button on:click={handleWeiter}>weiter</button>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		min-height: 100vh;
		background: #f5f5f5;
		padding: 2rem;
		gap: 2rem;
	}
	
	img {
		max-width: 100%;
		max-height: 70vh;
		object-fit: contain;
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
