<template>
  <div class="fixed inset-x-0 z-30 bg-green-700">
    <div class="flex-1">
      <div class="container flex items-center justify-between px-3 py-4">
        <div class="flex items-center gap-4">
          <span
            class="cursor-pointer material-symbols-outlined"
            @click="isShow.bool = !isShow.bool"
            v-if="!isShow.bool"
          >
            menu
          </span>
          <router-link
            :to="{ name: 'home' }"
            class="text-lg transition-all hover:text-amber-800"
            :class="{ 'sm:hidden': isShow.bool }"
          >
            Logo
          </router-link>
        </div>
        <div class="">
          <input-search />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useTemplateStore } from "@/stores/template";
import InputSearch from "@/components/input-search.vue";

const isShow = useTemplateStore();
</script>
