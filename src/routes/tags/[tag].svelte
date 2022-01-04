<script context="module">

    import { description } from '@lib/site-config'

    export async function load({ fetch, page }) {
        const res = await fetch(`/posts.json`)
        const tag = page.params.tag;

        if (res.ok) {
            const { posts } = await res.json()

            const postsWithTag = posts.filter((post) => {
                return post.tags.includes(tag) && post.published;
            });

            return {
                props: { postsWithTag, tag },
            }
        }
    }
</script>
  
<script>
    import Head from '$lib/components/head.svelte'
    import PostCard from '$lib/components/post-card.svelte'

    export let description
    export let postsWithTag
    export let tag
</script>
  
<Head title={description} />

<div class="mb-2">
    <span class="font-normal text-xl pr-1">Tag:</span>
    <a href="/tags/{tag}" class="font-semibold text-xl text-accent-focus">{tag}</a>
</div>
<div class="divider mb-8"></div> 
<div class="flex flex-col flex-grow">
    {#each postsWithTag as post}
        {#if post.published}
        <PostCard {post} />
        {/if}
    {/each}
</div>
