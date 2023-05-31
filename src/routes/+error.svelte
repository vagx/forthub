<script>
    import { page } from '$app/stores';
</script>

<h1 class="pt-10 flex justify-center text-3xl text-red-500">{$page.status}: {$page.error.message}</h1>
