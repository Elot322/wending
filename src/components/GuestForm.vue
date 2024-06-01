<template>
  <div
    :class="{
      [$style['container-pc']]: !isMobile,
      [$style['container-mobile']]: isMobile
    }">
    <div
      :class="$style['title']">АНКЕТА ГОСТЯ</div>
    <div>
      <div :class="$style['input-container']">
        <div :class="$style['text']">Ваше Имя и Фамилия</div>
        <input 
          type="text" 
          id="input"
          v-model="fio">
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">Подтвердите присутствие до 1 августа</div>
        <div
          :class="$style['radio']">
          <input type="radio" id="one" value="Обязательно буду" v-model="iam" />
          <div :class="$style['radio-label']">Обязательно буду</div>
        </div>
        <div
          :class="$style['radio']">
          <input type="radio" id="two" value="Не смогу прийти" v-model="iam" />
          <div :class="$style['radio-label']">Не смогу прийти</div>
        </div>
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">С кем Вы пойдете на праздник?</div>
        <input 
          type="text" 
          id="input"
          v-model="iamwith"/>
      </div>
    </div>
    <div
      :class="$style['margin-top']">
      <div :class="$style['input-container']">
        <div :class="$style['text']">Уточните Ваши предпочтения в алкоголе:</div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="vineRed"/>
          <div :class="$style['checkbox-label']">Вино красное</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="vineWhite"/>
          <div :class="$style['checkbox-label']">Вино белое</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="shampain"/>
          <div :class="$style['checkbox-label']">Шампанское</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="vodka"/>
          <div :class="$style['checkbox-label']">Водка</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="viski"/>
          <div :class="$style['checkbox-label']">Виски</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="konyak"/>
          <div :class="$style['checkbox-label']">Коньяк</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="gin"/>
          <div :class="$style['checkbox-label']">Джин</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="iDontKnow"/>
          <div :class="$style['checkbox-label']">Без разницы</div>
        </div>
          <div
            :class="$style['checkbox']">
            <input type="checkbox" id="input" v-model="iDontDrink"/>
          <div :class="$style['checkbox-label']">Я не пью</div>
        </div>
        <div
          :class="$style['checkbox']">
          <input type="checkbox" id="input" v-model="say"/>
          <div :class="$style['checkbox-label']">Напишу лично(другие предпочтения)</div>
        </div>
        <button
          :class="$style['button']"
          :disabled="disabled"
          @click="onButtonClick">{{buttonText}}</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue'

defineProps(['isMobile'])

const buttonText = ref('Отправить')
const disabled = ref(false)

const fio = ref('')
const iam = ref()
const iamwith = ref('')

const vineRed = ref(false)
const vineWhite = ref(false)
const shampain = ref(false)
const vodka = ref(false)
const viski = ref(false)
const konyak = ref(false)
const gin = ref(false)
const iDontKnow = ref(false)
const iDontDrink = ref(false)
const say = ref(false)


const alco = computed(() => {
  const result = []

  if (vineRed.value) {
    result.push('Вино красное')
  }

  if (vineWhite.value) {
    result.push('Вино белое')
  }

  if (shampain.value) {
    result.push('Шампанское')
  }

  if (vodka.value) {
    result.push('Водка')
  }

  if (viski.value) {
    result.push('Виски')
  }
  
  if (konyak.value) {
    result.push('Виски')
  }

  if (gin.value) {
    result.push('Джин')
  }

  if ( iDontKnow.value ) {
    result.push('Без разницы')
  }

  if ( iDontDrink.value ) {
    result.push('Я не пью')
  }

  if ( say.value ) {
    return ('Напишу лично')
  }

  return result
})

function onButtonClick() {

  try {
    disabled.value = true
    buttonText.value = 'Отправка формы...'
    const requestOptions = {
      method: "GET",
      redirect: "follow",
    };
    fetch(`https://script.google.com/macros/s/AKfycbwwrYhqqOuqtSrGSzYJCwCkRWHzojry41Os6saavIjYXzuF46Ell1oUWhCSG6H_ezc_/exec?fio=${fio.value}&iam=${iam.value}&iamwith=${iamwith.value}&alco=${alco.value}`, requestOptions)
      .then(response => {
          buttonText.value = '✓ Форма отправлена'
      })
  } catch {

  }
}

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
    .button {
      width: 100%;
      height: 100px;
      margin-top: 25px;
      font-family: 'Gilroy';
      border: none;
      background-color: $white;
      font-size: 42px;
      border-radius: 24px;
      cursor: pointer;
    }
  }
  .margin-top {
    margin-top: 99px;
  }
}

.container-mobile {
  margin-bottom: 30px;
  color: $white;
  .title {
    text-align: center;
    font-family: 'dance';
    font-size: 50px;
    margin-bottom: 39px
  }
  input[type="text"] {
    border: none;
    color: white;
    border-bottom: 2px solid white; /* Цвет и толщина полоски */
    border-radius: 0;
    outline: none; /* Убираем обводку при фокусе */
    background: transparent; /* Прозрачный фон */
    //width: 100%;
    max-width: calc(100% - 16px);
    min-width: calc(100% - 16px);
    font-family: 'Gilroy';
    font-size: 17px
  }
  input[type="radio"] {
    width: 17px;
    height: 17px;
    accent-color: #232323;
  }
  input[type="checkbox"] {
    width: 17px;
    height: 17px;
    accent-color: #232323;
  }
  .input-container {
    padding-left: 5px;
    padding-right: 5px;
    .text {
      text-align: start;
      font-family: 'Gilroy';
      font-size: 20px;
      margin-bottom: 5px;
    }
    .radio {
      display: flex;
      align-items: center;
      .radio-label {
        margin-left: 5px;
        font-family: 'Gilroy';
        font-size: 18px;
        cursor: pointer;
      }
    }
    .checkbox {
      display: flex;
      align-items: center;
      .checkbox-label {
        margin-left: 5px;
        font-family: 'Gilroy';
        font-size: 18px;
        cursor: pointer;
      }
    }

    .button {
      width: 100%;
      margin-top: 25px;
      font-family: 'Gilroy';
      border: none;
      background-color: $white;
      font-size: 30px;
      color: black;
      border-radius: 24px;
      cursor: pointer;
    }
  }
  .margin-top {
    margin-top: 52px;
  }
}
</style>