<template>
  <div>
    <ul class="card-list">
      <li v-for="schedule in schedules" :key="schedule.title">
        <ScheduleCard v-bind="{...schedule}" />
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
const {params} = useRoute()
const schedules = [
  { title: 'Casamento', time: '18h30' },
  { title: 'Meditação', time: '19h45' },
  { title: 'Prova de certificação', time: '13h00' },
  { title: 'Hora de dormir', time: '01h30' },
]
</script>

<style>

</style>