<template>
  <div class="hello">
    {{num}}{{a}}
  </div>
</template>

<script>
import {ref,reactive} from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup(){
    const num= ref(1);
    const obj=reactive({a:'a'}) 
    setTimeout(()=>{
      num.value=num.value+1000
    },2000)
    return {
      num,
      ...obj
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
