<template>
    <div class="picker-main"> 
        <h4 class="header">Select event theme</h4>
        <div class="color-picker">
          <div class="color" v-for="(theme, index) in colors" :key="index" @click="selectColor(theme)" :class="{selected: color === theme, [theme]: theme}"></div>
        </div>
      </div>
</template>

<script>
    export default {
      name: 'ColorPicker',
      props: ['color'],
      data(){
        return {
          colors: ['red', 'green', 'blue', 'orange']
        }
      },
      methods: {
        selectColor(color){
          this.$emit('colorPicked', color);
        }
      }
    }
</script>

<style scoped>

</style>