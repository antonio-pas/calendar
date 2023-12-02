<template>
  <div>
    <p>There are {{ daysInMonth }} days in the month</p>
    <div class="grid">
      <div v-for="day in days" :class='{}'>
        {{ day.getDate() }}
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const date = useState('date', () => new Date(Date.now()))
const month = date.value.getMonth();
const year = date.value.getFullYear();

const daysInMonth = new Date(year, month+1, 0).getDate();
const start = new Date(year, month, 1).getDay();

const days: Date[] = [];
for (let i = -start; i < 7*6-start; i++) {
  const currentDate = new Date(year, month, i+1);
  days.push(currentDate);
}
</script>

<style>
.grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  width: fit-content;
  gap: 1rem;
}
</style>