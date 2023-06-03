<section
	class="
		h-screen
		w-full
		bg-center
		bg-cover
	"
	style="background-image: url('{welcome}')"
>
	<div class="relative h-full flex flex-col items-center justify-center">
		<div
			class="
				absolute
				w-full
				h-full
				bg-black/50
			"
		/>
		<div class="absolute p-2 flex flex-col items-center gap-4 lg:gap-6">
			<h1
				class="
					text-5xl
					md:text-6xl
					xl:text-8xl
					font-bold
					text-white
					text-center
				"
			>
				Welcome to<br /><span class="text-amber-500">FortHub</span>
			</h1>
			<h2 class="text-lg md:text-xl xl:text-2xl text-white text-center">
				Lorem ipsum dolor sit amet consectetur adipisicing elit.<br>
				Accusamus minima quia id assumenda, quae corrupti illum consectetur!
			</h2>
			<button
				type="button"
				aria-label="Вперед!"
				class="
					px-5
					py-3
					inline-flex
					items-center
					justify-start
					text-2xl
					font-medium
					text-neutral-800
					bg-amber-500
					rounded-lg
					hover:opacity-90
					transition-opacity
				"
				on:click={() => { scrollTo('#tours') }}
			>
				Go Tour!
			</button>

		</div>
		
	</div>

</section>

<div class="md:container md:mx-auto">
	<section id="tours" class="mt-10 p-4 scroll-mt-14">
		<h3 class="mb-4 text-2xl">tours</h3>
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus minima quia id assumenda, quae corrupti illum consectetur! Similique delectus nihil ipsam dicta inventore natus iste nisi, dolorem ipsa iure cumque!</p>
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus minima quia id assumenda, quae corrupti illum consectetur! Similique delectus nihil ipsam dicta inventore natus iste nisi, dolorem ipsa iure cumque!</p>
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus minima quia id assumenda, quae corrupti illum consectetur! Similique delectus nihil ipsam dicta inventore natus iste nisi, dolorem ipsa iure cumque!</p>
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus minima quia id assumenda, quae corrupti illum consectetur! Similique delectus nihil ipsam dicta inventore natus iste nisi, dolorem ipsa iure cumque!</p>
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus minima quia id assumenda, quae corrupti illum consectetur! Similique delectus nihil ipsam dicta inventore natus iste nisi, dolorem ipsa iure cumque!</p>
	</section>
	
	<section id="about" class="mt-10 p-4 scroll-mt-14">
		<h3 class="mb-4 text-2xl">about</h3>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis facilis vel expedita possimus earum et consequuntur reiciendis, unde doloremque, animi aperiam magni esse rem obcaecati voluptatum culpa labore dolores illo!</p>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis facilis vel expedita possimus earum et consequuntur reiciendis, unde doloremque, animi aperiam magni esse rem obcaecati voluptatum culpa labore dolores illo!</p>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis facilis vel expedita possimus earum et consequuntur reiciendis, unde doloremque, animi aperiam magni esse rem obcaecati voluptatum culpa labore dolores illo!</p>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis facilis vel expedita possimus earum et consequuntur reiciendis, unde doloremque, animi aperiam magni esse rem obcaecati voluptatum culpa labore dolores illo!</p>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis facilis vel expedita possimus earum et consequuntur reiciendis, unde doloremque, animi aperiam magni esse rem obcaecati voluptatum culpa labore dolores illo!</p>
	</section>
</div>

<svelte:head>
	<title>FortHub - экскурсии по фортам финского залива</title>
	<meta name="description" content="FortHub site" />
	<meta name="keywords" content="кронштадт, экскурсии, форты" />
</svelte:head>

<script>
import welcome from '$lib/images/back.webp';
// import welcome_fallback from '$lib/images/back.jpg';

const scrollTo = id => {
	document.querySelector(id).scrollIntoView({ behavior: 'smooth' });
};
</script>
