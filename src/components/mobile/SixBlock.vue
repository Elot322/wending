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
    <div
      :class="$style['map']">
      <div :class="$style['map']" style="position:relative;overflow:hidden;"><a href="https://yandex.ru/maps/6/kaluga/?utm_medium=mapframe&utm_source=maps" style="color:#eee;font-size:12px;position:absolute;top:0px;">Калуга</a><a href="https://yandex.ru/maps/6/kaluga/house/rezvanskaya_ulitsa_4/Z08YdwJnQUACQFtufXlyd3hlZA==/?ll=36.158145%2C54.536231&utm_medium=mapframe&utm_source=maps&z=19.07" style="color:#eee;font-size:12px;position:absolute;top:14px;">Резванская улица, 4 — Яндекс Карты</a><iframe src="https://yandex.ru/map-widget/v1/?ll=36.158145%2C54.536231&mode=search&ol=geo&ouri=ymapsbm1%3A%2F%2Fgeo%3Fdata%3DCgozMjkyMTExOTE3Ej7QoNC-0YHRgdC40Y8sINCa0LDQu9GD0LPQsCwg0KDQtdC30LLQsNC90YHQutCw0Y8g0YPQu9C40YbQsCwgNCIKDaWhEEIVVSVaQg%2C%2C&z=19.07" width="350" height="350" frameborder="1" allowfullscreen="true" style="position:relative;"></iframe></div>
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
        z-index: 100;
        content: url('/mobile/актер.png');
      }
      margin-bottom: 36px;
    }

    .address {
      font-family: "Gilroy";
      font-size: 20px;
    }
  }

  .map {
    border-radius: 20px;
  }
}
</style>
