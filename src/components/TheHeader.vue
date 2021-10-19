<template>
  <div class="py-3 px-4 text-gray-700 border-b fixed w-full bg-white z-40">
    <div class="container mx-auto flex self-center">
    <img class="h-7 w-7" alt="Putra Tresna FC" src="../assets/logo.png" @click="$router.push('/')">
    <h1 class="ml-2 font-bold text-lg  " @click="$router.push('/')">Putra Tresna FC</h1>
    <span class="ml-auto mt-1 hide-in-print" @click="toggleMenu">
      <svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="20"
           height="20" viewBox="0 0 20 20">
        <path
            d="M17.5 6h-15c-0.276 0-0.5-0.224-0.5-0.5s0.224-0.5 0.5-0.5h15c0.276 0 0.5 0.224 0.5 0.5s-0.224 0.5-0.5 0.5z"
            fill="#000000"></path>
        <path
            d="M17.5 11h-15c-0.276 0-0.5-0.224-0.5-0.5s0.224-0.5 0.5-0.5h15c0.276 0 0.5 0.224 0.5 0.5s-0.224 0.5-0.5 0.5z"
            fill="#000000"></path>
        <path
            d="M17.5 16h-15c-0.276 0-0.5-0.224-0.5-0.5s0.224-0.5 0.5-0.5h15c0.276 0 0.5 0.224 0.5 0.5s-0.224 0.5-0.5 0.5z"
            fill="#000000"></path>
      </svg>
    </span>
    </div>

  </div>
  <teleport to="#modal" v-if="isMenu">
    <TheMenu @close="toggleMenu"/>
  </teleport>
</template>
<script>
import {ref} from "vue";
import TheMenu from "../components/TheMenu.vue";

export default {
  name: 'TheHeader',
  components: {TheMenu},
  setup() {
    let isMenu = ref(false)
    const toggleMenu = () => {
      let htmlBody = document.getElementsByTagName('body');

      if (htmlBody[0].style.overflow === '' || htmlBody[0].style.overflow === 'scroll') {
        htmlBody[0].style.overflow = 'hidden'
      } else {
        htmlBody[0].style.removeProperty('overflow')
      }

      isMenu.value = !isMenu.value;
    }
    return {isMenu, toggleMenu}
  }

}
</script>

