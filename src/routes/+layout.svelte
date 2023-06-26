<script>
	import "../app.postcss";
    import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
    import '@skeletonlabs/skeleton/styles/skeleton.css';
    import '../app.postcss';
    import { AppBar, popup, storePopup } from '@skeletonlabs/skeleton';
    import { metaStore } from '../stores';
    import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
    import NavLinks from '../components/NavLinks.svelte';
    import Icon from '@iconify/svelte';

	export const prerender = true;

    storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow })

    const popupNav = {
		// Represents the type of event that opens/closed the popup
		event: 'click',
		// Matches the data-popup value on your popup element
		target: 'popupNav',
		// Defines which side of your trigger the popup will appear
		placement: 'bottom',
	};
	</script>
	
	<svelte:head>
    	<title>{$metaStore.title ? `${$metaStore.title} - ` : ''} Doolittle.me</title> 
	</svelte:head>
	
	<body data-theme="skeleton">
		<main>
			<!-- Navbar -->
			<AppBar>
				<svelte:fragment slot="lead">
					<a class="h3 text-primary-800" href="/">
						Doolittle.me
					</a>
				</svelte:fragment>
				<svelte:fragment slot="trail">
					<button class="btn variant-filled md:hidden" use:popup="{popupNav}">
						Menu <Icon icon="fa-solid:bars" class="ms-3"></Icon>
					</button>
					<div class="card p-4 w-72 shadow-xl z-50" data-popup="popupNav">
						<ul class="list-none flex flex-col gap-5 text-lg">
							<NavLinks></NavLinks>
						</ul>
					</div>
					<!-- Horizontal links -->
					<ul class="hidden md:flex flex-wrap items-center justify-center gap-6">
						<NavLinks></NavLinks>
					</ul>
				</svelte:fragment>
			</AppBar>
			<div class=" my-4 mx-3 md:m-auto md:w-4/5 lg:w-1/2 relative overflow-x-hidden">
				<h1 class="text-3xl font-bold my-2">{$metaStore.title}</h1>
				<slot></slot>
			</div>
		</main>
		<!-- Force footer to bottom -->
		<footer class="bottom-0 w-full my-5">
			<div class="text-center text-muted-600 opacity-50">
				<p>
					&#xa9; 2023 Doolittle.me
				</p>
			</div>
		</footer>
	</body>
	
	