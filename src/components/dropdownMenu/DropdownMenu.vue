<script setup lang="ts">
import jsonData from '@/data.json'
import { json } from 'stream/consumers'
import RenderComponent from './RenderComponent.vue'
</script>
<template>
  <!-- <ul class="dropdown">
    <li>Menu 1</li>
    <li>Menu 2</li>
    <li>Menu 3</li>
  </ul> -->
  <div>
    <ul class="list-unstyled nav-menu d-flex flex-column align-items-start">
      <RenderComponent v-for="(item, index) in jsonData.menu" :key="index" :menuItem="item" />
    </ul>
  </div>
</template>
