<template>
<div>
        <div class="text-2xl font-semibold px-6 pt-3">{{ project }} </div>
        <div
          class="w-7/8 m-8 select-none rounded-lg border-green-600 bg-white p-6 text-left">
          <div class="flex items-center justify-between">
            <div class="flex items-center gap-3">
              <div class="flex items-center gap-2 text-lg font-semibold">
                <div class="h-2 w-2 rounded-full bg-green-600">&nbsp</div>
                Manupal Choudhary
              </div>
              <div class="text-gray-400 text-xs">3h ago</div>
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
            this key is shared with post edp.
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
              5
            </div>

            <div></div>
          </div>

          <div class="grid gap-2">
            <div class="text-sm p-4 py-2 border rounded-md">
              <div class="flex items-center gap-3">
                <div class="flex items-center gap-2 font-semibold">
                  Anubhav Sinha
                </div>
                <div class="text-xs text-gray-400">2h ago</div>
              </div>
              <div>
                asdasas dasdasdwa rgsergdf stdbfgbyhf sdfgsdfgsdfgdfgsdfg
                dfgsdfgssfdgsdfg sdfgsdf gs dfgsdfgsdfgsdfg dfg
              </div>
            </div>
             <div class="text-sm p-4 py-2 border rounded-md">
              <div class="flex items-center gap-3">
                <div class="flex items-center gap-2 font-semibold">
                  Anubhav Sinha
                </div>
                <div class="text-xs text-gray-400">2h ago</div>
              </div>
              <div>
                asdasas dasdasdwa rgsergdf stdbfgbyhf sdfgsdfgsdfgdfgsdfg
                dfgsdfgssfdgsdfg sdfgsdf gs dfgsdfgsdfgsdfg dfg
              </div>
            </div>
          </div>          
        </div>
</div>
</template>

<script>
export default {
  props: ['project'],
  data(){
    return {
      adata : {
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
                  content : 'there is some update on this above matter.'
                },
                {
                  author : 'Pritam',
                  content : 'there is some update on this above matter.'
                },
                {
                  author : 'Anubhav',
                  content : 'there is some update on this above matter.'
                }
              ],
            }
          ],
          date: '22/09/2022',
        }
    }
  }
}
</script>
