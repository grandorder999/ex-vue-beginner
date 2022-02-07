<template>
  <div class="container">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}歳</div>
    <div>10年後の年齢：{{ age + 10 }}歳</div>
    趣味：<span v-for="hobby of hobbies" v-bind:key="hobby">{{ hobby }}</span
    ><br />
    <div><a v-bind:href="companyUrl">株式会社ラクスパートナーズ</a></div>
    <div><img v-bind:src="imgUrl" alt="犬" /></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "山田太郎";
  private age = 31;
  private hobbies = ["スイム ", "バイク ", "ラン"];
  private companyUrl = "https://career-engineer.jp/";
  private imgUrl = "img/dog.jpeg";
}
</script>

<style scoped>
div.container {
  text-align: left;
  border: solid 2px black;
}
</style>
