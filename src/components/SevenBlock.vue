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
      <div
        :class="$style['carusel']">
        <img
          v-for="i in 7"
          :key="i"
          width="172"
          height="259"
          :src="`/ladys/${i+1}.png`"/>
      </div>
    </div>
    <div
      :class="$style['next']">
      <img
        src="/mobile/стрелочка.png"/>
    </div>
    <div>
      <img
        :src="`/${link}/seven_block_boys_pc.png`"/>
    </div>
    <div
      :class="$style['carusel']">
      <img
        v-for="i in 4"
        :key="i"
        width="172"
        height="259"
        :src="`/boys/${i+1}.png`"/>
    </div>
    <div
      :class="$style['next']">
      <img
        src="/mobile/стрелочка.png"/>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue'
const props = defineProps(['isMobile'])

const link = computed(()=> {
  if (props.isMobile === true) {
    return 'mobile'
  } else {
    return 'pc'
  }
})

// carousel settings
    const settings = ref({
      itemsToShow: 1,
      snapAlign: 'center',
    })
    // breakpoints are mobile first
    // any settings not specified will fallback to the carousel settings
    const breakpoints = {
      // 700px and up
      700: {
        itemsToShow: 3.5,
        snapAlign: 'center',
      },
      // 1024 and up
      1024: {
        itemsToShow: 5,
        snapAlign: 'start',
      },
    }
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

  .carusel {
    display: flex;
    overflow-x: auto; 
    width: 330px
  }

  .next {
    display: flex;
    width: 330px;
    justify-content: end;
  }

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