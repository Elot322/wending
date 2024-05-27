<template>
  <div
    :class="{
      [$style['container-pc']]: !isMobile,
      [$style['container-mobile']]: isMobile,
    }">
    <div
      :class="$style['title']">
      ДРЕСС-КОД
    </div>
    <div>
      <img
        :src="`/${link}/seven_block_lady_pc.png`"/>
    </div>
    <div>
      <img
        :src="`/${link}/seven_block_boys_pc.png`"/>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
const props = defineProps(['isMobile'])

const link = computed(()=> {
  if (props.isMobile === true) {
    return 'mobile'
  } else {
    return 'pc'
  }
})
</script>

<style lang="scss" module>
.container-pc {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: $white;

  .title {
    font-family: 'dance';
    font-size: 111px;
  }

  .lady {
    display: flex;
    
    .lady-colors {
      margin-top: 200px;
      margin-right: 250px;

      .lady-text {
        font-family: 'Gilroy';
        font-size: 30px;
        width: 402px;
        transform: rotate(-8.91deg);
      }

      .lady-color-list {
        margin-top: 20px;
        margin-left: 310px;
        position: relative;

        &::before {
          top: 100px;
          left: -200px;
          position: absolute;
          content: url('/серебро.png');
        }

        &::after {
          top: 100px;
          left: 150px;
          position: absolute;
          content: url('/бордо.png');
        }
      }

    }
    .lady-title {
      transform: rotate(9deg);
      font-family: 'Denistina';
      font-size: 200px;
    }
  }
}

.container-mobile {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: $white;

  .title {
    font-family: 'dance';
    font-size: 50px;
  }

  .lady {
    display: flex;
    
    .lady-colors {
      margin-top: 200px;
      margin-right: 250px;

      .lady-text {
        font-family: 'Gilroy';
        font-size: 30px;
        width: 402px;
        transform: rotate(-8.91deg);
      }

      .lady-color-list {
        margin-top: 20px;
        margin-left: 310px;
        position: relative;

        &::before {
          top: 100px;
          left: -200px;
          position: absolute;
          content: url('/серебро.png');
        }

        &::after {
          top: 100px;
          left: 150px;
          position: absolute;
          content: url('/бордо.png');
        }
      }

    }
    .lady-title {
      transform: rotate(9deg);
      font-family: 'Denistina';
      font-size: 200px;
    }
  }
}
</style>