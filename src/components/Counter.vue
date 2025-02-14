<script setup lang="ts">
import { Button } from "$/components/ui/button";
import {
  Card,
  CardContent,
  CardHeader,
  CardTitle,
} from "$/components/ui/card";

import { ref } from "vue";

const count = ref(0);
const add = () => count.value++;
const subtract = () => count.value--;
</script>

<template>
  <div class="counter">
    <Button @click="subtract">-</Button>
    <Card>
      <CardHeader>
        <CardTitle><slot /></CardTitle>
      </CardHeader>
	  <CardContent>
		<div class="items-center text-center">
			<p class="">{{ count }}</p>
			
		</div>
	  </CardContent>
    </Card>

    <Button @click="add">+</Button>
  </div>
  <div class="counter-message"></div>
</template>

<style>
.counter {
  display: grid;
  font-size: 2em;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  margin-top: 2em;
  place-items: center;
}

.counter-message {
  text-align: center;
}
</style>
