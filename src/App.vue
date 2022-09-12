<script setup>
import MyButton from "./components/MyButton.vue";
</script>

<template>
  <p><code>MyButton default</code></p>
  <MyButton> </MyButton>
  <p><code>MyButton default medium</code></p>
  <MyButton size="md"></MyButton>
  <p><code>MyButton default large</code></p>
  <MyButton size="lg"></MyButton>
  <p><code>MyButton default large no-shadow </code></p>
  <MyButton
    size="lg"
    :is-shadow="false"
  ></MyButton>
  <p><code>MyButton default primary</code></p>
  <MyButton color="primary"></MyButton>
  <p><code>MyButton default secondary</code></p>
  <MyButton color="secondary">
    <template v-slot:text>Secondary</template>
  </MyButton>
  <p><code>MyButton default danger</code></p>
  <MyButton color="danger">
    <template v-slot:text>Danger</template>
  </MyButton>
  <p><code>btn outline</code></p>
  <MyButton :variant="'outline'">
    <template v-slot:text>Outline</template>
  </MyButton>
  <p><code>btn text</code></p>
  <MyButton :variant="'text'">
    <template v-slot:text>Btn text</template>
  </MyButton>
  <MyButton
    :variant="'text'"
    :icon-position="'end'"
    :end-icon="'double_arrow'"
  >
    <template v-slot:text>Link text</template>
  </MyButton>

  <p><code>btns with icon</code></p>
  <div style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 2rem">
    <MyButton
      color="primary"
      size="md"
      :end-icon="'add_shopping_cart'"
    >
      <template v-slot:text>Add to cart</template>
    </MyButton>

    <MyButton
      :icon-position="'end'"
      color="danger"
      size="md"
      :start-icon="'add_shopping_cart'"
    >
      <template v-slot:text>Remove from cart</template>
    </MyButton>
  </div>

  <p><code>MyButton default disabled</code></p>
  <MyButton :is-disabled="true"> </MyButton>
</template>

<style scoped></style>
