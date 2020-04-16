<template>
  <div class="click-count-button" @click="addOne">
      {{ clickCount }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class ClickCountButton extends Vue {
  private clickCount = 0;

  public mounted() {
    this.$root.$on('reset', this.reset);
  }

  public reset() {
    this.clickCount = 0;
  }

  private addOne() {
    this.clickCount += 1;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.click-count-button {
    width: 50px;
    height: 30px;
    background-color: aquamarine;
    color: black;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    font-size: 10px;
    margin: 3px;
}
</style>
