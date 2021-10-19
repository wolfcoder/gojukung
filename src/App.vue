<template>
  <TheHeader/>
  <div id="router-view-wrapper" class="pt-12 text-sm text-gray-700 tex">
    <router-view/>
  </div>
</template>

<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue';
</script>