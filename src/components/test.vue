<template>
  <div class="px-4 sm:px-6 lg:px-8">
    <div class="-mx-4 sm:-mx-0">
      <table class="min-w-full divide-y divide-gray-300">
        <thead>
          <tr>
            <th
              scope="col"
              class="
                py-3.5
                pl-4
                pr-3
                text-left text-sm
                font-semibold
                text-gray-900
                sm:pl-0
              "
            >
              Name
            </th>
            <th
              scope="col"
              class="
                hidden
                px-3
                py-3.5
                text-left text-sm
                font-semibold
                text-gray-900
                lg:table-cell
              "
            >
              Title
            </th>
            <th
              scope="col"
              class="
                hidden
                px-3
                py-3.5
                text-left text-sm
                font-semibold
                text-gray-900
                sm:table-cell
              "
            >
              Email
            </th>
            <th
              scope="col"
              class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"
            >
              Role
            </th>
            <th scope="col" class="relative py-3.5 pl-3 pr-4 sm:pr-0">
              <span class="sr-only">Edit</span>
            </th>
          </tr>
        </thead>
        <tbody class="divide-y divide-gray-200 bg-white">
          <tr v-for="person in people" :key="person.email">
            <td
              class="
                w-full
                max-w-0
                py-4
                pl-4
                pr-3
                text-sm
                font-medium
                text-gray-900
                sm:w-auto sm:max-w-none sm:pl-0
              "
            >
              {{ person.name }}
              <dl class="font-normal lg:hidden">
                <dt class="sr-only">Title</dt>
                <dd class="mt-1 truncate text-gray-700">
                  {{ person.title }}
                </dd>
                <dt class="sr-only sm:hidden">Email</dt>
                <dd class="mt-1 truncate text-gray-500 sm:hidden">
                  {{ person.email }}
                </dd>
              </dl>
            </td>
            <td class="hidden px-3 py-4 text-sm text-gray-500 lg:table-cell">
              {{ person.title }}
            </td>
            <td class="hidden px-3 py-4 text-sm text-gray-500 sm:table-cell">
              {{ person.email }}
            </td>
            <td class="px-3 py-4 text-sm text-gray-500">{{ person.role }}</td>
            <td class="py-4 pl-3 pr-4 text-right text-sm font-medium sm:pr-0">
              <a href="#" class="text-indigo-600 hover:text-indigo-900"
                >Edit<span class="sr-only">, {{ person.name }}</span></a
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script setup>
const people = [
  {
    name: 'Sushil Singh',
    title: 'Front-end Developer',
    email: 'sushil.singh@example.com',
    role: 'Member',
  },
];
</script>
