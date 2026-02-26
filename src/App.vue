<script setup lang="ts">
import { ref } from "vue";
import Navbar from "./components/Navbar.vue";
import DashboardPage from "./views/DashboardPage.vue";
import SettingsPage from "./views/SettingsPage.vue";

export type Page = "dashboard" | "tasks" | "settings";

const currentPage = ref<Page>("dashboard");

const handlePage = (page: Page) => {
  currentPage.value = page;
};
</script>

<template>
  <DashboardPage v-if="currentPage === 'dashboard'" />
  <SettingsPage v-else-if="currentPage === 'settings'" />

  <Navbar :change-page="handlePage" />
</template>

<style scoped></style>
