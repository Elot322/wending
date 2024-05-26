<template>
  <div
    :class="$style['container-pc']">
    <div
      :class="$style['title']">АНКЕТА ГОСТЯ</div>
    <div>
      <div :class="$style['input-container']">
        <div :class="$style['text']">Ваше Имя и Фамилию</div>
        <input type="text" id="input">
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">Подтвердите присутствие</div>
        <div
          :class="$style['radio']">
          <input type="radio" id="one" value="One" v-model="picked" />
          <div :class="$style['radio-label']">Обязательно буду</div>
        </div>
        <div
          :class="$style['radio']">
          <input type="radio" id="two" value="Two" v-model="picked" />
          <div :class="$style['radio-label']">Не смогу прийти</div>
        </div>
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">С кем Вы пойдете на праздник?</div>
        <input type="text" id="input"/>
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">Уточните Ваши предпочтения в алкоголе:</div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Вино красное</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Вино белое</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Шампанское</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Водка</div>
        </div>
                <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Виски</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Коньяк</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Джин</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Без разницы</div>
        </div>
                <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Я не пью</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input"/>
          <div :class="$style['checkbox-label']">Напишу лично(другие предпочтения)</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const picked = ref()

</script>

<style lang="scss" module>
.container-pc {
  margin-bottom: 30px;
  color: $white;
  .title {
    text-align: center;
    font-family: 'dance';
    font-size: 111px;
    margin-bottom: 168px
  }
  input[type="text"] {
    border: none;
    color: white;
    border-bottom: 2px solid white; /* Цвет и толщина полоски */
    outline: none; /* Убираем обводку при фокусе */
    background: transparent; /* Прозрачный фон */
    width: 900px;
    font-family: 'Gilroy';
    font-size: 30px
  }
  input[type="radio"] {
    width: 50px;
    height: 50px;
    accent-color: #232323;
  }
  input[type="checkbox"] {
    width: 50px;
    height: 50px;
    accent-color: #232323;
  }
  .input-container {
    .text {
      text-align: start;
      font-family: 'Gilroy';
      font-size: 42px;
      margin-bottom: 5px;
    }
    .radio {
      display: flex;
      align-items: center;
      .radio-label {
        margin-left: 5px;
        font-family: 'Gilroy';
        font-size: 42px;
        cursor: pointer;
      }
    }
    .checkbox {
      display: flex;
      align-items: center;
      .checkbox-label {
        margin-left: 5px;
        font-family: 'Gilroy';
        font-size: 42px;
        cursor: pointer;
      }
    }
  }
  .margin-top {
    margin-top: 99px;
  }
}
</style>