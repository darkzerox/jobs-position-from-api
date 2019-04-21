<template>
  <v-container>
    <div class="jobs_page">
      <h1 class="page-title">Jobs Position</h1>
      <Joblist/>
    </div>
  </v-container>
</template>



<script>
import Joblist from "../components/Joblist";

export default {
  components: {
    Joblist
  }
};
</script>

<style lang="scss" scoped>
.page-title {
  margin: 30px 0;
}
</style>

  