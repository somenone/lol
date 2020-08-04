<template>
  <div>
    <router-link to="/test">To a test page</router-link>
    <button @click="toB">To a test page</button>

    
  </div>
</template>

<script>
export default {
  methods: {
    async test(){
      console.log(await this.$http.get('http://111.229.35.35:3001/'))
    },
    toB(){
      let newwindow = this.$electron.BrowserWindow({
        width: 1000,
        height: 1000
      })
      newwindow.loadURL('/')
      newwindow.on("close", ()=>{
        newwindow = null
      })
      console.log(newwindow);
    }
  },
  mounted(){
    this.test()
  }
}
</script>

<style scoped>

</style>