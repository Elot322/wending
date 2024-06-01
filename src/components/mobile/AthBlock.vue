<template>
  <div
    :class="$style['container']">
    <div>
      <img
        src="/mobile/Mask group.png"/>
    </div>
    <p
      :class="$style['margin-bottom']">Мы будем рады Вам в любом случае)</p>
    <div
      :class="$style['margin-bottom']">
      <p>НО можно сделать нас ещё счастливее: прийти</p>
      <p>в соответствии с дресс-кодом мероприятия!</p>
    </div>
    <div
      :class="[$style['margin-bottom'], $style['with-image']]">
      <p>Смелые девушки, наряжайтесь</p>
      <p>в нестандартные образы, подбирайте</p>
      <p>аксессуары или интересные детали,</p>
      <p>бахните крутой мейк</p>
    </div>
    <div
      :class="$style['margin-bottom']">
      <p>Дамы поскромнее, выбирайте любой</p>
      <p>сдержанный образ в соответствии</p>
      <p>с нашим цветовым решением</p>
    </div>
    <div
      :class="$style['margin-bottom']">
      <p>Присмотритесь к длине макси/миди,</p>
      <p>атласным и бархатным тканям...</p>
    </div>
    <div
      :class="$style['margin-bottom']">
      <p>Избегайте белых и супер цветных</p>
      <p>оттенков</p>
    </div>
    <div>
      <img
        src="/mobile/Group 27.png"/>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" module>
.container {
  display: flex;
  flex-direction: column;
  padding-left: 40px;
  font-family: 'Gilroy';
  font-size: 16px;
  color: $white;
  font-weight: 300;

  .margin-bottom {
    margin-bottom: 30px;
  }

  .with-image {
    &::after {
      position: absolute;
      top: 220px;
      left: 330px;
      width: 64px;
      height: 91px;
      content: url('/mobile/aaaggg.png')
    }
  }
}
</style>
