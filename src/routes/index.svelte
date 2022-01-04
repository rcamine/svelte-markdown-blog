<script context="module">

  import { description } from '@lib/site-config'

  export async function load({ fetch }) {
    const res = await fetch(`/posts.json`)
    if (res.ok) {
      const { posts } = await res.json()
      return {
        props: { posts },
      }
    }
  }
</script>

<script>
  import Head from '$lib/components/head.svelte'
  import PostCard from '$lib/components/post-card.svelte'

  export let description
  export let posts
</script>

<Head title={description} />

<div class="flex flex-col flex-grow">
  {#each posts as post}
    {#if post.published}
      <PostCard {post} />
    {/if}
  {/each}
</div>
