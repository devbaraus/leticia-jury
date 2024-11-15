<script lang="ts">
	import { page } from '$app/stores';
	import { cn } from '$lib';

	let pathname = $derived($page.url.pathname)

	type Link = {
		label: string
		href: string
		active?: boolean
	}

	const links: Array<Link> = [
		{
			label: 'Home', href: '/'
		}, {
			label: 'Artigos', href: '/artigos'
		}, {
			label: 'Capítulos', href: '/capitulos'
		}, {
			label: 'Livros', href: '/livros'
		}, {
			label: 'Citação', href: '/citacao'
		}, {
			label: 'Baru', href: '/baru'
		}, {
			label: 'Opinião', href: '/opiniao'
		}, {
		label: 'Contato', href: '/contato'
		}
	]
</script>

<header class="navbar max-auto container">
	<div class="navbar-start">
		<a href="/" class="font-semibold text-2xl">Leticia Jury</a>
	</div>
	<div class="navbar-center hidden lg:flex">
		<nav>
			<menu class="flex items-center gap-4 [&_>_li_>_a]:py-3 [&_>_li_>_a]:px-1">
				{#each links as link (link.label)}
					<li>
						<a class={cn("text-lg rounded-none transition", pathname === link.href ? 'border-b-2 border-primary' : '')} href={link.href}>{link.label}</a>
					</li>
				{/each}
			</menu>
		</nav>
	</div>
	<div class="navbar-end">
		<div class="dropdown dropdown-end">
			<button aria-label="logo" class="lg:hidden">
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
				{#each links as link (link.label)}
					<li>
						<a class="text-xl" href={link.href}>{link.label}</a>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</header>