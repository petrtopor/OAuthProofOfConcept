<template lang="pug">
  span {{keyField}}  -  {{valueField}}<br>
</template>

<script>
export default {
  name: 'DataField',
  props: {
    keyField: String,
    valueField: String
  }
}
</script>

