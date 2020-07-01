<template>
  <b-row>
    <b-col class="image-section" lg="6">
      <div class="image-overlay" />
      <div class="text-section d-flex align-items-center justify-content-center">
        <div class="text-center font-weight-bold">
          TROVA LA TUA ICONA <br /> NELLA PROSSIMA NEWSLETTER
        </div>
      </div>
    </b-col>
    <b-col lg="6" class="px-5 py-5 mt-5">
      <news-letter-form />
    </b-col>
  </b-row>
</template>

<script>
import newsLetterForm from '~/components/news-letter/news-letter-form'

export default {
  components: {
    newsLetterForm
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
      font-size: 1.8rem;
    }
  }
</style>
