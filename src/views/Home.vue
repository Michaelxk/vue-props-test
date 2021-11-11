<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Search :mensaje="mensaje" @changeTitle="updateTitle" />
  </div>
</template>

<script>
// @ is an alias to /src
import Search from "@/components/Search";

export default {
  name: "Home",
  components: {
    Search,
  },
  data() {
    return {
      mensaje: "Lo logre!!!!!",
    };
  },
  methods: {
    updateTitle(payload) {
      this.mensaje = payload;
    },
  },
};
</script>
