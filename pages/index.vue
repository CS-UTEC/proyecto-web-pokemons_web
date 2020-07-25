<template>
  <div class="container">
    <b-row>
      <b-col md="5">
        <div class="container1">
          <div>
            <b-img class="heart" src="~/static/img/3.png" alt="" fluid></b-img>
          </div>
          <div class="text-uppercase first-line blue">
            esterilizar
          </div>
          <div class="text-uppercase second-line violet">
            es un gesto de
          </div>
          <div class="text-uppercase first-line blue">
            humanidad
          </div>
          <div class="line mt-5 mb-5"></div>
          <div>
            <b-img
              class="cats1"
              src="~/static/img/2.png"
              alt=""
              fluid-grow
            ></b-img>
          </div>
        </div>
      </b-col>
      <b-col md="7">
        <iframe
          class="meowtec-vid"
          :src="videoSrc"
          frameborder="0"
          allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </b-col>
    </b-row>
    <b-row class="mt-5" align-v="center">
      <b-col md="7">
        <div class="line2"></div>
      </b-col>
      <b-col md="5">
        <div class="text-uppercase blue header2">
          ¿Cómo puedes <span class="yellow">ayudarlos</span>?
        </div>
      </b-col>
    </b-row>
    <b-container fluid class="second-container">
      <b-row align-h="center" class="rows">
        <b-col md="4" class="p-0">
          <div class="img-container">
            <b-img
              class="cats2"
              src="~/static/img/41.jpg"
              alt=""
              fluid-grow
            ></b-img>
            <span class="text-white text-uppercase img-name">albergues</span>
          </div>
        </b-col>
        <b-col md="8" class="blue-p">
          <p>
            Los albergues sirven como espacio de acogida a gatos y perros sin
            hogar, perdidos o abandonados. Debido a que en Lima existe una
            sobrepoblación de gatos, estos refugios no se abastecen y necesitan
            de mucha ayuda para mantener a los animales que ya rescataron.
            Conoce un poco más de los albergues dando click
            <a to="/albergues"><span class="yellow">aquí</span></a>
          </p>
        </b-col>
      </b-row>
      <b-row align-h="center" class="rows">
        <b-col md="4" class="yellow-p">
          <p>
            Un gatito en tu hogar es toda una aventura, tendrás a un compañero
            de por vida que alegrará tu vida día a día.
          </p>
        </b-col>
        <b-col md="4" class="p-0">
          <div class="img-container">
            <b-img
              class="cats2"
              src="~/static/img/42.jpg"
              alt=""
              fluid-grow
            ></b-img>
            <span class="text-white text-uppercase img-name">adopta</span>
          </div>
        </b-col>
        <b-col md="4" class="yellow-p">
          <p>
            ¿Estás listo para rescatar una vida? Puedes dar click
            <a to="/adopta"><span class="yellow">aquí</span></a> para ver a
            todos los gatitos que necesitan una segunda oportunidad.
          </p>
        </b-col>
      </b-row>
      <b-row align-h="center" class="rows">
        <b-col md="8" class="blue-p" align-h="center">
          <p>
            Atender a 20, 30, 50 o más de 100 gatitos no es fácil, necesitan
            apoyo de personas para alimentarlos, asearlos, construyéndoles
            casitas, etc. Puedes ayudar con unas pocas horas de tu tiempo, click
            <a to="/contacto"><span class="yellow">aquí</span></a> para más
            información.
          </p>
        </b-col>
        <b-col md="4" class="p-0">
          <div class="img-container">
            <b-img
              class="cats2"
              src="~/static/img/43.jpg"
              alt=""
              fluid-grow
            ></b-img>
            <span class="text-white text-uppercase img-name">voluntariado</span>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <b-row class="mt-5">
      <b-col md="3">
        <b-row>
          <b-img
            class="cats2"
            src="~/static/img/40.jpg"
            alt=""
            fluid-grow
          ></b-img>
        </b-row>
        <b-row>
          <div class="title text-center text-uppercase">
            agradecimientos
          </div>
        </b-row>
        <b-row class="p-2">
          <p class="grey-p mt-1">
            Todos estos gatitos fueron auxiliados, rescatados, llevados al
            veterinario, acompañados en su proceso de recuperación y adoptados.
            Gracias al apoyo de nuestros miembros salvamos muchas vidas
          </p>
        </b-row>
      </b-col>
      <b-col md="6">
        <b-row align-h="center">
          <div class="text-center text-uppercase first-line blue">
            nuestros casos de <span class="violet">éxito</span>
          </div>
        </b-row>
        <b-row>
          <b-img
            class="cats2 mt-3"
            src="~/static/img/46.jpg"
            alt=""
            fluid-grow
          ></b-img>
        </b-row>
        <b-row>
          <div class="line3 mt-5"></div>
        </b-row>
      </b-col>
      <b-col md="3">
        <b-row>
          <b-img
            class="cats2"
            src="~/static/img/39.jpg"
            alt=""
            fluid-grow
          ></b-img>
        </b-row>
        <b-row>
          <div class="title text-center text-uppercase">
            donaciones
          </div>
        </b-row>
        <b-row class="p-2">
          <p class="grey-p mt-1">
            Pueden ayudarnos con efectivo o donando galletitas, mantitas,
            camitas, etc.
            <br />
            <span class="blue">BCP:</span>
            <br />
            Renato Miranda
            <br />
            19197417321032
            <br />
            ICC: 002191197417732103254
            <br />
            <span class="blue">YAPE:</span>
            <br />
            Renato Miranda
            <br />
            969 476 236
            <br />
            <span class="blue">PAYPAL:</span>
            <br />
            meowtec@utec.edu.pe
          </p>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        videoSrc: 'https://www.youtube.com/embed/MNsTTYcblSY',
      }
    },
  }
</script>
