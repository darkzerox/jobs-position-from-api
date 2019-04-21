<template>
  <div class="jobs-list">
    <v-expansion-panel>
      <v-expansion-panel-content v-for="job in listdata" :key="job.id" class="job-item">
        <template v-slot:header>
          <div>
            <h2>{{ job.title}}</h2>
          </div>
        </template>
        <v-card>
          <!-- <v-img src="https://cdn.vuetifyjs.com/images/cards/desert.jpg" aspect-ratio="2.75"></v-img> -->

          <v-card-title primary-title>
            <div class="job-description">
              <!-- <h3 class="headline mb-0">{{ job.title}}</h3> -->
              <div v-html="job.description"></div>
            </div>
          </v-card-title>
          <v-layout align-center justify-center row fill-height>
            <v-card-actions class="job-aply-btn">
              <v-btn color="info" :href="job.applyUrl">Apply Now</v-btn>
            </v-card-actions>
          </v-layout>
        </v-card>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listdata: []
    };
  },
  methods: {
    get_api_data: function() {
      const baseURI = process.env.VUE_APP_URL;
      this.$http.get(baseURI).then(result => {
        this.listdata = result.data.positions;
      });
    }
  },
  created() {
    this.get_api_data();
  }
};
</script>

<style lang="scss" scoped>
.job-description {
  padding: 0 30px;
}
.job-aply-btn {
  padding-bottom: 30px;
}
</style>
  