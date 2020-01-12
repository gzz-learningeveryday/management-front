<template>
  <div class="hello">
    <h1>{{getMenu}}</h1>
    <h1>{{menu}}</h1>
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
      
    }
  },
  computed: {
    // 计算属性的 getter
    getMenu: function () {
     axios.get('/mock', {
        params: {
          ID: 12345
        }
      }).then((response)=> {
        console.log(response.data);
        this.menu = response.data;
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

</style>
