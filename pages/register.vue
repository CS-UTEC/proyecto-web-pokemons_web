<template>
  <b-container class="pr-4 pl-4">
    <b-row class="banner" align-v="center" align-h="center">
      <b-col md="1">
        <img
          src="~/static/img/LOGO-OFICIAL-MEOWTEC.png"
          alt="Meowtec"
          class="img-brand"
          height="150"
          width="150"
        />
      </b-col>
      <b-col md="11" class="text-center">
        <span class="text-uppercase text-white">
          solicitud de albergue gatuno
        </span>
      </b-col>
    </b-row>
    <b-row class="info" align-v="center">
      <b-col md="4">
        <b-row align-h="center" class="violet info-title"
          >¿Qué es Meowtec?</b-row
        >
        <b-row class="p-info" align-content="center"
          >Es una organización conformada por estudiantes de ingeniería y
          ciencias con el propósito de mejorar la vida de los gatos callejeros
          de nuestro país.</b-row
        >
      </b-col>
      <b-col md="4" class="yellow-circles">
        <b-row align-h="center" class="violet info-title pr-3 pl-3"
          >¿Cuáles son los requisitos para pertenecer a Meowtec?</b-row
        >
        <b-row class="p-info">
          <p>
            Pueden aplicar todos los albergues que tengan
            <span class="blue">más de 6 gatos</span> en situación de rescatados
            con un mínimo de creación de 1 año.
          </p>
        </b-row>
      </b-col>
      <b-col md="4">
        <b-row align-h="center" class="violet info-title"
          >¿Por qué utilizar la web de Meowtec?</b-row
        >
        <b-row class="p-info" align-content="center"
          >Porque somos una plataforma gratuita que verificará y respaldará su
          albergue brindando seguridad y confianza para las personas que quieran
          ayudar.</b-row
        >
      </b-col>
    </b-row>
    <b-row class="mt-5">
      <div class="form-register">
        <!-- Hablanos de ti -->
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/38.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                háblanos de ti
              </div>
            </b-row>
            <b-row align-h="around" align-v="center">
              <b-col>
                ¿Eres el representante del albergue?
              </b-col>
              <b-col class="m-0 p-0">
                <b-form-radio-group
                  id="radio-boxes"
                  v-model="form.owner"
                  :options="options"
                  name="radio-options"
                >
                </b-form-radio-group>
              </b-col>
            </b-row>
            <b-row>
              <b-col>
                <label for="nombres">Nombres</label>
                <b-input
                  id="nombres"
                  v-model="form.name"
                  placeholder="Nombres"
                ></b-input>
                <br />
                <label for="telf">Celular</label>
                <b-input
                  id="telf"
                  v-model="form.cellphone"
                  type="tel"
                  placeholder="+51"
                ></b-input>
              </b-col>
              <b-col>
                <label for="apellidos">Apellidos</label>
                <b-input
                  id="apellidos"
                  v-model="form.lastname"
                  placeholder="Apellidos"
                ></b-input>
                <br />
                <label for="correo">Correo</label>
                <b-input
                  id="correo"
                  v-model="form.mail"
                  type="email"
                  placeholder="ejemplo@mail.com"
                ></b-input>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <!-- Hablanos sobre el albergue -->
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/37.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                háblanos del albergue
              </div>
            </b-row>
            <b-row>
              <b-col>
                <label for="type">¿A quiénes albergas?</label>
                <b-form-select
                  id="type"
                  v-model="form.type"
                  :options="type.options"
                  value="null"
                ></b-form-select>
              </b-col>
              <b-col>
                <label for="quantity">¿Cuántos gatos albergas?</label>
                <b-input
                  id="quantity"
                  v-model="form.quantity"
                  type="number"
                  placeholder="Más de 6"
                  :state="validateQuantity"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="4">
                <div class="line3"></div>
              </b-col>
              <b-col md="4">
                <div class="text-uppercase blue form-header text-center">
                  datos del albergue
                </div>
              </b-col>
              <b-col md="4">
                <div class="line3"></div>
              </b-col>
            </b-row>
            <b-row align-h="center">
              <div class="text-center gray-strong">
                Esta información es solo para fin de registro y futuras mejoras,
                <strong>NO</strong> será publicado.
              </div>
            </b-row>
            <b-row>
              <b-col md="8">
                <label for="albergue">Nombre del albergue</label>
                <b-input
                  id="albergue"
                  v-model="form.refuge"
                  placeholder="Albergue"
                ></b-input>
              </b-col>
              <b-col md="4">
                <label for="years">Años Fundación</label>
                <b-input
                  id="years"
                  v-model="form.years"
                  type="number"
                  placeholder="Mayor a 1"
                  :state="validateYears"
                ></b-input>
              </b-col>
            </b-row>
            <b-row>
              <b-col md="8">
                <label for="address">Dirección</label>
                <b-input
                  id="address"
                  v-model="form.address"
                  placeholder="Calle/Pasaje/Avenida/Jirón"
                ></b-input>
              </b-col>
              <b-col md="4">
                <label for="urbanization" class="text-white">_</label>
                <b-input
                  id="urbanization"
                  v-model="form.urbanization"
                  placeholder="Urb/Mz"
                ></b-input>
              </b-col>
            </b-row>
            <b-row>
              <b-col>
                <b-input
                  id="district"
                  v-model="form.district"
                  placeholder="Distrito"
                ></b-input>
              </b-col>
              <b-col>
                <b-input
                  id="city"
                  v-model="form.city"
                  placeholder="Ciudad"
                ></b-input>
              </b-col>
              <b-col>
                <b-input
                  id="department"
                  v-model="form.department"
                  placeholder="Departamento"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col>
                ¿De qué tamaño aproximado es el albergue?
              </b-col>
              <b-col>
                <b-input
                  id="size"
                  v-model="form.size"
                  class="size"
                  placeholder="m2"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col>
                Material de construcción:
              </b-col>
              <b-col>
                <b-input
                  id="material"
                  v-model="form.material"
                  placeholder="Noble/Rústico"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col>
                Gasto mensual aproximado en mantenimiento:
              </b-col>
              <b-col>
                <b-input
                  id="budget"
                  v-model="form.budget"
                  type="number"
                  placeholder="S/."
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col>
                ¿El albergue le pertenece o paga por alquiler del lugar?
              </b-col>
              <b-col>
                <b-form-radio-group
                  id="owner-options"
                  v-model="form.own"
                  :options="optionsOwn"
                  name="owner-options"
                >
                </b-form-radio-group>
              </b-col>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col>
                ¿Cuántos voluntarios te ayudan?
              </b-col>
              <b-col>
                <b-input
                  id="volunteers"
                  v-model="form.volunteers"
                  type="number"
                  placeholder="nº voluntarios"
                ></b-input>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <!-- Fotos de los gatos del albergue -->
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/36.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                fotos de los gatos del albergue
              </div>
            </b-row>
            <b-row>
              <div class="gray-strong">
                Se verificará una foto por cada gato, adjuntar mínimo 6 fotos,
                además de completar sus datos (Nombres, edad y si está en
                proceso de adopción). Si está en proceso de
                <strong>ADOPCIÓN</strong>, mostraremos su foto en la sección de
                <strong>ADOPTA</strong> de nuestra página.
              </div>
            </b-row>
            <b-row>
              <v-card
                v-for="(cat, index) in form.cats"
                :key="index"
                width="374"
                class="mx-auto m-2"
              >
                <div class="image-upload">
                  <label :for="index" class="cat-photo">
                    <b-img
                      class="cat-photo"
                      :src="cat.src === '' ? photoPlaceholder : cat.src"
                    ></b-img>
                  </label>
                  <input
                    :id="index"
                    ref="inputFile"
                    accept="image/*"
                    type="file"
                    @change="onFileChange(index, $event)"
                  />
                </div>
                <v-card-text class="p-1">
                  <b-container class="p-0">
                    <b-row align-v="center">
                      <b-col md="3" class="p-0">
                        Nombre:
                      </b-col>
                      <b-col class="p-0">
                        <b-input
                          :id="'name' + index"
                          v-model="cat.nombre"
                        ></b-input>
                      </b-col>
                    </b-row>
                    <b-row align-v="center">
                      <b-col md="3" class="p-0">
                        Edad:
                      </b-col>
                      <b-col class="p-0">
                        <b-input
                          :id="'edad' + index"
                          v-model="cat.edad"
                          type="number"
                          placeholder="meses"
                          style="text-align: right;"
                        ></b-input>
                      </b-col>
                    </b-row>
                    <b-row align-v="center">
                      <b-col md="3" class="p-0">
                        Adopción:
                      </b-col>
                      <b-col class="p-0">
                        <b-form-select
                          :id="'adopta' + index"
                          v-model="cat.adopta"
                          :options="type.optionsAdopt"
                          value="null"
                        ></b-form-select>
                      </b-col>
                    </b-row>
                  </b-container>
                  <div></div>
                </v-card-text>
              </v-card>
            </b-row>
          </b-col>
        </b-row>
        <!-- Canales de Donación -->
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/35.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                canales de donación
              </div>
            </b-row>
            <b-row align-h="around" align-v="center">
              <b-col>
                <div>
                  ¿Aceptas donaciones de galletas, arena, medicinas, etc.?
                </div>
                <br />
                <div>
                  ¿Aceptas apoyo de voluntarios que visiten tu albergue?
                </div>
              </b-col>
              <b-col class="m-0 p-0">
                <b-form-radio-group
                  id="radio-donations"
                  v-model="form.donations"
                  :options="options"
                  name="radio-donations"
                >
                </b-form-radio-group>
                <br />
                <b-form-radio-group
                  id="radio-aceptVolunteers"
                  v-model="form.aceptVolunteers"
                  :options="options"
                  name="radio-aceptVolunteers"
                >
                </b-form-radio-group>
              </b-col>
            </b-row>
            <b-row align-h="center">
              <div class="info-title text-uppercase blue">
                cuentas bancarias
              </div>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  bcp
                </div>
              </b-col>
              <b-col md="5">
                <b-input
                  id="bcp"
                  v-model="form.bcp"
                  type="number"
                  maxlength="12"
                  placeholder="nº de cuenta (12 dígitos)"
                ></b-input>
              </b-col>
              <b-col md="5">
                <b-input
                  id="bcp-cci"
                  v-model="form.bcpCci"
                  type="number"
                  maxlength="15"
                  placeholder="nº interbancario (15 dígitos)"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  interbank
                </div>
              </b-col>
              <b-col md="5">
                <b-input
                  id="interbank"
                  v-model="form.interbank"
                  type="number"
                  maxlength="12"
                  placeholder="nº de cuenta (12 dígitos)"
                ></b-input>
              </b-col>
              <b-col md="5">
                <b-input
                  id="interbank-cci"
                  v-model="form.interbankCci"
                  type="number"
                  maxlength="15"
                  placeholder="nº interbancario (15 dígitos)"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  bbva
                </div>
              </b-col>
              <b-col md="5">
                <b-input
                  id="bbva"
                  v-model="form.bbva"
                  type="number"
                  maxlength="12"
                  placeholder="nº de cuenta (12 dígitos)"
                ></b-input>
              </b-col>
              <b-col md="5">
                <b-input
                  id="bbva-cci"
                  v-model="form.bbvaCci"
                  type="number"
                  maxlength="15"
                  placeholder="nº interbancario (15 dígitos)"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  yape
                </div>
              </b-col>
              <b-col md="5">
                <b-input
                  id="yape"
                  v-model="form.yape"
                  type="number"
                  maxlength="9"
                  placeholder="nº de cuenta (9 dígitos)"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  paypal
                </div>
              </b-col>
              <b-col md="10">
                <b-input
                  id="paypal"
                  v-model="form.paypal"
                  type="email"
                  placeholder="correo electrónico"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  Otro
                </div>
              </b-col>
              <b-col md="5">
                <b-input
                  id="other"
                  v-model="form.other"
                  placeholder="Banco/Entidad"
                ></b-input>
              </b-col>
              <b-col md="5">
                <b-input
                  id="other-cci"
                  v-model="form.otherCci"
                  maxlength="15"
                  placeholder="nº interbancario (15 dígitos)"
                ></b-input>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/34.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                contacto
              </div>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  facebook
                </div>
              </b-col>
              <b-col md="10">
                <b-input
                  id="facebook"
                  v-model="form.facebook"
                  placeholder="link de Facebook"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  instagram
                </div>
              </b-col>
              <b-col md="10">
                <b-input
                  id="instagram"
                  v-model="form.instagram"
                  placeholder="@cuenta"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  correo
                </div>
              </b-col>
              <b-col md="10">
                <b-input
                  id="email"
                  v-model="form.email"
                  placeholder="albergue@gmail.com"
                ></b-input>
              </b-col>
            </b-row>
            <b-row align-v="center">
              <b-col md="2">
                <div class="text-uppercase">
                  otro
                </div>
              </b-col>
              <b-col md="10">
                <b-input
                  id="otherContact"
                  v-model="form.otherContact"
                  placeholder="Otro"
                ></b-input>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row>
          <b-col md="3">
            <b-img
              class="numbers"
              src="~/static/img/33.png"
              alt=""
              fluid
            ></b-img>
          </b-col>
          <b-col md="9">
            <b-row>
              <div class="form-header text-uppercase violet">
                recomendaciones (opcional)
              </div>
            </b-row>
            <b-row align-h="center" align-v="center">
              <b-col md="6" class="p-0">
                <b-row class="text-center">
                  ¿Nos puedes recomendar alguna veterinaria de costo social o
                  algún doctor veterinario, etc?
                </b-row>
              </b-col>
              <b-col md="6" class="p-0">
                <b-row align-h="center">
                  Comentarios libres
                </b-row>
              </b-col>
            </b-row>
            <b-row>
              <b-col md="6" class="p-0">
                <b-row>
                  <textarea
                    id="recomendations"
                    v-model="form.recomendations"
                    class="form-control"
                    rows="5"
                  ></textarea>
                </b-row>
              </b-col>
              <b-col md="6" class="p-0">
                <b-row>
                  <textarea
                    id="freeComments"
                    v-model="form.freeComments"
                    class="form-control"
                    rows="5"
                  ></textarea>
                </b-row>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <br />
        <b-row>
          <b-col md="11" offset="1">
            <div>
              <b-form-checkbox
                id="checkbox-1"
                v-model="form.terms"
                name="checkbox-1"
                value="Aceptado"
                unchecked-value="No aceptado"
              >
                Acuerdo de confidencialidad: (*) De conformidad con la Ley Nº
                29733, Ley de Protección de Datos Personales, la Universidad de
                Ingeniería y Tecnología le informa que los datos personales que
                usted nos ha facilitado serán tratados acorde a nuestra Política
                de Privacidad que puede revisar en el siguiente link:
                http://bit.ly/2F7OCQr
              </b-form-checkbox>

              <div>
                Estado:
                <strong
                  :class="{
                    red: form.terms === 'No aceptado',
                    green: form.terms === 'Aceptado',
                  }"
                  >{{ form.terms }}</strong
                >
              </div>
            </div>
          </b-col>
        </b-row>
        <br />
        <b-row>
          <b-col md="11" offset="1">
            <div>
              <b-form-checkbox
                id="checkbox-2"
                v-model="form.accept"
                name="checkbox-2"
                value="Aceptado"
                unchecked-value="No aceptado"
              >
                Confirmo que la información proporcionada en esta solicitud es
                exacta y completa. Meowtec verificará que cumplan con las
                directrices de esta plataforma.
              </b-form-checkbox>
              <div>
                Estado:
                <strong
                  :class="{
                    red: form.accept === 'No aceptado',
                    green: form.accept === 'Aceptado',
                  }"
                  >{{ form.accept }}</strong
                >
              </div>
            </div>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-button type="submit" variant="violet" @click="onSubmit"
            >Enviar Solicitud</b-button
          >
        </b-row>
      </div>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    data() {
      return {
        aceptado: false,
        form: {
          name: '',
          lastname: '',
          cellphone: '',
          mail: '',
          type: null,
          quantity: null,
          refuge: '',
          owner: 'si',
          own: 'propio',
          years: null,
          address: '',
          urbanization: '',
          district: '',
          city: '',
          department: '',
          size: null,
          budget: null,
          volunteers: null,
          material: '',
          donations: 'si',
          aceptVolunteers: 'si',
          bcp: '',
          interbank: '',
          bbva: '',
          yape: '',
          paypal: '',
          other: '',
          bcpCci: '',
          interbankCci: '',
          bbvaCci: '',
          facebook: '',
          instagram: '',
          email: '',
          otherContact: '',
          recomendations: '',
          freeComments: '',
          terms: 'No aceptado',
          accept: 'No aceptado',
          cats: [
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
            {
              nombre: '',
              edad: '',
              adopta: null,
              file: null,
              src: '',
            },
          ],
        },
        photoPlaceholder: require('../static/img/38.jpg'),
        options: [
          { text: 'Sí', value: 'si' },
          { text: 'No', value: 'no' },
        ],
        optionsOwn: [
          { text: 'Propio', value: 'propio' },
          { text: 'Alquilado', value: 'alquilado' },
        ],
        type: {
          options: [
            { text: 'Elige...', value: null },
            'Gatos',
            'Gatos y Perros',
            'Otros',
          ],
          optionsAdopt: [{ text: 'Elige...', value: null }, 'Si', 'No'],
        },
      }
    },
    computed: {
      validateQuantity() {
        return this.form.quantity >= 6
      },
      validateYears() {
        return this.form.years > 1
      },
    },
    methods: {
      onFileChange(index, e) {
        const file = e.target.files[0]
        this.form.cats[index].file = e.target.files[0]
        const reader = new FileReader()
        reader.onload = (e) => {
          this.form.cats[index].src = e.target.result
        }
        reader.readAsDataURL(file)
      },
      async onSubmit() {
        const url = '/albergue'
        const formData = new FormData()
        const admin = {
          nombre: this.form.name,
          apellidos: this.form.lastname,
          representante: this.form.owner === 'si',
          celular: this.form.cellphone,
          correo: this.form.mail,
        }
        const albergue = {
          nombre: this.form.refuge,
          anios: this.form.years,
          direccion: this.form.address,
          urbanizacion: this.form.urbanization,
          distrito: this.form.district,
          ciudad: this.form.city,
          departamento: this.form.department,
          tamanio: this.form.size,
          material: this.form.material,
          gasto: this.form.budget,
          pertenencia: this.form.own === 'propio',
          voluntarios: this.form.volunteers,
          albergan: this.form.type,
          num_gatos: this.form.quantity,
          acep_donaciones: this.form.donations === 'si',
          acep_apoyo: this.form.aceptVolunteers === 'si',
          banco_name: 'bcp',
          banco_number: this.form.bcp,
          banco_cci: this.form.bcpCci,
          facebook: this.form.facebook,
          instagram: this.form.instagram,
          correo: this.form.email,
          otro_contacto: this.form.otherContact,
        }
        const gato0 = {
          nombre: this.form.cats[0].nombre,
          edad: this.form.cats[0].edad,
          adopcion: this.form.cats[0].adopta === 'Si',
        }
        const gato1 = {
          nombre: this.form.cats[1].nombre,
          edad: this.form.cats[1].edad,
          adopcion: this.form.cats[1].adopta === 'Si',
        }
        const gato2 = {
          nombre: this.form.cats[2].nombre,
          edad: this.form.cats[2].edad,
          adopcion: this.form.cats[2].adopta === 'Si',
        }
        const gato3 = {
          nombre: this.form.cats[3].nombre,
          edad: this.form.cats[3].edad,
          adopcion: this.form.cats[3].adopta === 'Si',
        }
        const gato4 = {
          nombre: this.form.cats[4].nombre,
          edad: this.form.cats[4].edad,
          adopcion: this.form.cats[4].adopta === 'Si',
        }
        const gato5 = {
          nombre: this.form.cats[5].nombre,
          edad: this.form.cats[5].edad,
          adopcion: this.form.cats[5].adopta === 'Si',
        }
        const data = {
          admin,
          albergue,
          gato0,
          gato1,
          gato2,
          gato3,
          gato4,
          gato5,
        }
        for (let i = 0; i < 6; i++) {
          const file = this.form.cats[i].file
          formData.append('files[' + i + ']', file)
          /* eslint-disable */
          /* console.log(formData) */
        }
        formData.append('data', JSON.stringify(data))
        /* eslint-disable */
        await this.$axios
          .$post(url, formData, {
            headers: { 'Content-Type': false, processData: false },
          })
          .then((res) => {
            // this.aceptado = res
            console.log(res)
            this.$router.push('/login')
          })
          .catch((e) => {
            console.log('Problemas')
            console.log(e)
          })
      },
    },
  }
</script>
