<template>
  <div class="container mx-20">
    <Card title="Its my heading" description="Lorel ip"/>
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
      data: []
    }
  },
  components: {
    Card
  },
  methods:{
    async getData(){
      await axios.get(`http://127.0.0.1:8000/`).then((res) => {
        res.data.map((e) => {
          this.data.append(e)
        })
      })
    }
  },
  mounted(){
    this.getData()
  }
}
</script>
