<template>
  <div
    :class="$style['container-pc']">
    <div
      :class="$style['text']">До встречи осталось</div>
    <div
      :class="$style['date-container']">
      <div
        :class="$style['item']">
        <div
          :class="$style['number']">
          {{ days }}
        </div>
        <div
          :class="$style['description']">
          {{ descriptionDays }}
        </div>
      </div>
      <div
        :class="$style['item']">
        <div
          :class="$style['number']">
          {{ hours }}:
        </div>
        <div
          :class="$style['description']">
          {{ descriptionHours }}
        </div>
      </div>
      <div
        :class="$style['item']">
        <div
          :class="$style['number']">
          {{ minutes }}:
        </div>
        <div
          :class="$style['description']">
          {{ descriptionMinutes }}
        </div>
      </div>
      <div
        :class="$style['item']">
        <div
          :class="$style['number']">
          {{ seconds }}
        </div>
        <div
          :class="$style['description']">
          {{ descriptionSeconds }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from "vue";

onMounted(() => {
  updateDate()
  setInterval(updateDate, 1000)
})

const targetDate = ref(new Date('2024-08-18T15:30:00'))
const days = ref('00')
const hours = ref('00')
const minutes = ref('00')
const seconds = ref('00')

function updateDate() {
  const currentTime = new Date()
  const timeDifference = targetDate.value.getTime() - currentTime.getTime()

  const rawDays = Math.floor(timeDifference / (1000 * 60 * 60 * 24))
  const rawHours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
  const rawMinutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60))
  const rawSeconds = Math.floor((timeDifference % (1000 * 60)) / 1000)

  days.value = getNumber(rawDays)
  hours.value = getNumber(rawHours)
  minutes.value = getNumber(rawMinutes)
  seconds.value = getNumber(rawSeconds)


}

function getNumber(number) {
  if (number < 10) {
    return `0${number}`
  }

  return `${number}`
}

function getNoun(number, one, two, five) {
  let n = Math.abs(number);
  n %= 100;
  if (n >= 5 && n <= 20) {
    return five;
  }
  n %= 10;
  if (n === 1) {
    return one;
  }
  if (n >= 2 && n <= 4) {
    return two;
  }
  return five;
}

const descriptionDays = computed(() => getNoun(days.value, 'день', 'дня', 'дней'))

const descriptionHours = computed(() => getNoun(hours.value, 'час', 'часа', 'часов'))

const descriptionMinutes = computed(() => getNoun(minutes.value, 'минута', 'минуты', 'минут'))

const descriptionSeconds = computed(() => getNoun(seconds.value, 'секунда', 'секунд', 'cекунд'))
</script>

<style lang="scss" module>
.container-pc {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: $white;

  .text {
    position: relative;
    font-family: 'Girloy';
    font-size: 60px;
    margin-bottom: 92px;

    &::before {
      position: absolute;
      content: url('/собака.png');
      top: -200px;
      left: -350px;
      transform: rotate(-3deg);
    }
  }

  .date-container {
    display: flex;

    .item {
      &:first-child {
        margin-right: 167px
      }
      
      .number {
        font-family: 'Gilroy';
        font-size: 184px;
      }

      .description {
        font-family: 'Gilroy';
        font-size: 48px;
      }
    }
  }
}

.container-mobile {

}
</style>