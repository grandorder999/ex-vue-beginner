<template>
  <div class="container">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}歳</div>
    <div>10年後の年齢：{{ plus10YearsAge }}歳</div>
    <div>趣味：{{ hobby }}</div>
    <div><a v-bind:href="companyUrl">自社ページリンク</a></div>
    <div><img v-bind:src="imgUrl" /></div>
    <button type="button" v-on:click="up" v-bind:disabled="push">ボタン</button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "";
  private age = 0;
  private plus10YearsAge = 0;
  private hobby = "";
  private companyUrl = "";
  private imgUrl = "";
  private push = false;

  up(): void {
    this.name = "山田太郎";
    this.age = 31;
    this.plus10YearsAge = this.age + 10;
    this.hobby = "スイム バイク ラン";
    this.companyUrl = "https://career-engineer.jp/";
    this.imgUrl = "img/dog.jpeg";
    this.push = true;
  }
}
</script>

<style scoped>
div.container {
  text-align: left;
  border: solid 2px black;
}
</style>
