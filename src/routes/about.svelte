<script context="module">
	import { siteName } from '@lib/site-config'
</script>

<script>
	import Head from '$lib/components/head.svelte'

	export let siteName
</script>

<Head title={`${siteName} | About me`} />

