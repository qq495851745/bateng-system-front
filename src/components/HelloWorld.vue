<template>
 <p @click="handleClick">{{item}}</p>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['item', 'index'],
  methods: {
    handleClick () {
      this.$emit('del', this.index)
    }
  }

}
</script>
