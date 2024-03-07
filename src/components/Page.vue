<template>
  <div class="">
    <div class="max-w-3xl mx-auto">
      <h1 class="text-xl p-4">Responsive Table (stacked columns)</h1>
      <h3 class="px-4">HTML Version</h3>
      <Test />
      <h3 class="p-4">Component Version</h3>
      <ResponsiveTable :columnDefs="columnDefs" :tableData="people">
        <template #name="{row}">
          <div>{{ row.name }}</div>
        </template>
        <template #name-mobile="{row}">
          <dt class="sr-only">Title</dt>
          <dd class="mt-1 truncate text-gray-700">{{ row.title }}</dd>
          <dt class="sr-only sm:hidden">Title</dt>
          <dd class="mt-1 truncate text-gray-700 sm:hidden">{{ row.email }}</dd>
        </template>
        <template #edit="{ row }">
          <button
            @click="editAction(row)"
            class="text-indigo-600 hover:text-indigo-900"
          >
            Edit
          </button>
        </template>
      </ResponsiveTable>
    </div>
  </div>
</template>

<script setup>
import ResponsiveTable from './ResponsiveTable.vue';
import BaseButton from './BaseButton.vue';
import Test from './test.vue';
const columnDefs = [
  {
    name: 'Name',
    ref: 'name',
    class:
      'py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-0',
    cellClass:
      'w-full max-w-0 py-4 pl-4 pr-3 text-sm font-medium text-gray-900 sm:w-auto sm:max-w-none sm:pl-0',
  },
  {
    name: 'Title',
    ref: 'title',
    class:
      'hidden px-3 py-3.5 text-left text-sm font-semibold text-gray-900 lg:table-cell',
    cellClass: 'hidden px-3 py-4 text-sm text-gray-500 lg:table-cell',
  },
  {
    name: 'Email',
    ref: 'email',
    class:
      'hidden px-3 py-3.5 text-left text-sm font-semibold text-gray-900 sm:table-cell',
    cellClass: 'hidden px-3 py-4 text-sm text-gray-500 sm:table-cell',
  },
  {
    name: 'Role',
    ref: 'role',
    class: 'px-3 py-3.5 text-left text-sm font-semibold text-gray-900',
    cellClass: 'px-3 py-4 text-sm text-gray-500',
  },
  {
    name: 'Edit',
    ref: 'edit',
    class: 'relative py-3.5 pl-3 pr-4 sm:pr-0',
    cellClass: 'py-4 pl-3 pr-4 text-right text-sm font-medium sm:pr-0',
  },
];
const people = [
  {
    name: 'Sushil Singh',
    title: 'Front-end Developer',
    email: 'sushil.singh@example.com',
    role: 'Member',
    edit: '',
  },
];

const editAction = (row) => {
  console.log('Editing', row);
};
</script>
