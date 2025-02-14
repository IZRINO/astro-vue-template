<script setup lang="ts">
import { ref } from "vue";

const count = ref(0);
const add = () => count.value++;
const subtract = () => count.value--;
</script>

<template>
  <div class="counter">
    <button class="btn btn-success" @click="subtract">-</button>

    <div class="card bg-base-100 w-96 shadow-sm">
      <div class="card-body items-center text-center">
        <div class="card-title text-5xl">
          <slot />
        </div>

        <div
          class="bg-neutral rounded-box text-neutral-content flex flex-col p-2 mt-10"
        >
          <span class="countdown font-mono text-5xl">
            <span :style="'--value: ' + count"></span>
          </span>
        </div>
      </div>
    </div>

    <button class="btn btn-success" @click="add">+</button>
  </div>
</template>

<style>
.counter {
  display: grid;
  font-size: 2em;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  margin-top: 2em;
  place-items: center;
}
</style>
