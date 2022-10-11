<template>
  <div class="grid grid-cols-12 min-h-screen select-none">
    <div class="col-span-1 bg-black text-white text-center">
      <div class="mt-5">
        Activity<br />
        <span class="font-semibold"> Tracker </span>
      </div>
    </div>

    <div class="col-span-4 bg-blue-100">
      <Projs :projects="projects" />
    </div>

    <div class="col-span-7"></div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      count: 0,
      projects: [
        {
          title: 'SBI Bank',
          project_code: '2134',
          comments: '',
          date: '22/09/2022',
        },
        {
          title: 'Sample Project',
          project_code: '5614',
          comments: '',
          date: '23/09/2022',
        },
        {
          title: 'PNB Bank',
          project_code: '3145',
          comments: '',
          date: '24/09/2022',
        },
      ],
      data: [
        {
          status: 'closed',
          activity_message: 'this is a sample ',
          comments: [
            { author: 'Anubhav Sinha', msg: 'sample comment', time: '3hr ago' },
            { author: 'Pritam', msg: 'sample comment', time: '3hr ago' },
            { author: 'Sonu', msg: 'sample comment', time: '3hr ago' },
          ],
        },
        {
          status: 'closed',
          activity_message: 'this is a another sample ',
          comments: [],
        },
      ],
    }
  },
}
</script>
