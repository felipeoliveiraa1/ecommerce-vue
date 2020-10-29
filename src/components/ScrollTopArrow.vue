<template>
  <ScrollTopComponent>
    <div class="fundo">
      <a class="btn btn-light arrow up"></a>
    </div>
  </ScrollTopComponent>
</template>

<script>
import ScrollTopComponent from './scrollTop'
export default {
  components: {
    ScrollTopComponent
  }
}
</script>

<style scoped>

.fundo{
  position: relative;
  width: 35px;
  height: 35px;
  border:1px solid black;
  border-radius:4px;
  background-color: rgba(0, 0, 0, 0.55);
}

.arrow {
  border: solid white;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 8px;
  margin-top: 10px;
}

.up {
  transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
}
</style>