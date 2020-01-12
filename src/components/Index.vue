<template>
  <div class="hello">
    <h1>{{menu}}</h1>
    <el-button type="primary" @click="init">请求后台</el-button>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Index',
  data () {
    return {
      menu: ''
    }
  },
  methods: {
    init: function () {
      axios.get('/mock', {
        params: {
          ID: 12345
        }
      }).then((response)=> {
        console.log(response.data);
        this.menu = response.data;
      });
    }
  },
  computed: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

</style>
