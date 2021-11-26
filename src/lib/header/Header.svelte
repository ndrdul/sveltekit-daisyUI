<script>
	import { page } from '$app/stores';
	
</script>

<nav>
	<div class="navbar mb-2 shadow-lg bg-neutral text-neutral-content ">
		<div class="flex-1 px-2 mx-2">
			<ul>
				<li class:active={$page.path === '/'}>
					<a class="btn" sveltekit:prefetch href="/">Home</a>
				</li>
				<li class:active={$page.path === '/about'}>
					<a class="btn" sveltekit:prefetch href="/about">About</a>
				</li>
				<li class:active={$page.path === '/todos'}>
					<a class="btn" sveltekit:prefetch href="/todos">Todos</a>
				</li>
			</ul>
		</div>
	</div>
</nav>

<style>
	header {
		display: flex;
		justify-content: space-between;
	}

	.corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
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
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li.active::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--accent-color);
	}

	a:hover {
		color: var(--accent-color);
	}
</style>
