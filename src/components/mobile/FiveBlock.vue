<template>
  <div
    :class="$style['container']">
    <div
      :class="$style['header']">ТАЙМИНГ</div>
    <div
      :class="$style['timing']">
      <div
        v-for="(item, index) in timing"
        :key="index"
        :class="$style['timing-item']">
        <div
          :class="$style['image']">
          <img
            :src="item.image"/>
        </div>
        <div
          :class="$style['time']">
          {{ item.time }}
        </div>
        <div
          :class="$style['description']">
          {{ item.description }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"

const timing = ref([
  {
    image: '/mobile/бокалы.png',
    time: '15:30',
    description: 'Сбор гостей и фуршет',
  },
  {
    image: '/mobile/церемония.png',
    time: '16:00',
    description: 'Церемония',
  },
  {
    image: '/mobile/фуршет.png',
    time: '17:00',
    description: 'Торжественный ужин',
  },
  {
    image: '/mobile/салют.png',
    time: '23:00',
    description: 'Завершение вечера',
  },
])
</script>

<style lang="scss" module>
.container {
  color: white;
  .header {
    text-align: center;
    font-family: 'dance';
    font-size: 50px;
  }
  .timing {
    display: flex;
    flex-direction: column;
  }
  .timing-item {
    display: flex;
    align-items: center;
    font-family: 'Gilroy';
    gap: 10px;

    .image {
      width: 86.86px;
      height: 95px;
    }

    .time {
      font-size: 20px;
    }

    .description {
      text-align: left;
      font-size: 20px;
      max-width: 140px;
      min-width: 140px;
    }
  }
}
</style>
