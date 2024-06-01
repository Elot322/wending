<template>
  <div
    :class="$style['video-container']"
    v-if="!endVideoFlag && isMobile">
    <video
      muted
      playsinline
      autobuffer 
      preload="metadata"
      class="video" 
      ref="video"
      src="/opening.mp4#t=0.79"
      @ended="onEnded">
    </video>
    <div 
      v-if="showAnim"
      :class="$style['tap-me']"
      @click="onRunVideoClick">
      <img
        src='/mobile/tap-tap.gif'
      />
      <div
        :class="$style['text']">
        Жмяк сюда
      </div>
    </div>
  </div>
  <div
    v-if="endVideoFlag || !isMobile"
    :class="$style['page-container']">
      <div :class="$style['page-container__gradient-first']"></div>
      <div :class="$style['page-container__gradient-two']"></div>
      <div 
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1', 'margin-top': isMobile ? '80px': '0px'}"
          :width="link === 'mobile' ? 365 : 1171"
          :height="link === 'mobile' ? 542.55 : 916"
          :src='`/${link}/first_block_pc.png`'/>
      </div>
      <div 
        v-motion-slide-visible-once-right>
        <TwoBlock
          :style="{'z-index': '1'}"
          v-if="isMobile"/>
        <img
          v-else
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
        <FiveBlock
          v-if="isMobile"/>
        <img
          v-else
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? screenWidth : 1467"
          :height="link === 'mobile' ? 616 : 858"
          :src="`/${link}/five_block_pc.png`"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <SixBlock
          v-if="isMobile"/>
        <img
          v-else
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
        :style="{'z-index': '1'}"
        v-motion-slide-visible-once-right>
        <AthBlock
          v-if="isMobile"/>
        <img
          v-else
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? screenWidth-10 : 1262.07"
          :height="link === 'mobile' ? 681 : 980"
          :src="`/${link}/8 блок послание.png`"/>
      </div>
      <div
        v-motion-slide-visible-once-right>
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? screenWidth : 1262.07"
          :height="link === 'mobile' ? 793.2 : 837"
          :src="`/${link}/9 блок смс.png`"/>
      </div>
      <div
        :style="{'z-index': '1'}">
        <GuestForm
          :isMobile="isMobile"/>
      </div>
      <div
        :style="{'z-index': '1'}">
        <img
          :style="{'z-index': '1'}"
          :width="link === 'mobile' ? screenWidth : 1262.07"
          :height="link === 'mobile' ? 319 : 837"
          :src="`/${link}/11 блок конец.png`"/>
      </div>
  </div>
</template>

<script setup>
import { computed, onMounted, ref, onBeforeMount} from 'vue'
import FourBlock from './components/FourBlock.vue'
import GuestForm from './components/GuestForm.vue'
import SevenBlock from './components/SevenBlock.vue'
import FiveBlock from './components/mobile/FiveBlock.vue'
import ThreeBlock from './components/ThreeBlock.vue'
import TwoBlock from './components/mobile/TwoBlock.vue'
import SixBlock from './components/mobile/SixBlock.vue'
import AthBlock from './components/mobile/AthBlock.vue'

const video = ref()
const endVideoFlag = ref(false)
const showAnim = ref(true)

function onRunVideoClick() {
  showAnim.value = false
  video.value.play()
}

const screenWidth = ref(screen.width)

function onEnded() {
  var video = document.querySelector('.video');
  video.classList.add('anim-fade-out');
  setTimeout(() => {
    endVideoFlag.value = true
  }, 100)
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
})
</script>

<style module lang="scss">

.video-container {
  position: relative;
  video {
    width: 100%;
    height: 100%;
  }

  .tap-me {
    position: absolute;
    top: 10%;
    left: 10%;
  }

  .text {
    font-family: 'dance';
    font-size: 30px;
    color: white;
    font-weight: bold;
  }
}

.anim-fade-out {
  animation: fade-out 1s forwards;
}

@keyframes fade-out {
  to {
    opacity: 0;
  }
}
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;
  gap: 50px;
  position: relative;
  background-color: $background_color;
  overflow-x: hidden;

  // &::before {
  //   position: absolute;
  //   width: 500px;
  //   height: 500px;
  //   left: 1250px;
  //   top: 1000px;
  //   background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
  //   filter: blur(56.75px);
  // }

  &__gradient-first {
    position: fixed;
    width: 1157px;
    height: 1025px;
    left: -500px;
    top: -500px;
    background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
    filter: blur(56.75px);

     @media screen and (max-width: 480px) {
      left: -700px;
      top: -700px;
    }
  }

  &__gradient-two {
    position: fixed;
    width: 1157px;
    height: 1025px;
    left: 600px;
    top: 300px;
    background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
    filter: blur(56.75px);

    @media screen and (max-width: 480px) {
      left: 50px;
      top: 150px;
    }
  }

  // &__gradient-two {
  //   position: fixed;
  //   width: 1157px;
  //   height: 1025px;

  //   background: radial-gradient(50% 50% at 50% 50%, rgba(242, 9, 16, 0.79) 0%, rgba(242, 9, 16, 0) 100%);
  //   filter: blur(56.75px);

  //   @media screen and (max-width: 480px) {
  //     left: -250px;
  //     top: -300px;
  //   }
  // }
}
</style>
