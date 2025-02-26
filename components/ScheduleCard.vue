<template>
    <div class="card">
      <span>{{props.title}}</span> <span>{{props.time}}</span>
    </div>
</template>

<script lang="ts" setup>
type Props = {
  title: string
  time: string
}
const props = defineProps<Props>()
</script>

<style>

</style>