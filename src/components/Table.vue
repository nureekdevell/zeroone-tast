<script setup>
defineProps({
  data: Array,
  columns: Array,
});
</script>

<template>
  <table class="">
    <tr class="text-left bg-gray-200">
      <th v-for="column of columns" :key="column" class="px-4 py-2">
        {{ column }}
      </th>
    </tr>

    <tr
      v-for="(item, id) of data"
      :key="id"
      class="border-b border-b-gray-200 bg-white hover:bg-gray-100"
    >
      <td class="py-2.5 px-4 text-blue-500">
        {{ item.name }}
      </td>
      <td class="py-2.5 px-4">{{ item.age }}</td>
      <td class="py-2.5 px-4">{{ item.address }}</td>
      <td class="py-2.5 px-4 flex gap-2">
        <span
          v-for="tag of item.tags"
          :key="tag"
          :class="`badge badge-${tag.toLowerCase()}`"
        >
          {{ tag }}
        </span>
      </td>
      <td class="py-2.5 px-4">
        <ul class="flex space-x-2.5 text-blue-500">
          <li
            v-for="link of item.action"
            :key="link"
            class="even:px-2 even:border-l even:border-r even:border-gray-100"
          >
            {{ link }}
          </li>
        </ul>
      </td>
    </tr>
  </table>
</template>

<style>
.badge {
  @apply py-0.5 px-1.5 bg-cyan-100 text-cyan-900 border border-cyan-500;
  @apply rounded-md text-xs;
}

.badge-nice {
  @apply bg-green-100 text-green-900 border-green-500;
}

.badge-developer {
  @apply bg-purple-100 text-purple-900 border-purple-500;
}

.badge-loser {
  @apply bg-red-100 text-red-900 border-red-500;
}
</style>
