

<script setup>
import { ref, onMounted } from 'vue';

const imageList = ref([]);
const currentIndex = ref(0);

onMounted(() => {
  imageList.value = Array.from(
    document.querySelectorAll('.product__img')
  );
  updateImage();
});

const updateImage = () => {
  imageList.value.forEach((image, index) => {
    image.style.display = index === currentIndex.value ? 'block' : 'none';
  });
}

const leftButtonClicked = () => {
  currentIndex.value--;
  if (currentIndex.value < 0) {
    currentIndex.value = imageList.value.length - 1;
  }
  updateImage();
}

const rightButtonClicked = () => {
  currentIndex.value++;
  if (currentIndex.value >= imageList.value.length) {
    currentIndex.value = 0;
  }
  updateImage();
}

</script>

<template>
    <div class="product__pic">
        <ul class="product__list">
            <li class="product__item">
                <img class="product__img" src="../assets/Porsheone.jpg" alt="вид машины с боку" />
            </li>
            <li class="product__item item-block">
                <img class="product__img item-block" src="../assets/porsche-2.jpg" alt="вид машины с зади" />
            </li>
            <li class="product__item item-block">
                <img class="product__img" src="../assets/porsche-3.jpg" alt="вид машины в салоне" />
            </li>
            <li class="product__item item-block">
                <img class="product__img" src="../assets/porsche-4.jpg" alt="коробка передачи механическая" />
            </li>
        </ul>
        <div class="product__button-box">
            <button class="product__button-left product__button" @click="leftButtonClicked">
                <svg class="product__buton-icon" width="20" height="42" viewBox="0 0 23 44" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M22.4443 44.1739L3.10979 24.8394C1.94306 23.6658 1.94306 21.7703 3.10979 20.5967L22.4443 1.26221"
                        stroke="#F9572E" stroke-width="3" />
                </svg>
            </button>
            <button class="product__button-right product__button" @click="rightButtonClicked">
                <svg class="product__buton-icon" width="20" height="42" viewBox="0 0 23 44" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M1.44434 1.26221L20.7789 20.5967C21.9504 21.7683 21.9504 23.6678 20.7789 24.8394L1.44434 44.1739"
                        stroke="#F9572E" stroke-width="3" />
                </svg>
            </button>
        </div>
    </div>
</template>







<style lang="scss">
$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;

.product {
    margin: 0;
    padding: 0;
    width: 280px;
    margin: 0 auto;
    

    &__title {
        margin: 0;
        padding: 0;
        text-align: center;
        font-size: 24px;
        padding-top: 20px;
    }

    &__price {
        margin: 0;
        padding: 0;
        text-align: center;
        padding-top: 50px;
        font-size: 20px;
    }

    &__list {
        margin: 0;
        padding: 0;
        list-style-type: none;
        margin-top: 30px;
        height: 150px;
        margin-bottom: 30px;
       

    }

    &__item {
        margin: 0;
        padding: 0;

    }

    &__img {
        height: 150px;
        object-fit: cover;
    }

    &__pic {
        position: relative;
    }

    &__button-box {
        width: 280px;
        display: flex;
        justify-content: space-between;
        padding-left: 5px;
        padding-right: 5px;
        position: absolute;
        top: 50px;
    }

    &__button {
        background-color: rgba(234, 239, 240, 0.0);
        border: none;
    }

    &__buton-icon:hover {
        height: 25px;
    }
}

@media (min-width:$tablet-width) {


.product { 
    width: 708px;


    &__title {
        font-size: 30px;
    }

    &__price {
        padding-top: 50px;
        font-size: 25px;
    }

    &__list {
        margin-top: 50px;
        height: 300px;
        margin-bottom: 50px;
        width: 100%;

    }

    &__item {
        margin: 0;
        padding: 0;

    }

    &__img {
        height: 300px;
        object-fit: cover;
       border-top-left-radius: 50px/50px;
       border-top-right-radius: 50px/50px;
    }

    &__pic {
        position: relative;
    }

    &__button-box {
        width: 708px;
        padding-left: 15px;
        padding-right: 15px;
        position: absolute;
        top: 120px;
    }

    &__button {
        background-color: rgba(234, 239, 240, 0.0);
        border: none;
    }

    &__buton-icon:hover {
        height: 25px;
    }

}
}

@media (min-width:$desktop-width){
   
   .product { 
       width: 1220px;
       display: grid;
       grid-template-columns: 600px 450px;
       grid-template-rows: 135px  300px 135px;
       column-gap: 30px;
       justify-content: space-between;
       
       
   

       &__title {
           font-size: 40px;
           grid-column: 1/2;
           margin: auto auto;
           padding: 0;

       }

       &__price {
           padding-top: 0;
           font-size: 40px;
           grid-column: 1/2;
           grid-row: 3/4;
           margin: auto auto;
       }

       &__list {
           margin-top: 0;
           height: 300px;
           margin-bottom: 0;
           width: 100%;
           grid-column: 1/2;
           grid-row: 2/3;

       }

       &__item {
           margin: 0;
           padding: 0;

       }

       &__img {
           height: 300px;
           object-fit: contain;
          border: none;
          width: 100%;
       }

       &__pic {
           position: relative;
       }

       &__button-box {
           width: 600px;
           padding-left: 15px;
           padding-right: 15px;
           position: absolute;
           top: 130px;
       }

       &__button {
           background-color: rgba(234, 239, 240, 0.0);
           border: none;
       }

       &__buton-icon:hover {
           height: 25px;
       }
    }
}

</style>



<!-- <ul class="product__list">
    <li class="product__item" v-for="(item, index) in productList" :key="index">
      <img class="product__img" :src="item.image" :alt="item.alt"/>
    </li>
  </ul>

const productList = [
  { image: "../assets/Porsheone.jpg", alt: "вид машины с боку" },
  { image: "../assets/porsche-2.jpg", alt: "вид машины с зади" },
  { image: "../assets/porsche-3.jpg", alt: "вид машины в салоне" },
  { image: "../assets/porsche-4.jpg", alt: "коробка передачи механическая"}
];-->