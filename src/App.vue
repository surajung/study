<template>
  <div>
    <app-header 
      v-bind:propsdata="str"
      v-on:renew="renewStr"
    ></app-header>
    <result-component></result-component>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import ResultComponent from './components/ResultComponent.vue'

  export default {
    data: function() {
      return {
        str: 'header'
      }
    },
    components: {
      'app-header': AppHeader,
      ResultComponent,
    },
    methods: {
      renewStr: function() {
        this.str = 'hi'
      }
    }
  }
</script>