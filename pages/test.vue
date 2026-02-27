<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const config = {
  headers: {
    Authorization: 'Bearer b9d0a50fb8e867c645322b9ac08477d172d12652c5f8c5e169cd2e340f74427720dfa51236f73d60b7c3fabf88463066dfdc9c48f304529570dfeeefe458dad5ee9ea23a4ca4694a3029c4d64bc29bd2dc096e9b2c366aa54c69f1cb659edcddb172f56bd3300b2e99bc90dba40e8159bf7331fd4deb9053443e7cd462e2af11'
  }
}
const dataFetch = await axios.get('http://localhost:1337/api/job-postings',config);
const jobPostingDatas = dataFetch.data.data;

console.log(jobPostingDatas);

</script>

<template>
  <div>
    <h1>Job Postings</h1>
    <div v-for="data in jobPostingDatas">
      {{ data.jobTitle }}
    </div>
  </div>
</template>