<script setup lang="ts">
import { House, LayoutListIcon, SettingsIcon } from "lucide-vue-next";
import type { Page } from "../App.vue";

defineProps<{
  changePage: (page: Page) => void;
}>();
</script>

<template>
  <nav class="nav">
    <ul class="nav-list">
      <li class="nav-list-item" @click="() => changePage('dashboard')">
        <House class="nav-list-item__icon" />
      </li>
      <li class="nav-list-item">
        <LayoutListIcon class="nav-list-item__icon" />
      </li>
      <li class="nav-list-item" @click="() => changePage('settings')">
        <SettingsIcon class="nav-list-item__icon" />
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.nav {
  position: fixed;
  bottom: 40px;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 10px;
  background-color: #1f1f1f;
  color: #fff;
  border-radius: 20px;
}

.nav-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}

.nav-list-item {
  padding: 8px 8px 2px;
  border-radius: 12px;
  color: #42b883;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

.nav-list-item:hover {
  background-color: #2f2f2f;
}

.nav-list-item__icon {
  width: 30px;
  height: 30px;
  margin: 0;
}
</style>
