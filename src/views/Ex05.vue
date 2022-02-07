<template>
  <div class="container">
    <span class="error">{{ error1 }}</span
    ><br />
    名前：<br />
    <input type="text" v-model="name" /><br />
    <span class="error">{{ error2 }}</span
    ><br />
    年齢：<br />
    <input type="text" v-model="age" /><br />
    <span class="error">{{ error3 }}</span
    ><br />
    コメント：<br />
    <textarea v-model="comment" cols="30" rows="10"></textarea><br />
    <button type="button" v-on:click="error">入力値チェック</button><br />
    <hr />
    <span class="submit">{{ submit }}</span>
    入力値：<br />
    名前：{{ name }}<br />
    年齢：{{ age }}<br />
    コメント：
    <pre>{{ comment }}</pre>
    <br />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "";
  private age = "";
  private comment = "";
  private error1 = "";
  private error2 = "";
  private error3 = "";

  error(): void {
    if (this.name === "" && this.age === "" && this.comment === "") {
      (this.error1 = "名前が入力されていません"),
        (this.error2 = "年齢が入力されていません"),
        (this.error3 = "コメントが入力されていません");
    }
  }
}
</script>

<style scoped>
div.container {
  text-align: left;
  border: solid 2px black;
}
.error {
  color: red;
}
.submit {
  color: blue;
}
</style>
