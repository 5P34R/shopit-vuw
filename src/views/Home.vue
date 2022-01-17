<template>
  <div class="container mx-auto">
    <h1 class="text-center text-3xl uppercase text-gray-700 my-10">Latest Products</h1>
    <div class="flex p-5">
      <div v-for="product in data" :key="product.id">
       <Card :title=product.title :description=product.description :image=product.photo_url :price=product.price />
     </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
// @ is an alias to /src
import Card from '../components/Card.vue'

export default {
  name: 'Home',
  data(){
    return {
      data:[]
    }
  },
  components: {
    Card
  },
  methods:{
    async getData(){
      await axios.get(`http://127.0.0.1:8000/`).then((res) => {
        res.data.map((e) => {
          this.data.push(e)
        })
      })
    }
  },
  mounted(){
    this.getData()
  }
}
</script>
