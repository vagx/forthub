<footer
	class="
		mt-10
		p-6
		flex
		flex-col
		justify-center
		md:flex-row
		gap-8
		bg-neutral-100
		dark:bg-neutral-900
		scroll-mt-14
	"
	id="contacts"
>
	<img src={forthub} width="114" height="40" alt="FortHub logo" />
	<div class="flex flex-col gap-4">
		<h3 class="uppercase">Контакты</h3>
		<a href="tel:+79991234567" class="flex items-center">
			<Icon d={mdiPhone} />
			<span class="ml-2 text-amber-800 dark:text-amber-200 hover:underline">+7 999 123 4567</span>
		</a>
	</div>
	<div class="flex flex-col gap-4">
		<h3 class="uppercase">Социальные сети</h3>
		<ul class="flex flex-col gap-4">
			{#each socials as social}
				<li>
					<a href={social.link} class="flex items-center">
						<Icon d={social.icon.path} />
						<span class="ml-2 text-amber-800 dark:text-amber-200 hover:underline">{social.label}</span>
					</a>
				</li>
			{/each}
		</ul>
	</div>
</footer>

<script>
import forthub from '$lib/images/forthub.svg';
import Icon from '$lib/components/Icon.svelte';
import { mdiPhone } from '@mdi/js';
import { siVk, siTelegram, siWhatsapp, siInstagram } from 'simple-icons';

const socials = [
	{ link: '/', label: 'vk group', icon: siVk },
	{ link: '/', label: 'telegram channel', icon: siTelegram },
	{ link: '/', label: 'Whatsapp group', icon: siWhatsapp },
	{ link: '/', label: 'Instagram', icon: siInstagram },
];
</script>
