<template>
  <div class="hello">
    <group>
      <cell title="title" value="value">{{msg}}</cell>
    </group>
  </div>
</template>

<script>
import { Group, Cell } from 'vux';
import common from '../common';
import qs from 'qs';
const {urlfix}=common;
export default {
  name: 'HelloWorld',
  components: {
    Group,
    Cell
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    console.log(urlfix)
    const query={
            range:'all',
            sort:'_created',
            project:'code,name'
          }
    this.$http.get(`${urlfix}/ProjectInstance?${qs.stringify(query)}`,{emulateJSON : true})
     .then(function(data){
       console.log(data)
     })
     .then(function(data){
       console.log(data)
     })
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
