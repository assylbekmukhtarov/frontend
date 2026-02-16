<script >
export default {
  data() {
    return {
      info: 'Hello World',
      someInfo: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas, doloremque."
  }
}
,
  methods: {
    userData(word = "John Doe") {
      this.someInfo = "User data updated!"
      this.info = "User Name: " + word
    }
    
  }
  
}

</script>

<template>
 <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>
  <button @click="userData()" @mouseenter="info = 'Mouse Hovered!'">Change Info</button>
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
