<template>
  <div>   
    <img alt="Peaks logo" src="./assets/PeaksTextBlack.png">
    <div class="container">
      <button class="buttons" @click="showNotification">Notification button</button>
      <button class="buttons" @click="showNotification2">Notification2 button</button>
      <!-- Different types of push-notifications to notify the user -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mm:  Math.floor(Math.random()*100), //can be interchanged with a variable that shows live data
      stresspeaks:  Math.floor(Math.random()*10), //amount of measured "Peaks" which pass the threshold set by the user
      timeslot: 'Middag', //split the day in different timeslots (morning, afternoon, evening, midnight)
      user: 'Dennis',
    }
  },
  methods: {
    showNotification() {
      const notification = new Notification("New message from Peaks!", {
        body: "Hey " + this.user + "!\nIk zag dat je een stresslevel van " + this.mm + " had. Zou je mij daar meer info over kunnen geven?",
        icon: "https://i.imgur.com/DGlDio3.png",
      });
      notification.onclick = function(event) {
        event.preventDefault();
        window.open('https://www.google.nl/', '_blank') //action which takes place after clicking on the notification
      }
    },
    showNotification2() {
      const notification = new Notification("New message from Peaks!", {
        body: "Hey " + this.user + "!\nIk zag dat je deze " + 'middag' + ' ' + this.stresspeaks + " stresspieken had. Zou je mij daar meer info over kunnen geven?",
        icon: "https://i.imgur.com/DGlDio3.png",
      });
      notification.onclick = function(event) {
        event.preventDefault();
        window.open('https://www.google.nl/', '_blank')
      }
    },
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
.buttons {
  margin: 10px;
}
</style>
