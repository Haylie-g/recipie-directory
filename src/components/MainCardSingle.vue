<script setup>
import { faker } from '@faker-js/faker'
const firstname = faker.person.firstName()
const lastname = faker.person.lastName()
const fullname = faker.person.fullName({ firstname: firstname, lastname: lastname })
const job_title = faker.person.jobTitle()
const bio = faker.lorem.lines(2)
const username = faker.internet.userName({ firstname: firstname, lastname: lastname }).toLowerCase()
</script>

<template>
  <!-- {{ fullname }}<br /> -->
    
    <RouterLink :to="{name: 'CardDetails', params: {id: username}}">
     <div class="border border-pink-400 rounded-lg shadow-lg bg-pink-200 h-full overflow-hidden">
      <img :src="faker.image.urlLoremFlickr({ width: 640, height: 480, category: 'desserts'})" class ="rounded-t-xl"/>
     <div class="p-4">
        <p class="mb-2 text-2xl font-bold text-pink-800">{{ fullname }}</p>
        <p class="mb-3 font-normal text-pink-600">{{ job_title }}</p>
        <p class="mb-3 font-normal text-pink-600">{{ bio }}</p>
      </div>
    </div>
</RouterLink>
</template>