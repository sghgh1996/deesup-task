<template>
  <div class="c-news-letter-from d-flex flex-column align-items-center">
    <div class="my-5 title-form">
      unisciti alla nostra community di <b>design lovers</b>
    </div>

    <ValidationProvider
      v-slot="validationContext"
      rules="email|required"
    >
      <b-form-input
        v-model="form.email"
        type="text"
        placeholder="Inserisci la tua email"
        class="mb-2"
        aria-describedby="email-live-feedback"
        :state="getValidationState(validationContext)"
      />
      <b-form-invalid-feedback id="email-live-feedback">
        {{ validationContext.errors[0] }}
      </b-form-invalid-feedback>
    </ValidationProvider>

    <b-button class="button-form my-4">
      INVIA
    </b-button>

    <ValidationProvider
      v-slot="validationContext"
      rules="accepted"
    >
      <b-form-checkbox
        v-model="form.privacyStatus"
        class="d-none d-lg-block mt-4"
        value="accepted"
        unchecked-value="not_accepted"
      >
        Accetto l'informativa
        <a href="https://www.iubenda.com/privacy-policy/7828472/legal?ifr=true&height=581" target="blank"> sulla privacy</a>
      </b-form-checkbox>
      <b-form-invalid-feedback
        id="privacy-live-feedback"
        :state="getValidationState(validationContext)"
      >
        {{ validationContext.errors[0] }}
      </b-form-invalid-feedback>
    </ValidationProvider>
  </div>
</template>

<script>
import { ValidationProvider } from 'vee-validate'
import { extend } from 'vee-validate'
import { required, email } from 'vee-validate/dist/rules'

extend('email', {
  ...email,
  message: 'si prega di inserire una e-mail corretta'
})

extend('required', {
  ...required,
  message: 'Questo campo è obbligatorio'
})

extend('accepted', {
  validate: (value) => {
    return value === 'accepted'
  },
  message: 'accetta la privacy'
})

export default {
  components: {
    ValidationProvider
  },
  data () {
    return {
      form: {
        email: '',
        privacyStatus: ''
      }
    }
  },
  methods: {
    getValidationState ({ dirty, validated, valid = null }) {
      return dirty || validated ? valid : null
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
