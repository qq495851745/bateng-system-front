<template>
  <div>
    <input v-model="inputValue"/>
    <button @click="handleClick">插入数据</button>
    <hello-world v-for="(item,index) of list"
                 :item="item"
                 :index="index"
                 @del="del"></hello-world>
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld'

  export default {
    name: 'App',
    components: {HelloWorld},
    data() {
      return {
        inputValue: 'test',
        list: []
      }
    },
    methods: {
      handleClick() {
        this.list.push(this.inputValue);
        this.inputValue = ''

      },
      del(index){
        this.list = this.list.slice(0,index).concat(this.list.slice(index+1))
      }
    },
    comments: {
      'hello-world': HelloWorld
    }

  }
</script>

<style>

</style>
