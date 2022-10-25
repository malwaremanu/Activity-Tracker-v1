<template>
  <div>
<div class="grid min-h-screen grid-cols-12">
<div class="col-span-2">
  <Sidebar />
</div>


  <div class="col-span-4 border bg-indigo-50">
    <Content />

    <div class="mt-4 px-4 py-2 text-xl font-semibold">Projects (32)</div>

    <div class="grid gap-0.5">
       <div
          v-for="d in projects"
          :key="d.uuid" @click="vp = d"
          class="cursor-pointer"
        >
        <div class="flex items-center justify-between bg-white/50 hover:bg-blue-50/20 hover:shadow-xl px-4 py-2 hover:bg-blue-200">
          <div class="flex items-center gap-2">

            <div v-show="d.status"
            class="rounded-full bg-green-700 px-4 py-2 text-xs text-white"> {{ d.project_code }} </div>

            <div v-show="!d.status"
            class="rounded-full bg-red-700 px-4 py-2 text-xs text-white"> {{ d.project_code }} </div>
            
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

  </div>

  <div class="col-span-6">
  {{ vp }}
     <div v-show="vp.title">
        <div class="text-2xl font-semibold px-6 pt-3 flex items-center gap-2"> 
        {{ vp.title }} 
        <span class="text-xs p-1"> {{ vp.date }} </span>
        </div>      
        <div v-for="aa in vp.activity" :key="aa"
          class="w-7/8 m-8 select-none rounded-lg border-green-600 bg-white p-6 text-left">
          <div class="flex items-center justify-between">
            <div class="flex items-center gap-3">
              <div class="flex items-center gap-2 text-lg font-semibold">

                <div v-show="vp.status" class="h-2 w-2 rounded-full bg-green-600">&nbsp</div>
                <div v-show="!vp.status" class="h-2 w-2 rounded-full bg-red-600">&nbsp</div>

                {{ aa.author }}
              </div>
              <div class="text-gray-400 text-xs"> {{ aa.time }} </div>
            </div>
            <div class="flex items-center gap-3">
              <svg
                class="h-5 w-5"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"
                ></path>
              </svg>
              <svg
                class="h-5 w-5"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
                >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M8 11V7a4 4 0 118 0m-4 8v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2z"
                ></path>
              </svg>

              <div class="rounded-full bg-green-400 p-2 text-green-800">
                <svg
                  class="h-5 w-5"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                  >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M3 10h10a8 8 0 018 8v2M3 10l6 6m-6-6l6-6"
                  ></path>
                </svg>
              </div>
            </div>
          </div>

          <div class="flex items-center pl-4 text-gray-600">
            {{ aa.desc }}
          </div>
          <div class="flex items-center gap-2 p-4 pl-4">
            <div
              class="flex cursor-pointer items-center gap-2 rounded-full bg-green-200 px-4 py-2 text-sm text-green-700">
              <svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h10a8 8 0 018 8v2M3 10l6 6m-6-6l6-6"></path>
              </svg>
              Reply
            </div>

            <div class="flex cursor-pointer items-center gap-2 rounded-full bg-yellow-200 px-4 py-2 text-sm text-yellow-700">
              <svg class="h-5 w-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 8h10M7 12h4m1 8l-4-4H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-3l-4 4z"></path>
              </svg>
              {{ aa.comments.length }}
            </div>

            <div></div>
          </div>

          <div class="grid gap-2 ml-10">
            <div v-for="bb in aa.comments" :key="bb" class="text-sm p-4 py-2 border rounded-md">
              <div class="flex items-center gap-3">
                <div class="flex items-center gap-2 font-semibold">
                  {{ bb.author }} 
                </div>
                <div class="text-xs text-gray-400"> 
                  {{ bb.time }} 
                </div>
              </div>
              <div>
                {{ bb.content }}
              </div>
            </div>

            <div class="w-full flex items-center gap-1"> 
              <textarea class="text-sm p-4 py-2 border border-2 rounded-md w-full" placeholder="Type your reply here..."></textarea>
              <button class="px-4 py-2 bg-gray-900 text-white rounded-full text-xs"> Send </button>
            </div>

          </div>  


        </div>
    </div>

    <div v-show="!vp.title" class="grid place-items-center">      
      <div class="text-center font-semibold">
        Please select project first...
      </div>
    </div>

  </div>
</div>

  </div>

</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      count: 0,
      vp : {},
      projects: [
        {
          uuid : 'asdasd2dasd43ftg4zvzsdr43tsdfb7hre5',
          title: 'SBI Bank',
          project_code: '2134',
          activity : [
            {
              author : 'Manupal Choudhary',
              desc : 'The final key is shared with the respective users.',
              time : '3h ago',
              comments: [
                {
                  author : 'Anubhav Sinha',
                  time : '2min ago',
                  content : 'let us discuss this over meeting...'
                },
                {
                  author : 'Pritam', 
                  time : '12min ago',                
                  content : 'no updates so far...'
                },
                {
                  author : 'Anubhav',                  
                  time : 'just now',
                  content : 'there is some update on this above matter. please get in touch with authorised personnel.'
                }
              ],
            }
          ],
          date: '22/09/2022',
          status : true,
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
