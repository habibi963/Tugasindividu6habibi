<script>
export default {
  data(){
    return {
      datasensor: "60",
      datasensor2: "80",
    };
  },
  created() {
    //this.getData();
  },
  methods: {
    async getData() {
      const data = await fetch("http://localhost:83/sensor1")
      const datajson = await data.json()
      this.datasensor = datajson.sensor1
    }
  }
}
</script>

<template>
  <div>
    hello {{ datasensor }}
    <button @click="getData" class="bg-orange-400 p-5">Ambil data</button>
  </div>
</template>

