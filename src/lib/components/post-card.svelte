<script>
  export let post
</script>

<article class="border border-neutral bg-base-200 shadow-lg mb-7 p-6 card transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-105 duration-300 hover:shadow-2xl">
    <div>
      <h2 class="font-black mt-5 mb-1 text-3xl hover:text-accent-focus">
        <a sveltekit:prefetch href={`/posts/${post.slug}`} class="">{post.title}</a>
      </h2>
      <div class="prose-sm mb-2">
        <time>{new Date(post.date).toLocaleDateString()}</time>
        •
        <span>{post.readingTime.text}</span>
        •
        {#each post.tags as tag}
          <a href="/tags/{tag}" class="font-semibold hover:text-accent-focus pr-1 hover:link">{`#${tag}`}</a>
        {/each}
      </div>
    </div>
</article>
