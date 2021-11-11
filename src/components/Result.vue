<template>
  <div id="result">
    <div v-for="hero in heroes" :key="hero.id">
      <h3>{{ hero.title }}</h3>
      <h5>{{ hero.body }}</h5>
      <h6>{{ hero.id }}</h6>
      <button @click="deleteHero">delete</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "Result",
  props: ["heroes"],
  data: () => ({}),
  methods: {
    deleteHero(e) {
      e.currentTarget.parentNode.remove();
    },
  },
};
</script>

<style lang="css">
button {
  width: 50%;
  height: 30px;
  border-radius: 20px;
  border: 1px solid #ccc;
  padding: 2px 10px;
  margin-top: 10px;
}
</style>
