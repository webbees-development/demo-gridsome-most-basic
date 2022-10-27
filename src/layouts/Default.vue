<template>
  <div class="layout">
    <Header />
    <main>
      <slot/>
    </main>
  </div>
</template>

<script>
import Header from '~/components/Header.vue';

export default {
  components: {
    Header
  }
}
</script>


<style>
main {
  max-width: 600px;
  margin-inline: auto;
  margin-block: 3rem 5rem;
}

main > * + * {
  margin-block-start: 1rem;
}

img {
  display: block;
  max-width: 100%;
}
</style>
