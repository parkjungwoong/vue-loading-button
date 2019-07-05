<template>
  <div id="app">
    {{msg}}<br>
    <loading-button title="api요청" :click-func="apiCall"/> <br>
    <loading-button title="class지정" class-nm="btn2" :click-func="apiCall"/> <br>
    <loading-button title="파라미터" :click-func="apiCall" :func-param="parameter"/>
  </div>
</template>

<script>
import LoadingButton from './components/LoadingButton.vue'

export default {
  name: 'app',
  components: {
    LoadingButton
  },
  data() {
    return {
      msg: '버튼을 클릭하세요.',
      parameter: '부모에서 넘긴는 파라미터'
    }
  },
  methods: {

    async apiCall(_param) {
      this.msg = _param ? _param : '';
      this.msg = await this.nonSyncMethod();
    },

    nonSyncMethod() {
      return new Promise(resolve => {
        setTimeout(function() {
          resolve('완료');
        }, 2000);
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  .btn {
    background-color: gold;
  }

  .btn2 {
    background-color: chartreuse;
  }
</style>
