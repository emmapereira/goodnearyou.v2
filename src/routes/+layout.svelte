<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import { page } from '$app/stores';
</script>

<AppShell>
	<svelte:fragment slot="header">
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Good Near You</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a 
					class="btn btn-sm variant-ghost-surface" 
					href="/" 
					class:variant-filled-primary={$page.url.pathname === '/'}
				>
					Home
				</a>
				<a 
					class="btn btn-sm variant-ghost-surface" 
					href="/stores" 
					class:variant-filled-primary={$page.url.pathname === '/stores'}
				>
					Stores
				</a>
				<a 
					class="btn btn-sm variant-ghost-surface" 
					href="/about" 
					class:variant-filled-primary={$page.url.pathname === '/about'}
				>
					About & Register
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>

	<main class="container mx-auto p-4">
		<slot />
	</main>

	<svelte:fragment slot="footer">
		<footer class="p-4 bg-surface-100-800-token">
			<div class="container mx-auto text-center">
				<p>Copyright GoodNearYou 2025 | info@goodnearyo.com | Our Terms</p>
			</div>
		</footer>
	</svelte:fragment>
</AppShell>
