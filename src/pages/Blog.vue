<template>
    <Layout>
        <main class="blog">
            <h1>Blog Posts</h1>

            <ul class="blog-list">
                <li v-for="post in $page.allPost.edges" v-bind:key="post.node.id">
                    <g-link :to="post.node.path">
                        <g-image :src="post.node.thumbnail" style="width: 250px" />
                        <span>{{post.node.title}}</span>
                    </g-link>
                </li>
            </ul>
        </main>
    </Layout>
</template>

<page-query>
query {
    allPost {
        totalCount
        edges {
            node {
                id
                title
                author
                thumbnail
                date (format: "MMMM D, YYYY")
                content
                timeToRead
                path
            }
        }
    }
}
</page-query>

<style lang="scss" scoped>
.blog-list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;

    a {
        display: block;

        text-decoration: none;
        color: black;
    }

    a:hover,
    a:focus-visible {
        font-weight: 700;
    }

    a:focus-visible {
        outline: none;
    }

    img {
        margin-inline: auto;

        aspect-ratio: 1.6;
        object-fit: cover;
    }

    li {
        text-align: center;

        background-color: rgb(244, 244, 244);
        padding: 1rem;
    }

    span {
        display: block;
        padding-block-start: 1rem;
    }
}
</style>