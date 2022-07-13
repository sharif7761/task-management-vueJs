<template>
  <button @click="onClickHandler()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'ButtonComp',
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClickHandler(){
        console.log('onClickHandler()');
    }
  }
}
</script>