<template>
  <b-container>
    <b-row>
      <b-col class="t-quicksand">
        <b-row align-h="center">
          <b-img class="numbers" src="~/static/img/4.png" alt="" fluid></b-img>
        </b-row>
        <br />
        <b-row align-v="center" align-h="center">
          <b-col md="2">
            <b-img
              class="numbers"
              src="~/static/img/5.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="10">
            <span class="contact">www.facebook.com/meowtec</span>
          </b-col>
        </b-row>
        <br />
        <b-row align-v="center">
          <b-col md="2">
            <b-img
              class="numbers"
              src="~/static/img/6.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="10">
            <span class="contact">@meowtec_utec</span>
          </b-col>
        </b-row>
        <br />
        <b-row align-v="center">
          <b-col md="2">
            <b-img
              class="numbers"
              src="~/static/img/7.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="10">
            <span class="contact"
              >https://chat.whatsapp.com/GGSM5QXqhd234warL0QD8B</span
            >
          </b-col>
        </b-row>
        <br />
        <b-row align-v="center">
          <b-col md="2">
            <b-img
              class="numbers"
              src="~/static/img/8.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="10">
            <span class="contact">https://discord.gg/3wdgpFu</span>
          </b-col>
        </b-row>
        <br />
        <b-row align-v="center">
          <b-col md="2">
            <b-img
              class="numbers"
              src="~/static/img/9.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="10">
            <span class="contact">meowtec@utec.edu.pe</span>
          </b-col>
        </b-row>
        <br />
      </b-col>
      <b-col>
        <b-row align-v="center">
          <b-col md="3">
            <div class="line3"></div>
          </b-col>
          <b-col md="6">
            <div class="t-bebas text-uppercase blue t-3 text-center">
              contáctanos
            </div>
          </b-col>
          <b-col md="3">
            <div class="line3"></div>
          </b-col>
        </b-row>
        <br />
        <br />
        <b-row>
          <b-col class="t-quicksand">
            <label for="nombres" class="t-fredoka">Nombres</label>
            <b-input
              id="nombres"
              v-model="form.name"
              placeholder="Nombres"
            ></b-input>
            <br />
            <label for="telf" class="t-fredoka">Celular</label>
            <b-input
              id="telf"
              v-model="form.cellphone"
              type="tel"
              placeholder="+51"
            ></b-input>
          </b-col>
          <b-col class="t-quicksand">
            <label for="apellidos" class="t-fredoka">Apellidos</label>
            <b-input
              id="apellidos"
              v-model="form.lastname"
              placeholder="Apellidos"
            ></b-input>
            <br />
            <label for="correo" class="t-fredoka">Correo</label>
            <b-input
              id="correo"
              v-model="form.mail"
              type="email"
              placeholder="ejemplo@mail.com"
            ></b-input>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="t-quicksand">
            <label for="message" class="t-fredoka">Mensaje:</label>
            <textarea
              id="message"
              v-model="form.message"
              class="form-control"
              rows="9"
              placeholder="Escribir algo aqui"
            ></textarea>
          </b-col>
        </b-row>
        <br />
        <b-row align-h="center">
          <b-button variant="violet">Enviar</b-button>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          name: '',
          lastname: '',
          mail: '',
          cellphone: '',
          message: '',
        },
      }
    },
  }
</script>
