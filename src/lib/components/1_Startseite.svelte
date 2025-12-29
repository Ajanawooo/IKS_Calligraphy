<script>
	import { goto } from '$app/navigation';
	
	function handleStart() {
		goto('/KalligrafieIntro');
	}
</script>

<div class="container">
	<div class="content">
		<h1>come over and try out</h1>
		<button on:click={handleStart}>start</button>
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
