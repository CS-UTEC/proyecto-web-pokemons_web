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
          <b-col class="t-quicksand">
            <b-form-group label="Correo electrónico:" label-for="email">
              <b-form-input
                id="email"
                v-model="form.correo"
                type="email"
                required
                placeholder="Ingresa tu correo electrónico"
              ></b-form-input>
            </b-form-group>
            <br />
            <b-form-group label="Contraseña:" label-for="password">
              <b-form-input
                id="password"
                v-model="form.contrasenha"
                type="password"
                required
                placeholder="Ingresa tu contraseña"
              ></b-form-input>
            </b-form-group>
            <br />
            <br />
            <b-row align-h="center" class="t-quicksand">
              <b-button variant="violet" @click="onSubmit">Ingresar</b-button>
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
          correo: '',
          contrasenha: '',
        },
      }
    },
    methods: {
      async onSubmit() {
        const json = {
          correo: this.form.correo,
          contrasenha: this.form.contrasenha,
        }
        /* await this.$auth
          .loginWith('local', json)
          .then((res) => {
            this.$auth.setUser(res.data)
            this.$router.push('/')
          })
          .catch((e) => {
            console.log(e)
          }) */
        await this.$axios
          .post('/authenticate/' + json.correo + '/' + json.contrasenha)
          .then((res) => {
            this.$auth.setUser(res.data)
            this.$router.push('/')
          })
          .catch((e) => {
            console.log(e)
          })
      },
    },
  }
</script>
