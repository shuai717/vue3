<template>
  <div class="hello">
    {{num}}{{a}}
    <button @click="add">click</button>
  </div>
</template>

<script>
import {ref,reactive,onMounted,watch} from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // methods:{
  //   add(){
  //     num.value+='a'
  //   }
  // },
  setup(){
    const num= ref(1);
    const obj=reactive({a:'a'})
    onMounted(()=>{
      setTimeout(()=>{
        num.value=num.value+1000
      },2000)
    })
    num.value=num.value+1000
    watch(num,(value)=>{
      console.log(value,'value')
    })
    const add=()=>{
      num.value+='a'
    }
    return {
      num,
      ...obj,
      add
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
