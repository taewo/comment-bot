<template>
  <div style="border:1px solid red;">
    <!-- <input :value="value" @input="$emit('update:value', $event.target.value)" type="text"> -->
    <!-- <input v-model="inputValue" type="text"> -->
    <Test2 :value123.sync="msg" />
  </div>
</template>
<script>
import Test2 from './Test2'

export default {
  components: {
    Test2
  },
  computed: {
    inputValue: {
      get() {
        console.log('get---', this.value)
        return this.value
      },
      set(val) {
        console.log('set---', val)
        this.$emit('input', val)
      }
    }
  },
  data() {
    return {
      name: 'taewoong'
    }
  },
  methods: {
    handleInput() {
      this.$emit('value', this.value)
    }
  }
}
</script>
<style lang=''>

</style>
