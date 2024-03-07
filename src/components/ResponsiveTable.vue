<template>
  <div class="px-4 sm:px-6 lg:px-8">
    <div class="-mx-4 sm:-mx-0">
      <table class="min-w-full divide-y divide-gray-300">
        <thead>
          <tr>
            <th
              v-for="column in columnDefs"
              :key="column.ref"
              :class="column.class"
              scope="col"
            >
              {{ column.name }}
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="row in tableData" :key="row.id">
            <td
              v-for="column in columnDefs"
              :key="column.ref"
              :class="column.cellClass"
            >
              <!-- Check for a named slot corresponding to this column -->
              <template v-if="$slots[column.ref]">
                <!-- Use the slot with dynamic content -->
                <slot :name="column.ref" :row="row"></slot>
              </template>
              <template v-else>
                <!-- Fallback to default rendering -->
                {{ row[column.ref] }}
              </template>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script setup>
defineProps({
  columnDefs: {
    type: Array,
    default: () => [],
  },
  tableData: {
    type: Array,
    default: () => [],
  },
});
</script>
