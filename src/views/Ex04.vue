<template>
  <div class="container">
    <input type="number" v-model.number="num1" /><br />
    <input type="number" v-model.number="num2" /><br />
    <input type="number" v-model.number="num3" />
    <div>税抜き価格：{{ nonTaxedPrice.toLocaleString() }}円</div>
    <div>税込み価格：{{ total.toLocaleString() }}円</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  readonly TAX = 1.1;
  private num1 = 0;
  private num2 = 0;
  private num3 = 0;

  get nonTaxedPrice(): number {
    return Math.floor(this.num1 + this.num2 + this.num3);
  }
  get total(): number {
    return Math.floor(this.nonTaxedPrice * this.TAX);
  }
}
</script>

<style scoped></style>
