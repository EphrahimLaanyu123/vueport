<template>
  <div class="form-container">
    <form @submit.prevent="SendMessage" class="form-box">
      <div class="form-group">
        <label for="name">Username</label>
        <input type="text" id="name" v-model="formData.name">
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="text" id="email" v-model="formData.email">
      </div>
      <div class="form-group">
        <label for="message">Message</label>
        <input type="text" id="message" v-model="formData.message">
      </div>
      <button>Send message</button>
    </form>
    <div v-if="responseMessage" class="response">{{ responseMessage }}</div>
    <div v-if="errorMessage" class="error">{{ errorMessage }}</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'CreatePost',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      },
      responseMessage: '',
      errorMessage: ''
    };
  },
  methods: {
    SendMessage() {
      axios.post('https://putsreq.com/rwacIEok4pufas6fY7T8', this.formData)
        .then(response => {
          console.log('Response:', response.json);
          this.responseMessage = response.data.message;
        })
        .catch(error => {
          console.error('Error:', error);
          if (error.response) {
            console.error('Response data:', error.response.data);
          } else if (error.request) {
            console.error('Request data:', error.request);
          } else {
            console.error('Error message:', error.message);
          }
        });
    }
  }
};
</script>

<style>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
}



.form-group {
  margin-bottom: 15px;
}



input[type="text"] {
  width: 100%;
  padding: 10px;
  background: black;
  border: 1px solid white;
  border-radius: 5px;
  color: white;
}

button {
  padding: 10px 20px;
  background: #4CAF50;
  border: none;
  border-radius: 5px;
  color: white;
  cursor: pointer;
}

button:hover {
  background: green;
}

.response {
  color: green;
  margin-top: 10px;
}

.error {
  color: red;
  margin-top: 10px;
}
</style>
