<script context="module">
  import { siteName } from '@lib/site-config'
  
  export async function load({ fetch, page: { params } }) {
    const { slug } = params
    const res = await fetch(`/posts/${slug}.json`)
    
    if (res.ok) {
      const { post } = await res.json()
      return {
        props: { post },
      }
    }
  }
</script>

<script>
  import Head from '$lib/components/head.svelte'

  export let post

  let { html, date, title, readingTime } = post
</script>

<Head title={`${siteName} | ${title}`} />

<article class="flex flex-col flex-grow">
  <h1 class="font-bold mb-5 text-5xl">{title}</h1>
  <div>
    <div class="mb-8">
      <time>{new Date(date).toLocaleDateString()}</time> • 
      <span>{readingTime.text}</span> • 
      {#each post.tags as tag} 
       <a href="/tags/{tag}" class="font-bold hover:text-accent-focus pr-1 hover:link">{`#${tag}`}</a>
      {/each}
    </div>

    <article class="all-prose mb-10">
      {@html html}
    </article>
  </div>
</article>