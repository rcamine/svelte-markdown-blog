<script>
  import { authorName } from '@lib/site-config'

  export let title
  export let description
  export let url
</script>

<svelte:head>
  <link rel="canonical" href={url} />

  <!-- HTML Meta Tags -->
  <title>{title}</title>
  <meta name="description" content={description} />
  <meta name="author" content={authorName} />

  <!-- Google / Search Engine Tags -->
  <meta itemprop="name" content={title} />
  <meta itemprop="description" content={description} />
</svelte:head>
