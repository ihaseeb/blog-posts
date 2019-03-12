<template>
  <h2
    v-bind="$attrs"
    v-on="$listeners"
    class="subheading text-uppercase font-weight-medium mb-3">
    <slot/>
  </h2>
</template>
<script>
export default {
  name: 'BaseSubheading',
  inheritAttrs: false
}
</script>
