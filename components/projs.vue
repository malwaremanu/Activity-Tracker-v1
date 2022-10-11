<template>
  <div>
    <div class="grid mt-4 py-4 mb-2 justify-items-center">
      <div class="flex items-center gap-4">
        <input
          placeholder="Project Code or Name"
          class="px-5 py-3 w-90 col-span-3 bg-white active:shadow-xl decoration-none shadow-lg rounded-full"
        />
        <div class="px-5 py-3 cursor-pointer shadow-lg hover:shadow-xl bg-white rounded-full">Search</div>
      </div>
    </div>

    <div class="px-4 py-2 pl-4 font-semibold">
      Projects ({{ projects.length }})
    </div>

    <div
      v-for="d in projects"
      :key="d"
      class="flex items-center cursor-pointer justify-between px-5 py-4 hover:bg-blue-200 hover:rounded-r-full"
    >
      <div class="flex items-center gap-3">
        <div class="bg-red-800 rounded-full px-4 py-2 text-white">
          {{ d.project_code }}
        </div>

        <div>
          <div class="text-md">{{ d.title }}</div>
          <div class="text-xs">{{ d.date }}</div>
        </div>
      </div>

      <div class="bg-white px-4 py-2 rounded-full text-sm">23</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['projects'],
}
</script>
