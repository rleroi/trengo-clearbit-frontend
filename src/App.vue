<template>
  <div class="addon">
    <h3>Clearbit</h3>
    <div class="person">
      <div class="item">
        <div class="title">Name</div>
        <div class="value">{{state.person.fullName}}</div>
      </div>
      <div class="item">
        <div class="title">Email</div>
        <div class="value">{{state.person.email}}</div>
      </div>
      <div class="item">
        <div class="title">Location</div>
        <div class="value">{{state.person.location}}</div>
      </div>
      <div class="item">
        <div class="title">LinkedIn</div>
        <div class="value"><a href="{{state.person.linkedin}}" title="LinkedIn">{{state.person.linkedin}}</a></div>
      </div>
      <div class="item">
        <div class="title">Role</div>
        <div class="value">{{state.person.role}}</div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { onMounted, reactive } from 'vue';

const state = reactive({
  person: {},
  company: {},
})

onMounted(() => {
  state.person = {
    fullName: 'Ramses Leroi',
    email: 'r.leroi@live.nl',
    location: 'Utrecht, Netherlands',
    linkedin: 'https://linkedin.com/in/itbazen',
    role: 'Engineering',
  };
  state.company = {
    name: 'Trengo',
    domain: 'trengo.com',
    logo: 'https://logo.clearbit.com/trengo.com?size=100',
    description: 'Discover Trengo, the omnichannel communication platform that unifies all messaging channels into one single view. Make customer communicatio…',
    employees: '100',
  };
})
</script>
<style scoped>
  .item {
  }
  .title {
    font-weight: bold;
    font-size: .75rem;
  }
</style>
