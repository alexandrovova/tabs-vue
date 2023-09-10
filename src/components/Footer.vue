<template>
     <footer class="main-footer">
    <h2 class="main-footer__name">ТЕСТОВОЕ ЗАДАНИЕ ДЛЯ ВЕБ СТУДИИ <br> <span
        class="main-footer__span">playnext.ru</span></h2>
  </footer>
</template>


<style lang="scss">

$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;

.main-footer{
    margin: 0;
    padding: 0;
    width: 280px;
    background-color: #f2f2f2;
    margin: 0 auto;
    height: 100px;

    &__name{
        
        padding: 0;
        margin: 0;
        font-family: "lato",sans-serif;
        font-size: 10px;
        text-align: center;
        padding-top: 30px;
    }

    &__span{
    font-size: 15px;
    font-family: "osward";
    color: rgb(18, 187, 18);
    
    }

}

@media (min-width:$tablet-width) {

    .main-footer{
      width: 708px;
       
        &__name{
            font-size: 15px; 
        }
        &__span{
        font-size: 20px;
        }
    }

    
}

@media (min-width:$desktop-width) {
    .main-footer{
        width: 1220px;
    }
}
</style>