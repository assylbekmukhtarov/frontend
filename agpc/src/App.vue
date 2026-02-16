<script >
export default {
  data() {
    return {
      users:[],
      error: '',
      userName: 'John Doe',
      userPass: '',
      userEmail: ''

  }
}
,
  methods: {
    sendData() {
      if(this.userName=='' || this.userPass==='' || this.userEmail===''){
        this.error = 'PLEASE FILL ALL FIELDS';
        return;
      }
      this.error = '';

      this.users.push({
        name: this.userName,
        email: this.userEmail,
        password: this.userPass
      });
    }
    
  }
  
}

</script>

<template>
  <input type="text" v-model="userName" placeholder="Enter your name">
  <input type="password" v-model="userPass" placeholder="Enter your password">
  <input type="email" v-model="userEmail" placeholder="Enter your email">
  <p class="error">{{ error }}</p>
  <button @click="sendData()">Submit</button>


  <div v-if="users.length === 0" style="margin-top:20px; font-weight:bold; font-size:18px; text-align:center;">
    NO USERS ADDED YET
  </div>

  <div v-else-if="users.length === 1" style="margin-top:20px; font-weight:bold; font-size:18px; text-align:center;">
    ONLY 1 USER ADDED 
  </div>

  <div v-else style="margin-top:20px; font-weight:bold; font-size:18px; text-align:center;">
    {{ users.length }} USERS ADDED
  </div>

  <div v-for="el,index in users" :key="index" className="users">
    <h3>{{ el.name }}</h3>
    <p><b>Email:</b> {{ el.email }} - <b>Password:</b> {{ el.password }}</p>
  </div>
</template>

<style scoped>
input{
  width:100%;
  padding:10px 12px;
  margin:8px 0;
  border:1px solid #ccc;
  border-radius:8px;
  outline:none;
}

input:focus{
  border-color:#4f46e5;
  box-shadow:0 0 0 3px rgba(79,70,229,.2);
}

button{
  width:100%;
  padding:10px 12px;
  margin-top:10px;
  border:none;
  border-radius:8px;
  background:#4f46e5;
  color:#fff;
  cursor:pointer;
}

button:hover{
  opacity:.9;
}

.users{
  margin-top:20px;
  font-family:Arial, sans-serif;
  font-size:14px;
  flex-direction:column;
  gap:12px;
  width:500px;
  margin:20px auto;
  border:1px solid #ccc;
  border-radius:8px;
  padding:20px;
  background:#f9f9f9;

}

p{
  margin-top:12px;
  padding:10px 12px;
  border:1px dashed #ccc;
  border-radius:8px;
  color:#333;
  word-break:break-word;
}
.error{
  color:red;
  font-weight:bold;
}
</style>
