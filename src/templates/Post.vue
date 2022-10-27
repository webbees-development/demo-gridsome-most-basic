<template>
    <Layout>
        <article>
            <h1 v-html="$page.post.title" />
            <h3>By {{ $page.post.author }} on {{ $page.post.date }}</h3>
            <g-image :src="$page.post.thumbnail" style="width: 15rem" />
            <div v-html="$page.post.content" />
        </article>
    </Layout>
</template>

<page-query>
query Post ($path: String!) {
    post: post (path: $path) {
        id
        title
        author
        thumbnail
        date (format: "MMMM D, YYYY")
        content
        timeToRead
    }
}
</page-query>

<style scoped>
article {
    position: relative;
}

article > * + * {
    margin-block-start: 1rem;
}

img {
    position: absolute;

    left: -17rem;
    top: 0;

    margin: 0;
}
</style>