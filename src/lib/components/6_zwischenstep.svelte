<script lang="ts">
	import { goto } from '$app/navigation';
	
	function handleWeiter() {
		goto('/quiz1');
	}
</script>

<div class="container">
	<div class="content">
		
		<section>
			<p>Today calligraphie isn’t as common anymore, but evolved to be a kind of art.
It isn’t just a way of writing, but a way of expressing yourself. </p>
		</section>

        <section>
			<p>It is commonly mistaken for Handlettering or typography</p>
		</section>
				
		<button on:click={handleWeiter}>weiter</button>
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
	
	h1 {
		font-size: 1.8rem;
		color: #333;
		margin: 0 0 2rem 0;
	}
	
	section {
		margin-bottom: 1.5rem;
	}
	
	section:last-child {
		margin-bottom: 0;
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
		margin-top: 2rem;
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
