<template>
    <ul class="main-nav__list site-list">
      <li class="site-list__item" v-for="(item, index) in list" :key="index">
        <a class="site-list__link" :href="item.link" :class="{'site-list__link--active': item.isActive}">{{ item.text }}</a>
      </li>
    </ul>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const list = ref([
    { text: 'Главная', link: '#' },
    { text: 'Заказать сейчас', link: '', isActive: true },
    { text: 'FAQ', link: '#form' },
  ]);
  </script>
  


        <!--<ul class="main-nav__list site-list">
        <li class="site-list__item">
          <a class="site-list__link" href="#">Главная</a>
        </li>
        <li class="site-list__item">
          <a class="site-list__link site-list__link--active">Заказать сейчас</a>
        </li>
        <li class="site-list__item">
          <a class="site-list__link" href="#form">FAQ</a>
        </li>
      </ul>-->