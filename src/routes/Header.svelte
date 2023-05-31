<nav
	class="
		fixed
		top-0
		py-2
		px-4
		md:py-0
		w-full
		backdrop-blur
		flex
		items-center
		justify-between
		bg-white/10
		dark:bg-neutral-950/10
		z-10
	"
>
	<div>
		<a href="/">
			<img src={forthub} width="114" height="40" alt="FortHub logo" />
		</a>
	</div>

	<div class="flex items-center gap-4">
		<div
			class="
				{isMenuOpen ? 'right-0' : '-right-[100%]'}
				fixed
				top-0
				bottom-0					
				py-2
				px-4
				w-60
				h-screen
				bg-white
				dark:bg-neutral-950
				md:p-0
				md:w-auto
				md:h-auto
				md:block
				md:static
				md:bg-transparent
				md:dark:bg-transparent
				shadow-md
				md:shadow-none
				transition-all
				duration-300
				ease-in-out
				z-10
			"
			use:clickOutside
			on:click_outside={() => {
				if (isMenuOpen) isMenuOpen = false;
			}}
		>
			<div class="mb-4 md:mb-0 flex justify-end">
				<Button
					round
					class="md:hidden"
					icon={mdiClose}
					on:click={menuToggle}
				/>
			</div>
		
			<ul class="flex flex-col md:flex-row">
				{#each navs as nav}
					<li>
						<a
							href={nav.href}
							class="
								px-5
								py-4
								w-full
								block
								hover:bg-black/10
								dark:hover:bg-white/10
								font-medium
								hover:text-amber-500
								rounded-md
								md:rounded-none
								md:w-auto
								md:inline-block
								md:hover:bg-transparent
								md:dark:hover:bg-transparent
								transition-colors
							"
							on:click={menuToggle}
							on:click={e => { scrollTo(e, nav.href) }}
						>{nav.label}</a>
					</li>
				{/each}
			</ul>
		</div>
			
		<div class="flex items-center gap-4">
			<Button
				round
				icon={themeClass === 'dark' ? mdiWeatherSunny : mdiWeatherNight}
				on:click={toggleTheme}
			/>
			<Button
				round
				class="md:hidden"
				icon={mdiMenu}
				on:click={menuToggle}
			/>
		</div>
	</div>
</nav>

<script>
import forthub from '$lib/images/forthub.svg';
import { clickOutside } from '$lib/utils/clickOutside';
import Button from '$lib/components/Button.svelte';
import { mdiMenu, mdiClose, mdiWeatherSunny, mdiWeatherNight } from '@mdi/js';

let navs = [
	{ href: '#tours', label: 'Экскурсии' },
	{ href: '#about', label: 'О нас' },
	{ href: '#contacts', label: 'Контакты' }
];

let theme = 'system';

try {
	theme = localStorage.getItem('theme') || 'system';
} catch {}
 
let isMenuOpen = false;

const menuToggle = () => {
	isMenuOpen = !isMenuOpen;
};

const scrollTo = (e, id) => {
	e.preventDefault();
	document.querySelector(id).scrollIntoView({ behavior: 'smooth' });
};

const prefersColorScheme = () =>
	window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light';

let themeClass = theme === 'system' ? prefersColorScheme() : theme;

const toggleTheme = () => {
	themeClass = themeClass === 'dark' ? 'light' : 'dark';
	
	try {
		localStorage.setItem('theme', themeClass);
	} catch {}
};

$: {
	document.documentElement.className = themeClass;
	// document.documentElement.style.colorScheme = themeClass === 'dark' ? 'dark' : 'light';
};
</script>
