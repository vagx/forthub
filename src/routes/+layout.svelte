<div
	class="
		flex
		flex-col
		bg-white
		text-neutral-900
		dark:bg-neutral-950
		dark:text-white
		transition-colors
	"
>
	<Header />

	<main class="flex flex-col items-center">
		<slot />
	</main>

	<Footer />

	<Button
		round
		bg="bg-amber-500"
		icon={mdiChevronUp}
		size="lg"
		class="
			fixed
			right-5
			{y > 200 ? 'bottom-5' : '-bottom-[100%]'}
			duration-500
		"
		on:click={toTop}
	/>
</div>

<svelte:window bind:scrollY={y} />

<script>
import Header from './Header.svelte';
import Footer from './Footer.svelte';
import Button from '$lib/components/Button.svelte';
import { mdiChevronUp } from '@mdi/js';
import '@fontsource-variable/inter';
import './app.css';

let y;

const toTop = () => {
	window.scrollTo({
		top: 0,
		behavior: 'smooth'
	});
};
</script>
