<template>
  <button @click="onClick">
    <slot></slot>
  </button>
</template>

<script lang="ts">
import { Component, Emit, Prop, Vue } from 'vue-property-decorator';

@Component
export default class MyButton extends Vue {
  @Prop()
  public greet?: string;

  private count: number = 0;

  @Emit()
  public click(count: number) {}

  public onClick() {
    alert(this.greet);
    this.count++;
    this.click(this.count);
  }
}
</script>
