<script lang="ts">
	import '../app.css';
	import Header from '$lib/components/header.svelte'
	import Footer from '$lib/components/footer.svelte'
	import { Toaster } from 'svelte-sonner';

	let { children } = $props();
</script>
<Toaster position="top-center" toastOptions={{
		classes: {
			error: 'bg-danger',
			success: 'text-success',
			warning: 'text-warning',
			info: 'bg-info'
		}
	}}/>
<Header/>
{@render children()}
<Footer/>
