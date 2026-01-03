<script lang="ts">
	import { goto } from '$app/navigation';
	
	let selectedOption: string | null = null;
	let showModal = false;
	let modalMessage = '';
	let isCorrect = false;
	
	function handleOptionClick(option: string) {
		selectedOption = option;
		
		setTimeout(() => {
			if (option === 'Calligraphy') {
				modalMessage = 'good job!';
				isCorrect = true;
			} else {
				modalMessage = 'ooops nice try';
				isCorrect = false;
			}
			showModal = true;
		}, 1000);
	}
	
	function handleWeiter() {
		goto('/quiz3');
	}
	
	function handleTryAnother() {
		goto('/quiz3');
	}
	
	function handleTryAgain() {
		showModal = false;
		selectedOption = null;
	}
</script>

<div class="container">
	<div class="content">
		<section>
			<p>under which category does the following word fall?</p>
		</section>

		<div class="quiz-layout">
			<div class="word-display">
				<p class="calligraphy">writing</p>
			</div>
			
			<div class="options">
				<button 
					class="option-box" 
					class:incorrect={selectedOption === 'Handlettering'}
					on:click={() => handleOptionClick('Handlettering')}
				>
					Handlettering
				</button>
				<button 
					class="option-box" 
					class:correct={selectedOption === 'Calligraphy'}
					on:click={() => handleOptionClick('Calligraphy')}
				>
					Calligraphy
				</button>
				<button 
					class="option-box" 
					class:incorrect={selectedOption === 'Typography'}
					on:click={() => handleOptionClick('Typography')}
				>
					Typography
				</button>
			</div>
		</div>
				
		<button on:click={handleWeiter}>weiter</button>
	</div>
	
	{#if showModal}
		<div class="modal-overlay" on:click={() => showModal = false}>
			<div class="modal-box" on:click|stopPropagation>
				<p>{modalMessage}</p>
				<div class="modal-buttons">
					{#if !isCorrect}
						<button class="modal-button" on:click={handleTryAgain}>try again</button>
					{/if}
					<button class="modal-button" on:click={handleTryAnother}>try another</button>
				</div>
			</div>
		</div>
	{/if}
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
		max-width: 1000px;
		width: 100%;
		padding: 2rem;
		background: white;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
	}
	
	section {
		margin-bottom: 2rem;
	}
	
	section p {
		font-size: 1.3rem;
		color: #333;
		line-height: 1.6;
		margin: 0;
	}
	
	.quiz-layout {
		display: flex;
		align-items: center;
		gap: 3rem;
		margin-bottom: 2rem;
	}
	
	.word-display {
		flex: 1;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem;
	}
	
	.calligraphy {
		font-family: 'Edwardian Script ITC', 'Monotype Corsiva', 'URW Chancery L', cursive;
		font-size: 3rem;
		color: #333;
		margin: 0;
		font-style: italic;
		font-weight: normal;
	}
	
	.options {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		flex: 1;
	}
	
	.option-box {
		font-size: 1.2rem;
		color: #333;
		background: white;
		border: 2px solid #007bff;
		border-radius: 8px;
		padding: 1.5rem;
		cursor: pointer;
		transition: all 0.3s ease;
		text-align: center;
	}
	
	.option-box:hover {
		background: #007bff;
		color: white;
	}
	
	.option-box.correct {
		background: #28a745;
		color: white;
		border-color: #28a745;
	}
	
	.option-box.incorrect {
		background: #dc3545;
		color: white;
		border-color: #dc3545;
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
	
	.modal-overlay {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: rgba(0, 0, 0, 0.5);
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 1000;
	}
	
	.modal-box {
		background: white;
		padding: 3rem 4rem;
		border-radius: 12px;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
		text-align: center;
	}
	
	.modal-box p {
		font-size: 1.5rem;
		color: #333;
		margin: 0 0 1.5rem 0;
	}
	
	.modal-buttons {
		display: flex;
		gap: 1rem;
		justify-content: center;
		flex-wrap: wrap;
	}
	
	.modal-button {
		font-size: 1rem;
		color: #fff;
		background: #007bff;
		border: none;
		border-radius: 4px;
		padding: 0.75rem 2rem;
		cursor: pointer;
		transition: background 0.3s ease;
	}
	
	.modal-button:hover {
		background: #0056b3;
	}
	
	@media (max-width: 768px) {
		.quiz-layout {
			flex-direction: column;
			gap: 2rem;
		}
		
		.calligraphy {
			font-size: 2rem;
		}
		
		.option-box {
			font-size: 1rem;
			padding: 1rem;
		}
		
		.modal-box {
			padding: 2rem 3rem;
		}
		
		.modal-box p {
			font-size: 1.2rem;
		}
	}
</style>
