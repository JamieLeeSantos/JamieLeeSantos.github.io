<template>
  <div class="horizontal">
    <div class="asansijems">
      <h1>AsansiJems.com</h1>
      <h2>LT: {{timestamp}}</h2>
      <h2>Jems Delfy: <span style="padding-right:2em;"></span><svg xmlns="http://www.w3.org/2000/svg" width="16" height="1em" fill="currentColor" class="bi bi-chat-square-dots" viewBox="0 0 16 16"><path d="M14 1a1 1 0 0 1 1 1v8a1 1 0 0 1-1 1h-2.5a2 2 0 0 0-1.6.8L8 14.333 6.1 11.8a2 2 0 0 0-1.6-.8H2a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1h12zM2 0a2 2 0 0 0-2 2v8a2 2 0 0 0 2 2h2.5a1 1 0 0 1 .8.4l1.9 2.533a1 1 0 0 0 1.6 0l1.9-2.533a1 1 0 0 1 .8-.4H14a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2z"/><path d="M5 6a1 1 0 1 1-2 0 1 1 0 0 1 2 0zm4 0a1 1 0 1 1-2 0 1 1 0 0 1 2 0zm4 0a1 1 0 1 1-2 0 1 1 0 0 1 2 0z"/></svg>
      <img src="/assets/images/bard.png" style="height: 1em;">
      <img src="@/assets/images/flames.png" style="height: 1em;">
      90 {{locations[this.locno]}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Asansijems',
  data() {
    return {
      timestamp: '',
      locno: '',
      locations: [
        'Eureka Pagos',
        'Eureka Anemos',
        'Eureka Hydatos',
        'Eureka Pyros',
        'Bozjan Southern Front',
        'Zadnor',
        "Private Estate (Snapper Fibbs)"
      ]
    }
  },
  created() {
    setInterval(() => {
      this.getNow();
    }, 1000),
    this.locno = this.getLocation(7)
    
  },
  methods: {
    getNow: function() {
      const today = new Date();
      const h = ('0'+today.getHours()).slice(-2);
      const m = ('0'+today.getMinutes()).slice(-2);
      const s = ('0'+today.getSeconds()).slice(-2);
      const time = h + ":" + m + ":" + s;
      const dateTime = time;
      this.timestamp = dateTime;
    },
    getLocation: function(max) {
      return Math.floor(Math.random() * max);
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.asansijems {
  font-family: 'Times New Roman', Times, serif;
}
</style>
