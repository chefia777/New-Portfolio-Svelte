<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/astropng.png';
	import github from '$lib/images/github.svg';
</script>

<header>
	<div class="corner">
		<a href="https://kit.svelte.dev">
			<img src={logo} alt="SvelteKit" />
		</a>
	</div>

	<nav>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Meus projetos</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">Tecnologias</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Sobre mim</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Curriculo</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Contato</a>
			</li>
		</ul>
	</nav>
</header>

<style>

@keyframes blink {
  100% {
    box-shadow: 0 0 3px #fff, 0 0 10px #fff, 0 0 20px #fff, 0 0 40px #0ba9ca,
      0 0 70px #0ba9ca, 0 0 80px #0ba9ca;
  }
}

	header {
		display: flex;
		justify-content: space-between;
	}

	.corner {
		width: 10em;
		height: 10em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 8em;
		height: 8em;
		object-fit: contain;
		left: 1em;
		top: 1em;
	}

	nav {
		display: flex;
		justify-content: center;
		--background:transparent;
		width: 100vw;
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		width:50vw;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
		gap: 15px;
		border-radius: 1em;
	}

	li {
		position: relative;
		height: 100%;
		
		
	}

	li[aria-current='page']::before {
		--size: 10px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 30px;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid white;
		transform: rotate(180deg);
		
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: white;
		font-family: Arial, Helvetica, sans-serif;
		font-weight: 500;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
		
	}

	a:hover {
		font-weight: 700;
	}

	a:active {
		font-weight: 700;
	}
</style>
