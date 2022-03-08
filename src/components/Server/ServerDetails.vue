<template>
  <div class="col-xs-12 col-sm-6" v-if="Object.keys(server).length === 0">
    <p>Sunucu Bilgisi güncel değil!!</p>
  </div>
  <div class="col-xs-12 col-sm-6" v-else>
    <p>Sunucu Bilgisi güncel değil!!</p>
    <h3>Sunucu #{{ server.id }}</h3>
    <h3>Sunucu Durumu :{{ server.status }}</h3>
    <button class="btn btn-xs btn-primary" @click="changeStatus">
      Durumu Değiştir
    </button>
  </div>
</template>
<script>
import { eventBus } from "../../main.js";
export default {
  data: function () {
    return { server: {} };
  },
  created: function () {
    eventBus.$on("serverDataSend", (data) => {
      this.server = data;
    });
  },
  methods: {
    changeStatus: function () {
      this.server.status = "Normal";
    },
  },
};
</script>