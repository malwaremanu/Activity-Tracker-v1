<template>
  <div>
    <div
      v-for="d in projects"
      :key="d" @click="view_project = d"
      class="cursor-pointer"
    >
      <div class="flex items-center justify-between bg-white/50 hover:bg-blue-50/20 hover:shadow-xl px-4 py-2 hover:bg-blue-200">
        <div class="flex items-center gap-2">
          <div class="rounded-full bg-red-700 px-4 py-2 text-xs text-white"> {{ d.project_code }} </div>
          <div class="px-2 text-left">
            <div class="font-semibold">{{ d.title }}</div>
            <div class="text-xs">{{ d.date }}</div>
          </div>
        </div>

        <div>
          <div class="min-w-8 rounded-full bg-white p-2 text-xs font-bold shadow-lg">250</div>
        </div>
      </div>


    </div>
  </div>
</template>

<script>
export default {
  props: ['projects'],
}
</script>
