<template>
  <div
    class="page-container">
      <!-- <div class="page-container__gradient-first"></div>
      <div class="page-container__gradient-two"></div> -->
      <div 
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1171"
          height="916"
          src='/pc/first_block_pc.png'/>
      </div>
      <div 
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1171"
          height="916"
          src='/pc/two_block_pc.png'/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <ThreeBlock/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <FourBlock/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1467"
          height="858"
          src='/pc/five_block_pc.png'/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1318"
          height="786"
          src='/pc/six_block_pc.png'/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <SevenBlock/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1262.07"
          height="980"
          src='/pc/8 блок послание.png'/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          width="1262.07"
          height="837"
          src='/pc/9 блок смс.png'/>
      </div>
      <div>
        <GuestForm/>
      </div>
      <div>
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
import { ref } from 'vue'
import FourBlock from './components/FourBlock.vue'
import GuestForm from './components/GuestForm.vue'
import SevenBlock from './components/SevenBlock.vue'
import ThreeBlock from './components/ThreeBlock.vue'

const video = ref()
const endVideoFlag = ref(false)

function onRunVideoClick() {
  video.value.play()
}
</script>

<style scoped lang="scss">
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;
  gap: 150px;
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
