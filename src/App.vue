<script setup>
import TreeCollapse from "./components/TreeCollapse.vue";
import Table from "./components/Table.vue";

// Tree Collapse
const treeList = [
  "Phone",
  ["Samsung", "iPhone", "Redmi", "Pixel"],
  "Notebooks",
  ["Asus ROG", "Ultrabook", "Macbook"],
];

// Table
const tableColumns = ["Name", "Age", "Address", "Tags", "Action"];
const tableData = [
  {
    name: "John Doe",
    age: 32,
    address: "California",
    tags: ["nice", "developer"],
    action: ["invite", "delete", "more"],
  },
  {
    name: "Jane Doe",
    age: 19,
    address: "New York",
    tags: ["loser"],
    action: ["invite", "delete", "more"],
  },
  {
    name: "Nurjahon Dev",
    age: 26,
    address: "Tashkent",
    tags: ["noob", "developer"],
    action: ["invite", "delete", "more"],
  },
];
</script>

<template>
  <main class="container py-10 px-4">
    <div class="flex w-full justify-center">
      <Table :columns="tableColumns" :data="tableData" />
    </div>

    <br />
    <hr />
    <br />

    <div class="bg-gray-100">
      <tree-collapse :items="treeList" />
    </div>
  </main>
</template>
