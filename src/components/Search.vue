<template>
  <div class="container">
    <h1>{{ mensaje }}</h1>
    <button @click="changeTitle">Change Title</button>
    <form>
      <button type="submit" @click="printHero">Imprimir Query</button>
    </form>
    <Result :heroes="heroes" />
  </div>
</template>
<script>
import Result from "@/components/Result";

export default {
  name: "Search",
  props: ["mensaje"],
  components: {
    Result,
  },
  data() {
    return {
      url: "https://jsonplaceholder.typicode.com/posts",
      heroes: null,
      message: "Lo Logre!!!!",
      newTitle: "Confirmaado ufff yeahh!",
    };
  },
  methods: {
    printHero(e) {
      e.preventDefault();
      fetch(this.url)
        .then((res) => res.json())
        .then((res) => (this.heroes = res))
        .catch((err) => console.log(err));
    },
    changeTitle() {
      this.$emit("changeTitle", this.newTitle);
    },
  },
};
</script>
<style lang="scss">
.container {
  width: 100%;
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  button {
    width: 50%;
    height: 30px;
    border-radius: 20px;
    border: 1px solid #ccc;
    padding: 2px 10px;
    margin-top: 10px;
  }
}
</style>
