<template>
  <div>   
    <img alt="Peaks logo" src="./assets/PeaksTextBlack.png">
    <div class="container">
      <button @click="showNotification">Notification button</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mm: 0,
    }
  },
  mounted() {
  // this.checkperm()
},
  methods: {
    showNotification() {
      this.mm = Math.floor(Math.random()*100);
      new Notification("New message from Peaks!", {
        body: "Hey Dennis!\nIk zag dat je een stresslevel van " + this.mm + " Hebt",
        icon: "https://i.imgur.com/DGlDio3.png",
      });
      console.log(Notification.permission)
    },
    // checkperm() {
    //   if (Notification.permission === "granted") {
    //     showNotification();
    //     } else if (Notification.permission !== "denied") {
    //     Notification.requestPermission().then(permission => {
    //       if (permission === "granted") {
    //         showNotification();
    //       }
    //     })
    //   }
    // },
  }  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  text-align: center;
  margin-top: 100px;
}
</style>
