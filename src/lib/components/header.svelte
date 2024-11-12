<script lang="ts">
	const links = [
		{
			label: 'Home',
			href: '/'
		}
	];
</script>

<header class="navbar max-auto container">
	<div class="navbar-start">
		<div class="dropdown">
			<button aria-label="logo" class="btn btn-ghost lg:hidden">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-5 w-5"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M4 6h16M4 12h8m-8 6h16" />
				</svg>
			</button>
			<ul
				class="menu menu-sm dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-52 p-2 shadow">
				{#each links as link (link.href)}
					<li>
						<a href={link.href}>{link.label}</a>
					</li>
				{/each}
			</ul>
		</div>
		<a href="/" class="btn btn-ghost text-xl">Leticia Jury</a>
	</div>
	<div class="navbar-center hidden lg:flex">
		<nav>
			<menu class="menu menu-horizontal px-1">
				{#each links as link (link.href)}
					<li>
						<a class="text-lg" href={link.href}>{link.label}</a>
					</li>
				{/each}
			</menu>
		</nav>
	</div>
	<div class="navbar-end">
		<a href="/contato" class="btn btn-primary">Contato</a>
	</div>
</header>