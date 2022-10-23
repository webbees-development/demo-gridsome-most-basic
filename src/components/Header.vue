<template>
    <header>
        <!-- <h2 v-html="$static.metadata.siteName">{{  }}</h2> -->
        <h2>{{ $static.metadata.siteName }}</h2>
        <nav>
            <g-link to="/">Home</g-link>
            <g-link to="/about">About</g-link>
            <g-link to="/blog">Blog</g-link>
        </nav>
    </header>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
}
</script>

<style lang="scss" scoped>
header {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: calc(100% - 12rem);
    padding: .5rem 6rem;
    background: $darkblue;
    color: $white;

    h2 {
        font-size: 1.4rem;
        font-weight: 500;
    }

    nav a {
        color: inherit;
        text-decoration: none;
        padding: 1rem;
        font-size: 1.2rem;
    }
}
</style>
