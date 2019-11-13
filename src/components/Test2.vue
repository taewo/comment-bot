<template>
  <div style="border:2px solid blue">
    <!-- <input :value="value123" @input="$emit('update:value123', $event.target.value)" type="text"> -->
    {{ value123}}
  </div>
</template>
<script>
export default {
  props: ['value123']
}
</script>
<style lang=''>

</style>
