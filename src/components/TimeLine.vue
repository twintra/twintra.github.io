<template>
  <div class="my-3">
    <TimeLineItem v-for="(item, index) in timeline" :key="index" :on-right="index % 2 == 0">
      <template #icon>
        {{ item.month }}
      </template>
      <template #heading>{{ item.title }}</template>

      {{ item.description }}
    </TimeLineItem>
  </div>
  
</template>
<script lang="ts">
import TimeLineItem from './TimeLineItem.vue'
export default {
  components: { TimeLineItem },
  data() {
    return {
      timeline: [
        {
          title: "title",
          description: "description",
          year: 2022,
          month: 6,
        },
        {
          title: "title",
          description: "description",
          year: 2022,
          month: 7,
        },
        {
          title: "title",
          description: "description",
          year: 2022,
          month: 9,
        },
        {
          title: "title",
          description: "description",
          year: 2022,
          month: 9,
        },
      ],
    }
  }
}
</script>
<style></style>