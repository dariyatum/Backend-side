
<template>
  <div class="container">
    <div v-for="job in jobs" :key="job.id">
      <h3>{{ job.title }}</h3>
      <h1>{{ job.full-time }}</h1>
      <h3></h3>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
const jobs = ref([])

const config = {
  headers: {
    Authorization: `Bearer 8fa49b28ded25f40197dc0e90bd19093fc7fec0136849cdd1d5373c5375afbf18c0ef263890e3be53e71df916f4a0aefb511516142394cbed9b62d18dceae6df491e36902cfad9b2ad3c2dc60b76a41dd52a5f747c5d69ddcdea1d3932b079767ce18056ccf65fde4e9b3be3c53080b62bf32efbbfbfdf6ec4bf843b5b0b481e`
  }
}

const getJobPostings = async () => {
  try {
    const response = await axios.get(
      'http://localhost:1337/api/jobs',
      config
    )

    jobs.value = response.data.data
    console.log(jobs.value)

  } catch (error) {
    console.error(error)
  }
}

onMounted(() => {
  getJobPostings()
})
</script>
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

