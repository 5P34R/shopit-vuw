<template>
   <div class="max-w-sm rounded overflow-hidden shadow-md p-5 mx-4 hover:shadow-xl">
  <img class="object-cover h-80 w-full" :src=image :alt=title>
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">{{title}}</div>
    <p class="text-gray-700 text-base font-semibold">
     {{description}}
    </p>
  </div>
  <div class="text-center text-xl">
    ${{price}}
  </div>
  <div class="px-6 my-4 flex justify-between">
    <span class="inline-block bg-purple-600 rounded-full shadow p-2 px-4 text-md text-white mr-2  hover:bg-purple-900 hover:translate-x-9">Add to cart</span>
    <span class="inline-block bg-purple-600 rounded-full shadow p-2 px-10 text-md text-white mr-2 hover:bg-purple-900 hover:translate-x-9">Buy</span>
  </div>
</div>
</template>

<script>
export default {
    name:"Card",
    props: ['title', 'description', 'image', 'price']
}
</script>