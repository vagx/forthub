<svg
	xmlns="http://www.w3.org/2000/svg"
	viewBox="0 0 24 24"
	{fill}
	class="{classSize} {className}"
>
	<path {d} />
</svg>

<script>
export let color = 'currentColor';
export let size = 'md';
export let d = '';

const sizes = {
	sm: 'w-5 h-5',
	md: 'w-6 h-6',
	lg: 'w-7 h-7'
};

let fill = color === 'currentColor' ? color : `#${color}`;
let classSize = sizes[size] || sizes.md;
let className = '';
export { className as class };
</script>
