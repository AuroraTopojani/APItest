<template>

<button :disabled="disable"
         @click="GetAPI">GET YOUR API</button>

</template>

<script>

export default {
  name: 'IndexPage',
  data(){
    return {
      disable:false,
    }
  },
 async created(){
    await this.GetAPI
 },
  methods: {
    async GetAPI() {

      try {
        this.disable=true;
        const data = await this.$axios.$get('/api/v3/ticker/24hr');
        console.log(data)
      }
      catch (e) {
           console.log(e)
      }
    }
  }


}

</script>
