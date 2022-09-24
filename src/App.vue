<template>
  <div>
    <div class="item">
      <div class="title">Name</div>
      <div class="value">{{state.data.fullName}}</div>
    </div>
    <div class="item">
      <div class="title">Company</div>
      <div class="value">{{state.data.companyName}}</div>
    </div>
    <div class="item">
      <div class="title">Location</div>
      <div class="value">{{state.data.location}}</div>
    </div>
    <div class="item">
      <div class="title">LinkedIn</div>
      <div class="value"><a :href="state.data.linkedin" target="_blank" title="LinkedIn">{{state.data.linkedin}}</a></div>
    </div>
    <div class="item">
      <div class="title">Role</div>
      <div class="value">{{state.data.role}}</div>
    </div>
  </div>
</template>
<script setup>
import { onMounted, reactive } from 'vue';

const state = reactive({
  data: {},
})

onMounted(async () => {
  const res = await fetch(`https://trengo-clearbit.itbazen.workers.dev/${document.location.search}`);
  state.data = await res.json();
})
</script>
<style scoped>
  .title {
    font-weight: bold;
    font-size: .75rem;
  }
  .value {
    color: rgb(112, 118, 123);
  }
</style>
