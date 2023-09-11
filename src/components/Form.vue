<template>
  <form @submit="handleSubmit" action="#" method="post" id="form">
    <fieldset class="form__order">
      <legend class="form__order-name">Закажите Сейчас</legend>
      <ul class="form__list">
        <li class="form__item">
          <span class="visully-hidden">Имя и Фамилия</span>
          <input class="form__input" v-model="inputValue" type="text" placeholder="Имя и фамилия" />
        </li>
        <li class="form__item">
          <span class="visully-hidden">Номер телефона*</span>
          <input class="form__input" v-model="inputTell" type="tel" placeholder="Телефон" />
        </li>
      </ul>
      <button class="form__button" type="submit">Submit</button>
      <a class="form__link" href="#"><span>Политика конфиденциальности</span></a> 
    </fieldset>
  </form>

  <div v-if="showModal" class="modal">
    <div class="modal__content">
      <p class="modal__text">{{ modalMessage }}</p>
      <button class="modal__button" @click="closeModal">крестик</button>
    </div>
  </div>
</template>
  

<script setup>
import { ref } from 'vue';

const inputValue = ref('');
const inputTell = ref('');
const showModal = ref(false);
const modalMessage = ref('');

const handleSubmit = (event) => {
  event.preventDefault();

  // Processing the form data here...
  // For this example, we'll just display a fixed modal message
  modalMessage.value = 'Наш менеджер свяжется с вами в течении 5 минут хорошего дня';
  showModal.value = true;

  inputValue.value = ''; // удаляем значение текста в инпуте
  inputTell.value = ''; // идаляю значения телефона в инпуте
}

function closeModal() {
  showModal.value = false;
}
</script>
  
<style lang="scss">
$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;
.form {
  &__order {
    margin: 0;
    padding: 0;
    border: 2px solid rgb(18, 187, 18);
  }

  &__order-name {
    margin: 0;
    padding: 0;
    text-align: center;
    padding-left: 10px;
    padding-right: 10px;
    font-size: 24px;
    text-transform: uppercase;
  }

  &__list {
    margin: 0;
    padding: 0;
    list-style-type: none;
    padding: 30px 10px;
  }

  &__item {
    margin: 0;
    padding: 0;
    width: 100%;
  }

  &__item:nth-child(1) {
    margin-bottom: 20px;
  }

  &__input {
    width: 100%;
    border: 2px solid gray;
    border-radius: 4%;
    padding: 15px 20px;
  }

  &__button {
    display: block;
    margin: 0 auto;
    background-color: rgb(18, 187, 18);
    padding: 5px 30px;
    border: none;
    border-radius: 50px/50px;
    color: #f2f2f2;
    cursor: pointer;
  }

  &__button:hover {
    background-color: rgb(98, 241, 98);
  }
  &__link {
        text-transform: uppercase;
        font-size: 10px;
        font-family: "lato", sans-serif;
        color: #3521cb;
        display: block;
        margin-top: 10px;
        text-align: center;
        margin-bottom: 40px;
    }
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;


  &__content {
  background-color: white;
  padding: 20px;
  width: 280px;
  height: 300px;
  border: 5px solid green;
}
&__text{
  font-size: 20px;
  text-align: center;
  margin: 40% auto;

}
&__button{
  display: block;
    margin: 0 auto;
    background-color: rgb(18, 187, 18);
    padding: 5px 30px;
    border: none;
    border-radius: 50px/50px;
    color: #f2f2f2;
    cursor: pointer;
}
&__button:hover {
    background-color: rgb(98, 241, 98);
}
}

@media (min-width:$tablet-width) {

  .form {

&__order {
    margin: 0;
    padding: 0;
    border: 4px solid rgb(18, 187, 18);
}

&__order-name {
    margin: 0;
    padding: 0;
    text-align: center;
    padding-left: 20px;
    padding-right: 20px;
    font-size: 30px;
    text-transform: uppercase;
}

&__list {
    margin: 0;
    padding: 0;
    list-style-type: none;
    padding: 50px 50px;
}

&__item {
    margin: 0;
    padding: 0;
    width: 100%;
}

&__item:nth-child(1) {
    margin-bottom: 40px;
}

&__input {
    width: 100%;
    border: 4px solid gray;
    border-radius: 4%;
    padding: 15px 20px;
    font-size: 15px;
}

&__button {
    display: block;
    margin: 0 auto;
    background-color: rgb(18, 187, 18);
    padding: 10px 30px;
    border: none;
    border-radius: 50px/50px;
    color: #f2f2f2;
    cursor: pointer;
    font-size: 20px;
}

&__button:hover {
    background-color: rgb(98, 241, 98);
}

&__link {
    text-transform: uppercase;
    font-size: 15px;
    font-family: "lato", sans-serif;
    color: #3521cb;
    display: block;
    margin-top: 20px;
    text-align: center;
    margin-bottom: 40px;
}

}
.modal {
  &__content {
  background-color: white;
  padding: 20px;
  width: 708px;
  height: 300px;
  border: 5px solid green;
}
&__text{
  font-size: 25px;
  text-align: center;
  margin: 0;
  margin-top: 50px;
  padding-bottom: 100px;

}
&__button{
    padding: 10px 30px;
    font-size: 20px;
}
}
}
@media (min-width: $desktop-width) {

  .form {

&__order {
    margin: 0;
    padding: 0;
    border: 4px solid rgb(18, 187, 18);
    width: 709px;
    margin: 0 auto;
}

&__order-name {
    margin: 0;
    padding: 0;
    text-align: center;
    padding-left: 25px;
    padding-right: 25px;
    font-size: 40px;
    text-transform: uppercase;
}



&__input {
    width: 100%;
    border: 4px solid gray;
    border-radius: 4%;
    padding: 15px 20px;
    font-size: 15px;
}

&__button {
    padding: 10px 50px;
}
}
}


</style>
  <!--Он содержит форму с двумя полями ввода (имя и фамилия, номер телефона), кнопку отправки формы и модальное окно, которое показывается после отправки формы.

При отправке формы вызывается функция handleSubmit, которая предотвращает стандартное поведение формы (перезагрузку страницы) и отображает модальное окно с сообщением "Form submitted successfully!".

Функция closeModal вызывается при нажатии на кнопку "Close" в модальном окне и скрывает модальное окно, устанавливая значение переменной showModal в false.

-->