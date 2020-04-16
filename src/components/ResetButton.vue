<template>
  <div class="reset-button" @click="sendResetSignal">Reset</div>
</template>

<script lang="ts">
import { Component, Emit, Vue } from 'vue-property-decorator';

@Component
export default class ResetButton extends Vue {
  private sendResetSignal() {
    this.$root.$emit('reset');
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.reset-button {
    width: 50px;
    height: 30px;
    background-color: red;
    color: black;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    font-size: 10px;
    margin: 3px;
}
</style>
