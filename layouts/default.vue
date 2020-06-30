<template>
  <div>
    <Nuxt />
    <b-modal
      id="news-letter"
      hide-footer
      hide-header
      centered
      size="lg"
      body-class="newsletter-body"
    >
      <news-letter-modal-content />
    </b-modal>
  </div>
</template>

<script>
import newsLetterModalContent from '~/components/news-letter-modal-content'

export default {
  components: {
    newsLetterModalContent
  },
  mounted () {
    setTimeout(() => {
      this.$bvModal.show('news-letter')
    }, 2000)
  }
}
</script>

<style lang="scss">

  .newsletter-body {
    padding: 0;
  }
</style>
