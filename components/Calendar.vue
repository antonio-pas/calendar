<template>
  <div>
    <h1>Today is {{ date }}</h1>
    <p>There are {{ daysInMonth }}</p>
    <p>There are {{ preDays }} from Sunday until the start of the month</p>
  </div>
</template>

<script setup lang="ts">
const date = useState('date', () => new Date(Date.now()))
const daysInMonth = new Date(date.value.getFullYear(), date.value.getMonth(), 0).getDate();
const preDays = date.value.getDay();
</script>
