<template>
  <div
    :class="$style['container']">
    <div
      :class="$style['header']">Helloy,</div>
    <div
      :class="$style['first']">
      <div>
        <img
          src="/mobile/фото (1).png">
      </div>
      <div
        :class="$style['text']">
        <p>РОДНЫЕ</p>
        <p>И РОДНЫЕ</p>
        <p>ДРУЗЬЯ!</p>
      </div>
    </div>
    <div>
      <p>Приглашаем Вас на вечеринку</p>
      <p>в честь семилетия наших</p>
      <p>отношений</p>
    </div>
    <div
      :class="$style['last']">
      <div
        :class="$style['text']">
        <p>Надя будет</p>
        <p>в свадебном</p>
        <p>платье, не</p>
        <p>пугайтесь  ...</p>
      </div>
      <div>
        <img
          :style="{transform: 'rotate(5deg)'}"
          src="/mobile/фото.png"/>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" module>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: white;
  font-family: "Gilroy";
  font-size: 20px;
  .header {
    font-family: "Dela Gothic One";
    margin-left: 50px;
    font-size: 50px;
    transform: rotate(20deg);
  }
  .first {
    display: flex;
    align-items: center;
    margin-bottom: 17px;
    .text {
      margin-left: 5px;
      font-family: "Gilroy";
      font-size: 30px;
    }
  }
  .last {
    display: flex;
    align-items: center;
    .text {
      font-family: 'Denistina';
      margin-right: 5px;
      font-size: 30px;
      transform: rotate(-13deg);
    }
  }
}
</style>