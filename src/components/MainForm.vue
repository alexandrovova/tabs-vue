
<script setup>
import Form from '../components/Form.vue'


</script>


<template>
     <section class="form-page">
      <h2 class="visully-hidden">Форма для заказа машины</h2>
          <Form /> 
    </section>
</template>



<style lang="scss">
$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;

.form-page{
    margin: 0;
    padding: 0;
    width: 280px;
    margin: 0 auto;
    padding-top: 20px;
    padding-bottom: 20px;
}


@media (min-width:$tablet-width) {

    .form-page {
        width: 708px;
        margin: 0 auto;
        padding-top: 50px;
        padding-bottom: 40px;
    }
}
@media (min-width:$desktop-width) {
    .form-page {
        width: 1220px;
        margin: 0 auto;
        padding-top: 70px;
        padding-bottom: 50px;
    }
}



</style>