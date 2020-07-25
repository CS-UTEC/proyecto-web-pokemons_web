<template>
  <b-row align-h="center" class="mt-0 pl-3">
    <b-col md="3" class="colorDarken">
      <v-row justify="center" align="center" class="maxHeight">
        <v-text-field
          v-model="searchVideo"
          solo
          clearable
          append-icon="mdi-magnify"
          @click:append="handleSearch"
          @click:clear="onSubmit"
        ></v-text-field>
      </v-row>
    </b-col>
    <b-col md="9" class="maxHeight">
      <b-row align-v="start">
        <v-card
          v-for="albergue in data"
          :key="albergue.nombre"
          outlined
          class="albergue t-helvetica"
        >
          <v-list-item>
            <b-row>
              <b-col>
                <div>
                  {{ albergue.nombre_albergue }}
                </div>
                <div>Albergue de {{ albergue.albergan }}</div>
                <b-row align-v="center">
                  <b-col>
                    {{ albergue.ciudad }}
                  </b-col>
                  <b-col> Desde {{ 2020 - albergue.anios }} </b-col>
                  <b-col> {{ albergue.num_gatos }} rescatados </b-col>
                </b-row>
              </b-col>
              <b-col>
                <div>
                  {{ albergue.nombre }}
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
      const url = '/get_albergues'
      await this.$axios.$get(url).then((res) => {
        /* eslint-disable */
        console.log(res)
        this.data = res
      })
    },
    data() {
      return {
        data: null,
        searchVideo: '',
      }
    },
    methods: {
      handleSearch() {},
      onSubmit() {},
    },
  }
</script>
