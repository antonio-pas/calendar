<script setup lang='ts'>
const props = defineProps<{
  type: 'primary' | 'secondary'
}>()
</script>

<button :class="{props.type}">
<slot></slot>
</button>

<style scoped>
button {
  padding: var(--p1);
  border: none;
  border-radius: var(--br2);
  font-size: 1rem;
}
.primary {
  background-color: var(--pri);
  color: var(--onPri);
}
.secondary {
  background-color: var(--priCon);
  color: var(--onPriCon);
}
</style>