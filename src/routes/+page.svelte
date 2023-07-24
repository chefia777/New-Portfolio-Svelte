<script>
	import Counter from './Counter.svelte';
	import astronaut from '$lib/images/astro.jpg';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section >
		<div class="laptop:mt-18 mt-8o home mb-10 columns-2 container">
			<div class="titulo mt-5 m-auto first">
				<div class="font-bold text-8xl tablet:text-6xl laptop:text-6xl laptopl:text-8xl p-1 tablet:p-2 text-bold w-4/5 mob:w-full laptop:w-4/5 text-white">
					ARIEL
				</div>
				<div class="text-7xl tablet:text-6xl laptop:text-6xl laptopl:text-8xl p-1 tablet:p-2 text-bold w-4/5 mob:w-full laptop:w-4/5 text-white">
					Desenvolvedor
				</div>
				<div class="font-bold text-7xl tablet:text-6xl laptop:text-6xl laptopl:text-8xl p-1 tablet:p-2 text-bold w-4/5 mob:w-full laptop:w-4/5 text-white">
					WEB
				</div>
				<div class="font-bold text-7xl tablet:text-6xl laptop:text-6xl laptopl:text-8xl p-1 tablet:p-2 text-bold w-4/5 mob:w-full laptop:w-4/5 text-white">
					FRONT-END
				</div>
			</div>
			<picture class="right-5">
				<source srcset={astronaut} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</div>
		
</section>

<style>
	
	.container{
		width: 100vw;
	}

	img {
		width: 500px;
		animation:  120s linear infinite;
		
	}

	@keyframes rotating {
		0% {
			rotate:0deg;
		}
		100% {
			rotate: 360deg;
		}
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		flex: 0.6;
	}

	.titulo {
		width: 100%;
		font-size: 2em;
		opacity:1;
		animation: showText 2s ease-in;
	}


	@keyframes showText {
		0% { opacity: 0; }
  		100% { opacity: 1; }
	}

</style>
