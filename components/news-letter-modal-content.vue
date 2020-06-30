<template>
  <b-row>
    <b-col class="image-section" cols="6">
      <div class="image-overlay" />
      <div class="text-section d-flex align-items-center justify-content-center">
        <div class="text-center font-weight-bold">
          trova la tua icona <br /> nella prossima newsletter
        </div>
      </div>
    </b-col>
    <b-col cols="6">
      newsletter Form
    </b-col>
  </b-row>
</template>

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
