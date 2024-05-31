<template>
  <div
    :class="$style['container']">
    <div
      :class="$style['title']">ЛОКАЦИЯ</div>
    <div
      :class="$style['text']">
      <div
        :class="$style['location']">GreenPark</div>
      <div
        :class="$style['address']">
        <p>г. Калуга</p>
        <p>ул. Резванская, д.4</p>
      </div>
    </div>
    <div>
      <img
        src="/mobile/карта.png"/>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" module>
.container {
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  .title {
    font-family: "dance";
    font-size: 50px;
    margin-bottom: 45px;
  }

  .text {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    width: 100%;
    margin-bottom: 24px;
    padding-right: 40px;
    .location {
      font-family: "Dela Gothic One";
      font-size: 30px;
      position: relative;
      &::before {
        position: absolute;
        top: -30px;
        left: -150px;
        content: url('/mobile/актер.png');
      }
      margin-bottom: 36px;
    }

    .address {
      font-family: "Gilroy";
      font-size: 20px;
    }
  }
}
</style>
