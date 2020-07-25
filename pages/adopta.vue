<template>
  <b-row align-h="center" class="mt-0 pl-3">
    <b-col md="3" class="colorDarken">
      <v-row justify="center" align="center" class="maxHeight">
        <v-text-field
          v-model="searchVideo"
          solo
          clearable
          append-icon="mdi-magnify"
        ></v-text-field>
      </v-row>
    </b-col>
    <b-col md="9" class="maxHeight">
      <b-row align-v="start" align-h="around">
        <v-card
          v-for="(gato, index) in handleSearch"
          :key="gato.nombre"
          outlined
          class="t-bebas m-2"
        >
          <v-list-item>
            <b-row align-h="center">
              <b-col>
                <b-img
                  class="cat-photo"
                  alt=""
                  :src="imgUrl[index]"
                  fluid
                ></b-img>
                <br />
                <div>
                  {{ gato.nombre }}
                </div>
                <div>{{ gato.edad }} meses</div>
                <div>
                  {{ gato.albergue || 'albergue' }}
                </div>
              </b-col>
            </b-row>
          </v-list-item>
        </v-card>
      </b-row>
    </b-col>
  </b-row>
</template>

<script>
  export default {
    auth: false,
    async fetch() {
      const url = '/get_gatos'
      await this.$axios.$get(url).then((res) => {
        /* eslint-disable */
        console.log(res)
        this.data = res.gatos
      })
    },
    data() {
      return {
        data: [],
        searchVideo: '',
      }
    },
    computed: {
      handleSearch() {
        return this.data.filter((gato) => {
          /* eslint-disable */
          console.log(gato)
          return (
            (gato.adopcion && gato.nombre.includes(this.searchVideo)) ||
            gato.edad == this.searchVideo ||
            gato.albergue.includes(this.searchVideo)
          )
        })
      },
      imgUrl() {
        /* eslint-disable */
        // console.log(index)
        return this.data.map((gato) => {
          console.log(gato.img.replace('home/ubuntu', '/52.67.175.153'))
          return gato.img.replace('home/ubuntu', '/52.67.175.153')
        })
      },
    },
  }
</script>
