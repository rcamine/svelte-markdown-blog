<script>
  import Footer from '@components/footer.svelte'
  import Nav from '@components/nav.svelte'
  import { onMount } from 'svelte'
  import { themeChange } from 'theme-change'
  import '../app.css'
  import '../prism.css'

  onMount(async () => {
    themeChange(false)
  })
</script>

<Nav />

<main class="mx-auto px-4 max-w-[90ch] min-h-[75vh] relative sm:px-6 lg:px-8 break-normal">
  <slot />
</main>

<Footer />
