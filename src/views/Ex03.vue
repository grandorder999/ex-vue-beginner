<template>
  <div class="container">
    <input type="number" v-model.number="num1" />+<input
      type="number"
      v-model.number="num2"
    />={{ add }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;

  get add(): number {
    return this.num1 + this.num2;
  }
}
</script>

<style scoped></style>
