<template>
  <div
    class="page-container">
      <!-- <div class="page-container__gradient-first"></div>
      <div class="page-container__gradient-two"></div> -->
      <div 
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 365 : 1171"
          :height="link === 'mobile' ? 542.55 : 916"
          :src='`/${link}/first_block_pc.png`'/>
      </div>
      <div 
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 365 : 1171"
          :height="link === 'mobile' ? 578.55 : 916"
          :src='`/${link}/two_block_pc.png`'/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <ThreeBlock
          :isMobile="isMobile"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <FourBlock
          :isMobile="isMobile"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 365 : 1467"
          :height="link === 'mobile' ? 616 : 858"
          :src="`/${link}/five_block_pc.png`"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 352 : 1318"
          :height="link === 'mobile' ? 605 : 786"
          :src="`/${link}/six_block_pc.png`"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <SevenBlock
          :isMobile="isMobile"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 345 : 1262.07"
          :height="link === 'mobile' ? 681 : 980"
          :src="`/${link}/8 блок послание.png`"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? 320 : 1262.07"
          :height="link === 'mobile' ? 793.2 : 837"
          :src="`/${link}/9 блок смс.png`"/>
      </div>
      <div
        v-if="!isMobile">
        <GuestForm/>
      </div>
      <div
        v-if="!isMobile">
        <img
          :style="{'z-index': '1'}"
          width="1262.07"
          height="837"
          src='/pc/11 блок конец.png'/>
      </div>
      <!-- <video
        v-if="!endVideoFlag"
        ref="video"
        src="/opening.mp4"
        @ended="endVideoFlag = true"
        @click="onRunVideoClick">
      </video> -->
      <!-- <div
        v-if="endVideoFlag">
        <div 
          v-motion-slide-visible-once-right>
          <HelloBlock/>
        </div>
        <div
          v-motion-slide-visible-once-right>
          <WelcomeBlock/>
        </div>
      </div> -->
  </div>
</template>

<script setup>
import { computed, onMounted, ref, onBeforeMount} from 'vue'
import FourBlock from './components/FourBlock.vue'
import GuestForm from './components/GuestForm.vue'
import SevenBlock from './components/SevenBlock.vue'
import ThreeBlock from './components/ThreeBlock.vue'

const video = ref()
const endVideoFlag = ref(false)

function onRunVideoClick() {
  video.value.play()
}

const isMobile = ref(false)

const link = computed(()=> {
  if (isMobile.value === true) {
    return 'mobile'
  } else {
    return 'pc'
  }
})

onBeforeMount(() => {
  if (screen.width <= 760) {
    isMobile.value = true
  }
  console.log(isMobile)
})
</script>

<style scoped lang="scss">
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;
  gap: 50px;
  background-color: $background_color;

  &__gradient-first {
    position: fixed;
    width: 1157px;
    height: 1025px;
    left: 341px;
    top: -433px;
    z-index: 0;

    background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
    filter: blur(56.75px);

    @media screen and (max-width: 480px) {
      left: 55px;
      top: 438px;
    }
  }

  &__gradient-two {
    position: fixed;
    width: 1157px;
    height: 1025px;
    left: 1000px;
    top: 500px;
    z-index: 0;

    background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
    filter: blur(56.75px);

    @media screen and (max-width: 480px) {
      left: 55px;
      top: 438px;
    }
  }

  video {
    z-index: 200;
    width: 100%;
    height: 100%;
  }
}
</style>
