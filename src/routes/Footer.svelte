<footer
	class="
		mt-10
		p-6
		flex
		flex-col
		items-start
		justify-center
		md:flex-row
		gap-4
		md:gap-10
		bg-neutral-100
		dark:bg-neutral-900
		scroll-mt-14
	"
	id="contacts"
>
	<img src={forthub} width="114" height="40" alt="FortHub logo" />
	<div>
		<h3 class="mb-4 uppercase">Контакты</h3>
		<ul class="flex flex-col gap-5 md:gap-4">
			{#each contacts as contact}
				<li>
					<a href={contact.link} class="flex items-center">
						<Icon d={contact.icon} />
						<span class="ml-2 text-amber-800 dark:text-amber-200 hover:underline">{contact.phone}</span>
					</a>
				</li>
			{/each}
		</ul>
	</div>
	<div>
		<h3 class="mb-4 uppercase">Социальные сети</h3>
		<ul class="flex flex-col gap-5 md:gap-4">
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

const contacts = [
	{ link: 'tel:+79991111111', phone: '+7 999 111 1111', icon: mdiPhone },
	{ link: 'tel:+79992222222', phone: '+7 999 222 2222', icon: mdiPhone },
];

const socials = [
	{ link: '/', label: 'VK group', icon: siVk },
	{ link: '/', label: 'Telegram channel', icon: siTelegram },
	{ link: '/', label: 'Whatsapp group', icon: siWhatsapp },
	{ link: '/', label: 'Instagram', icon: siInstagram },
];
</script>
