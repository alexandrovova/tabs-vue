

<template>
    <nav :class="{'main-nav': true, 'main-nav--closed': isClosed, 'main-nav--opened': isOpened}">
      <button class="main-nav__toggle" type="button" @click="toggleNav">
        <span class="visully-hidden">Открыть меню.</span>
      </button>
      <ul class="main-nav__list site-list">
        <li class="site-list__item">
          <a class="site-list__link" href="#">Главная</a>
        </li>
        <li class="site-list__item">
          <a class="site-list__link site-list__link--active">Заказать сейчас</a>
        </li>
        <li class="site-list__item">
          <a class="site-list__link" href="#form">FAQ</a>
        </li>
      </ul>
    </nav>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const isClosed = ref(true);
  const isOpened = ref(false);
  
  const toggleNav = () => {
    isClosed.value = !isClosed.value;
    isOpened.value = !isOpened.value;
  };
  </script>

<style lang="scss">

$mobile-width-only: 767px;
$tablet-width: 768px;
$desktop-width: 1280px;

.main-nav {
    position: relative;
    width: auto;
    background-color: #ffffff;
  }
  
  .main-nav__list {
    display: flex;
    flex-direction: column;
    text-align: center;
  }
  
  .main-nav__toggle {
    padding: 0;
    width: 57px;
    height: 65px;
    position: absolute;
    background: transparent;
    top: -65px;
    left: calc(50% + 95px);
    border: none;
    cursor: pointer;
  }
  
  .main-nav--closed .main-nav__toggle::before {
    content: "";
    position: absolute;
    top: 24px;
    left: 50%;
    width: 24px;
    transform: translate(-50%);
    height: 1.5px;
    background-color: #000000;
    box-shadow: 0 7.5px 0 0 #000000, 0 15px 0 0 #000000;
  }
  
  .main-nav--opened .main-nav__toggle::after {
    content: "";
    position: absolute;
    top: 28px;
    left: 50%;
    transform: translate(-50%) rotate(45deg);
    height: 1.5px;
    width: 24px;
    background-color: #000000;
  }
  
  .main-nav--opened .main-nav__toggle::before {
    content: "";
    position: absolute;
    top: 28px;
    left: 50%;
    transform: translate(-50%) rotate(-45deg);
    height: 1.5px;
    width: 24px;
    background-color: #000000;
  }
  .site-list {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  .site-list__item {
    font-weight: 500;
    font-size: 20px;
    line-height: 20px;
    min-height: 65px;
    text-transform: uppercase;
  }
  
  .site-list__link {
    text-decoration: none;
    color: #000000;
    display: block;
    padding-top: 23px;
    padding-bottom: 23px;
  }
  
  @media (max-width: $mobile-width-only) {
    .main-nav--closed .site-list__item {
      display: none;
    }
  
    .main-nav--opened .site-list {
      position: absolute;
      top: 0;
      z-index: 1;
      background-color: #ffffff;
      transform: translate(-50%);
      left: 50%;
      width: 100%;
    }
  
    .main-nav--nojs .main-nav__toggle {
      display: none;
    }
  
    .main-nav--nojs .site-list {
      position: static;
    }
  
    .main-nav--nojs .site-list__item {
      display: block;
    }

    .site-list__item {
      border-bottom: 1px solid #e6e6e6;
  
      &:nth-child(1) {
        border-top: 1px solid #e6e6e6;
      }
    }
  }
  
  @media (min-width: $tablet-width) {
    .main-nav {
      width: 440px;
    }
  
    .main-nav__list {
      display: flex;
      flex-direction: row;
      min-width: 440px;
    }
  
    .main-nav__toggle {
      display: none;
    }
    .site-list {
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 31px;
      margin-top: 4px;
    }
  
    .site-list__item {
      padding: 0;
      font-weight: 400;
      font-size: 17px;
      line-height: 24px;
      min-height: 0;
      position: relative;
    }
  
    .site-list__link {
      padding: 10px 0;
  
      &:hover {
        opacity: 60%;
      }
  
      &:focus {
        opacity: 30%;
      }
  
      &:active {
        opacity: 100%;
      }
  
      &--active::before {
        content: "";
        position: absolute;
        width: 100%;
        height: 2px;
        background-color: #68b738;
        bottom: 0;
        left: 0;
      }
  
      &--active-wite::after {
        content: "";
        position: absolute;
        width: 100%;
        height: 2px;
        background-color: #68b738;
        bottom: 0;
        left: 0;
      }
    }
  }
  
  @media (min-width: $desktop-width) {
    .main-nav {
      width: 490px;
      background-color: transparent;
    }
    .site-list {
      width: 480px;
      margin: 0;
      margin-left: 10px;
    }
  
    .site-list__item {
      padding: 0;
      font-weight: 400;
      font-size: 19px;
      line-height: 30px;
    }
  
    .site-list__link {
      &--active-wite::after {
        content: "";
        position: absolute;
        width: 100%;
        height: 2px;
        background-color: #ffffff;
        bottom: 0;
        left: 0;
      }
  
      &--iner {
        color: #ffffff;
      }
    }
  }
  
</style>


