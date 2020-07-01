<template>
  <div class="c-news-letter-from d-flex flex-column align-items-center">
    <div class="my-5 title-form">unisciti alla nostra community di <b>design lovers</b></div>

    <ValidationProvider rules="email|required" v-slot="{ errors }">
      <b-form-input
        v-model="form.email"
        type="text"
        placeholder="Inserisci la tua email"
        class="mb-2"
      />
      {{ errors }}
    </ValidationProvider>

    <b-button class="button-form my-4">INVIA</b-button>

    <b-form-checkbox
      class="d-none d-lg-block mt-4"
      v-model="form.privacyStatus"
      value="accepted"
      unchecked-value="not_accepted"
    >
      Accetto l'informativa
      <a href="https://www.iubenda.com/privacy-policy/7828472/legal?ifr=true&height=581" target="blank"> sulla privacy</a>
    </b-form-checkbox>
  </div>
</template>

<script>
import { ValidationProvider } from 'vee-validate'

export default {
  components: {
    ValidationProvider
  },
  data () {
    return {
      form: {
        email: '',
        privacyStatus: 'not_accepted'
      }
    }
  }
}
</script>

<style lang="scss" scoped>

  .c-news-letter-from {

    .title-form {
      font-size: 1.4rem;
      text-align: center;
    }

    .button-form {
      @media (min-width: 992px) {
        background-color: #111724;
        width: 100px;
      }
    }
  }
</style>
