<template>
  <b-row>
    <b-col class="image-section" lg="6">
      <div class="image-overlay" />
      <div class="text-section d-flex align-items-center justify-content-center flex-wrap">
        <div class="text-center font-weight-bold text-justify text-last-center">
          TROVA LA TUA ICONA <br /> NELLA PROSSIMA NEWSLETTER
        </div>
        <news-letter-form v-if="isMobileDevice" />
      </div>
    </b-col>
    <b-col v-if="!isMobileDevice" lg="6" class="px-5 py-5 mt-5">
      <news-letter-form />
    </b-col>
  </b-row>
</template>

<script>
import { isMobile } from 'mobile-device-detect'
import newsLetterForm from '~/components/news-letter/news-letter-form'

export default {
  components: {
    newsLetterForm
  },
  computed: {
    isMobileDevice () {
      return isMobile
    }
  }
}
</script>

<style lang="scss" scoped>

  .row {
    width: 100%;
    margin: 0;

    [class*="col-"] {
      padding: 0;
    }
  }

  .image-section {
    position: relative;
    overflow: hidden;
    min-height: 500px;

    .image-overlay {
      width: 100%;
      height: 100%;
      background: linear-gradient(to right, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
        url('~assets/images/news-letter-bg.jpg') left center;
      transform: scaleX(-1);
    }

    .text-section {
      color: white;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      font-size: 1.5rem;

      @media (max-width: 991px) {
        padding: 20px 30px;
      }
    }
  }
</style>
