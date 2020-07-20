<template>
  <v-container class="pa-6">
    <div>구름URL : <a href="https://level.goorm.io/exam/43241/%EA%B3%84%EC%82%B0%EA%B8%B0/quiz/1" target="_blank">계산기</a></div>
    <v-text-field
      v-on:keyup.enter="submit"
      label="값 입력"
    ></v-text-field>
    <p>{{title}}</p>
  </v-container>
</template>

<script>
export default {
  data: function() {
    return {
      title: ''
    };
  },
  methods: {
    submit: function(event) {
      // `event` 는 네이티브 DOM 이벤트입니다
      if (event) {
        // console.log(event.target.value)
        let line = event.target.value;
        // if (line <= 0) {console.log(0);rl.close();}
        if (line < 100 || line < 0) {
          line = line * 0.005;
        } else if (line < 200) {
          line = line * 0.007;
        } else if (line < 300) {
          line = line * 0.009;
        } else {
          line = line * 0.01;
        }
        this.title = line.toFixed(2);
      }
    }
  },
}
</script>

<style>

</style>