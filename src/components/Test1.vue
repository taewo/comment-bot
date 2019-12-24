<template>
  <div>
    <h1>
      Test1
    </h1>
    <Test2>
      <template v-slot:header>
        <!-- aaaa -->
      </template>
      <template v-slot:body>
        <!-- bbbbb -->
      </template>
      <template v-slot:footer>
        <!-- ccccc -->
      </template>
    </Test2>
  </div>
</template>
<script>
import Test2 from './Test2'
import Test3 from './Test3'

export default {
  components: {
    Test2, Test3
  },
  computed: {
  },
  data() {
    return {
      visible: false
    }
  },
  methods: {
    toggle() {
      this.visible = true
    }
  }
}
</script>
<style lang=''>

button {
  border: 1px solid gray;
}

</style>
