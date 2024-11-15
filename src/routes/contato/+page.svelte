<script>
	import InstagramIcon from '$lib/components/icons/instagram-icon.svelte';
	import LinkedinIcon from '$lib/components/icons/linkedin-icon.svelte';
	import LattesIcon from '$lib/components/icons/lattes-icon.svelte';
	import EmailIcon from '$lib/components/icons/email-icon.svelte';
	import { toast } from 'svelte-sonner';

	const links = [
		{ label: '@leticiajury', href: 'https://instagram.com/leticiajury', icon: InstagramIcon },
		{ label: 'Leticia Arantes Jury', href: 'https://www.linkedin.com/in/let%C3%ADcia-arantes-jury-545287b4', icon: LinkedinIcon },
		{ label: 'JURY, Leticia Arantes', href: 'https://lattes.cnpq.br/3069426017717757', icon: LattesIcon },
		{
			label: 'leticiajury@gmail.com', action: () => {
				navigator.clipboard.writeText('leticiajury@gmail.com').then(() => {
					toast.success('Email copiado');
				});
			}, icon: EmailIcon
		},
	];
</script>
{#snippet IconWrapper(icon)}
	<span class="bg-primary p-1.5 rounded">
		<svelte:component this={icon} class="fill-white size-6" />
	</span>
{/snippet}

<div class="lg:grid grid-cols-2 flex flex-col-reverse container gap-8 py-16">
	<div class="space-y-4">
		<h2 class="text-2xl">Redes Sociais</h2>
		<p><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid commodi cumque eius hic illum ipsa ipsam, maxime neque nobis nostrum perspiciatis possimus quas quia quod ratione velit voluptate voluptatum. Consequuntur.</span><span>A ab atque dolore dolores, maxime officia omnis pariatur repellendus. Cum eaque facere tempore voluptates? Accusantium at commodi consequatur, cum dolore doloribus libero mollitia nam nesciunt nobis non quis. Facilis.</span>
		</p>
		<nav class="list-none space-y-4">
			{#each links as link}
				<li>
					{#if 'href' in link}
						<a href={link.href} class="flex items-center gap-2 text-lg" target="_blank">
							{@render IconWrapper(link.icon)}
							<span>{link.label}</span>
						</a>
					{:else}
						<button onclick={link.action} class="flex items-center gap-2 text-lg">
							{@render IconWrapper(link.icon)}
							<span>{link.label}</span>
						</button>
					{/if}
				</li>
			{/each}
		</nav>
	</div>
	<div class="space-y-4">
		<h2 class="text-2xl">Contato</h2>
		<form action="" class="w-full space-y-4">
			<label class="form-control w-full">
			<span class="label">
				Nome
			</span>
				<input type="text" placeholder="Fulano da Silva" class="input input-bordered w-full" />
			</label>
			<label class="form-control w-full">
			<span class="label">
				E-mail
			</span>
				<input type="text" placeholder="fulano@gmail.com" class="input input-bordered w-full" />
			</label>
			<label class="form-control w-full">
			<span class="label">
				Mensagem
			</span>
				<textarea placeholder="Sua mensagem" class="textarea textarea-bordered w-full" rows="3"></textarea>
			</label>
			<button class="btn btn-primary float-right">Enviar</button>
		</form>

	</div>
</div>