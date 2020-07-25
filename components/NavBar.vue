<template>
  <b-navbar toggleable="lg" type="light" variant="white" sticky>
    <b-row>
      <b-col class="p-0" align-self="start">
        <b-navbar-brand href="#">
          <img
            src="~/static/img/LOGO-OFICIAL-MEOWTEC.png"
            alt="Meowtec"
            class="img-brand"
            height="120"
            width="120"
          />
          <div class="brand"></div>
          <div class="brand2"></div>
        </b-navbar-brand>
      </b-col>
      <b-col class="p-0" md="7" sm="9" align-self="center">
        <b-navbar-nav>
          <b-row align-h="between">
            <b-col class="p-0 text-center">
              <b-nav-item class="item t-kollektif" to="/">
                Inicio
              </b-nav-item>
            </b-col>
            <b-col class="p-0 text-center">
              <b-nav-item class="item" to="/albergues">
                Albergues
              </b-nav-item>
            </b-col>
            <b-col class="p-0 text-center">
              <b-nav-item class="item" to="/adopta">
                Adopta
              </b-nav-item>
            </b-col>
            <b-col class="p-0 text-center">
              <b-nav-item class="item" to="/nosotros">
                Nosotros
              </b-nav-item>
            </b-col>
            <b-col class="p-0 text-center">
              <b-nav-item class="item" to="/contact">
                Contacto
              </b-nav-item>
            </b-col>
            <b-col md="3" class="p-0 text-center">
              <b-nav-item-dropdown
                class="item"
                text="Hola ¿Tienes un albergue?"
              >
                <b-dropdown-item
                  to="/register"
                  class="pb-2 drop-class text-center"
                  ><span class="text-uppercase login-line"
                    >Registrarme</span
                  ></b-dropdown-item
                >
                <b-dropdown-item to="/login" class="pb-2 drop-class text-center"
                  ><span class="text-uppercase login-line"
                    >Ingresar</span
                  ></b-dropdown-item
                >
              </b-nav-item-dropdown>
            </b-col>
          </b-row>
        </b-navbar-nav>
      </b-col>
    </b-row>
  </b-navbar>
</template>

<script>
  export default {}
</script>
