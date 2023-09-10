<template>
    <div class="product__content">
        <h3 class="visully-hidden">О машине Porshe</h3>
      <div class="tabs">
        <div class="tab" :class="{ active: activeTab === 'Tab1' }" @click="activeTab = 'Tab1'">
        <span class="tab__text">Описание Машины вашей мечты</span>
        </div>
        <div class="tab" :class="{ active: activeTab === 'Tab2' }" @click="activeTab = 'Tab2'">
            <span class="tab__text">Характеристики машины</span>
        </div>
      </div>
      <div v-if="activeTab === 'Tab1'" class="tab-content">
        Силуэт 911 Carrera безошибочно узнаваем благодаря культовой покатой линии
            крыши Flyline, которая формирует ДНК марки Porsche с 1963 года – так же, как и выдающиеся характеристики
            спортивных автомобилей.
            На выбор есть пять вариантов: заднеприводный Porsche 911 Carrera GTS с кузовами купе и кабриолет,
            полноприводный Porsche 911 Carrera 4 GTS тоже с двумя типами кузова, а также Porsche 911 Targa 4 GTS. От
            прочих «девятьсот одиннадцатых» машины с приставкой GTS отличаются сдержанным черным декором (включая колеса
            и решетку в крышке двигателя), а также затемненными фарами и задними фонарями.
            Шасси купе и кабриолета такое же, как у версии Turbo: здесь подвеска PASM с адаптивными амортизаторами,
            другими пружинами и уменьшенным на 10 мм дорожным просветом. При этом самой тяжелой тарге оставили подвеску
            Карреры S, дополненную адаптивными амортизаторами, ведь Porsche 911 Turbo не предлагается с таким типом
            кузова. Зато все GTS-машины имеют мощные Turbo-тормоза — с десятипоршневыми механизмами на передней оси
            вместо шестипоршневых у версии Carrera S. Шины с увеличенной на 10 мм шириной тоже взяты из набора Turbo.
      </div>
      <div v-if="activeTab === 'Tab2'" class="tab-content">
        <dl class="tabs__description"> 
                <dt class="tabs__description-title border-bottom">Передние шины </dt>
                <dd class="tabs__description-item border-bottom">265/35 ZR19</dd>
                <dt class="tabs__description-title">Задние шины</dt>
                <dd class="tabs__description-item">335/30 ZR20</dd>
                <dt class="tabs__description-title">Объем</dt>
                <dd class="tabs__description-item">5.7 л</dd>
                <dt class="tabs__description-title">Мощность</dt>
                <dd class="tabs__description-item">612 л. с.</dd>
                <dt class="tabs__description-title">Расход</dt>
                <dd class="tabs__description-item">17,8 л</dd>
                <dt class="tabs__description-title">Тип топлива<br> Бензин</dt>
                <dd class="tabs__description-item">АИ-98</dd>
                <dt class="tabs__description-title">Привод</dt>
                <dd class="tabs__description-item"> Задний</dd>
                <dt class="tabs__description-title">Кол-во мест</dt>
                <dd class="tabs__description-item"> 2 места</dd>
                <dt class="tabs__description-title">Кол-во дверей</dt>
                <dd class="tabs__description-item">2 двери</dd>
                <dt class="tabs__description-title">Объем багажника</dt>
                <dd class="tabs__description-item">276 л</dd>
            
            </dl>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const activeTab = ref('Tab1');
  </script>
  
 
  
  
  


<style lang="scss">

$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;

.product__content {
    position: relative;
    width: 280px;
}
.tabs {
    display: flex;
    justify-content: space-between;

  }
  
  .tab {
    padding: 10px;
    cursor: pointer;
    background-color: #eee;
    border: 1px solid #ddd;
    width: 140px;
    text-align: center;
    font-size: 15px;
    font-family: "Oswaldr", "Arial", sans-serif;
    
  &.active {
    background-color: #ccc;
  }
 


}
  
  .tab-content {
    margin-top: 10px;
    padding: 15px;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    text-align:justify;
    font-size: 15px;
    font-family: "Lato", "Arial", sans-serif;
    height: 752px;
  }
  .tabs__description {
    display: grid;
    grid-template-columns: auto auto;
    row-gap: 30px;
    text-transform: uppercase;
    font-size: 14px;
    line-height: 30px;
    align-items: center;   
  }
 


@media (min-width:$tablet-width) {


    .product__content {
        position: relative;
        width:708px ;
    }
  
  
  .tab {
    padding: 25px;
    cursor: pointer;
    background-color: #eee;
    border: 1px solid #ddd;
    width: 354px;
    height: 70px;
    font-size: 20px;
}
  
  .tab-content {
    margin-top: 10px;
    padding: 10px;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    padding: 50px;
    font-size: 17px;
    line-height: 30px;
    height: 600px;
  }
  .tabs__description {
    row-gap: 20px;
    justify-content: space-between; 
    text-align: center;
  }

}
@media (min-width:$desktop-width) {

    .product__content {
        position: relative;
        grid-column: 2/3;
        grid-row: 1/4;
        width: 450px;
        

    }
    .tab {
    padding: 0;
    cursor: pointer;
    background-color: #eee;
    border: 1px solid #ddd;
    width: 225px;
    height: 70px;
    font-size: 20px;
    align-items: center;

    &__text{
        margin: 0;
        padding: 0;
        display: block;
        margin: auto auto;
        width: 150px;
        padding-top: 10px;
    }
}

  
  .tab-content {
    margin-top: 10px;
    padding: 15px;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    height: 490px;
    font-size: 15px;
    line-height: 21px;
  }
  .tabs__description {
    row-gap: 10px;
    justify-content:space-between;
    text-align: center;
  }
}</style>