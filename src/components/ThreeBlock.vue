<template>
  <div
    :class="{
      [$style['container-pc']]: !isMobile,
      [$style['container-mobile']]: isMobile
    }">
    <div
      :class="$style['month']">Август</div>
    <div
      :class="$style['calendar']">
      <img
        src="/календарь.png"/>
    </div>
  </div>
</template>

<script setup>
defineProps(['isMobile'])

</script>

<style lang="scss" module>
.container-pc {
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;

  .month {
    position: relative;
    font-family: 'dance';
    font-size: 111px;
    color: $white;
    margin-bottom: 142px;

    &::after {
      content: url('шар.png');
      position: absolute;
      left: 300px;
      top: -80px;
    }

    &::before {
      content: '2024';
      position: absolute;
      font-family: 'Denistina';
      font-size: 200px;
      top: 20px;
      right: 200px;
      transform: rotate(18deg);
    }
  }

  .calendar {
    position: relative;

    &::before {
      position: absolute;
      content: url('/love.png');
      left: -120px;
      top: -20px;
    }

    &::after {
      position: absolute;
      content: url('/поцелуй.png');
      top: 170px;
      left: 690px;
      animation: fadeInScale 2s infinite;
    }

    @keyframes fadeInScale {
      from {
        opacity: 0; /* Начальное состояние: объект невидимый */
        transform: scale(2); /* Уменьшенный размер */
      }
      to {
        opacity: 1; /* Конечное состояние: объект видимый */
        transform: scale(1); /* Исходный размер */
      }
    }
  }
}

.container-mobile {
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;

  .month {
    position: relative;
    font-family: 'dance';
    font-size: 50px;
    color: $white;
    margin-bottom: 59px;

    &::after {
      content: url('/mobile/шар.png');
      position: absolute;
      left: 115px;
      top: 25px;
    }

    &::before {
      content: '2024';
      position: absolute;
      font-family: 'Denistina';
      font-size: 50px;
      top: 30px;
      right: 100px;
      transform: rotate(18deg);
    }
  }

  .calendar {
    position: relative;
    img {
      width: 365px;
      height: 193px;
    }

    &::before {
      position: absolute;
      content: url('/mobile/love.png');
      left: 0px;
      top: 0px;
    }

    &::after {
      position: absolute;
      content: url('/mobile/поцелуй (1).png');
      top: 85px;
      left: 279px;
      animation: fadeInScale 2s infinite;
    }

    @keyframes fadeInScale {
      from {
        opacity: 0; /* Начальное состояние: объект невидимый */
        transform: scale(2); /* Уменьшенный размер */
      }
      to {
        opacity: 1; /* Конечное состояние: объект видимый */
        transform: scale(1); /* Исходный размер */
      }
    }
  }
}
</style>
