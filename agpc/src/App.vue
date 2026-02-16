<script >
export default {
  data() {
    return {
      info: 'Hello World',
      someInfo: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas, doloremque.",
      some:{
        name: "John Doe",
        age: 30,
        city: "New York"
      }
    }
  }
}
</script>

<template>
 <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>
  <p class="info">Name: {{ some.name }}</p>
  <p class="info">Age: {{ some.age }}</p>
  <p class="info">City: {{ some.city }}</p>


</template>

<style scoped>
h3 {
 font-weight: lighter;

}
p{
  color: red;
}
.info{
  color: blue;
}
</style>
