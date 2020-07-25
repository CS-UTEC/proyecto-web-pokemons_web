<template>
  <b-container>
    <b-row align-h="center">
      <b-col md="4">
        <b-row align-h="center">
          <b-img
            class="numbers"
            src="~/static/img/1.png"
            alt=""
            width="250"
            fluid
          ></b-img>
        </b-row>
        <br />
        <br />
        <b-row align-h="center">
          <b-col>
            <b-form-group label="Correo electrónico:" label-for="email">
              <b-form-input
                id="email"
                v-model="form.email"
                type="email"
                required
                placeholder="Ingresa tu correo electrónico"
              ></b-form-input>
            </b-form-group>
            <br />
            <b-form-group label="Contraseña:" label-for="password">
              <b-form-input
                id="password"
                v-model="form.password"
                type="password"
                required
                placeholder="Ingresa tu contraseña"
              ></b-form-input>
            </b-form-group>
            <br />
            <br />
            <b-row align-h="center">
              <b-button variant="violet">Ingresar</b-button>
            </b-row>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    auth: false,
    data() {
      return {
        form: {
          email: '',
          password: '',
        },
      }
    },
    methods: {
      async onSubmit() {
        await this.$auth
          .loginWith('local', { data: this.form })
          .then((res) => {
            this.$auth.setUser(res.data)
            this.$router.push('/')
          })
          .catch((e) => {
            // console.log(e)
          })
      },
    },
  }
</script>
