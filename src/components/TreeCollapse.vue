<script setup>
const isParentElement = (currentId) => {
  if (Array.isArray(props.items[currentId])) {
    return true;
  }

  return false;
};

const collapseElement = (id) => {
  if (isParentElement(id - 1)) return;

  const domElement = document.querySelector(`ul[data-id=${id}]`);
  if (domElement !== null && domElement !== undefined) return;

  return function () {};
};

const props = defineProps({
  items: { type: Number, default: () => [] },
  idx: { type: Number, default: () => 0 },
});
</script>

<template>
  <ul class="ml-4" :data-id="idx">
    <li v-for="(item, id) of items" :key="id">
      <span
        v-if="typeof item === 'string'"
        :class="['pl-4', isParentElement(id) && 'tree-parent']"
        @click="collapseElement(id + 1)"
      >
        {{ item }}
      </span>

      <tree-collapse v-else :items="item" :idx="id" />
    </li>
  </ul>
</template>

<style>
.tree-parent {
}
</style>
