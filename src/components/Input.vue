<template>
  <div>
    <h2>Form inputs</h2>

    <input type="text" v-model.lazy="name">
    <p>{{ name }}</p>

    <textarea v-model="textarea"></textarea>
    <p>{{ textarea }}</p>

    <label>
      <input type="checkbox" value="instagram" v-model="socials"> Instagram
    </label>
    <label>
      <input type="checkbox" value="vk" v-model="socials"> VK
    </label>
    <label>
      <input type="checkbox" value="facebok" v-model="socials"> Facebook
    </label>
    <hr>
    <ul>
      <li v-for="social in socials" :key=social.id>{{ social }}</li>
    </ul>

    <label>
      <input type="radio" value="instagram" v-model="socials2"> Instagram
    </label>
    <label>
      <input type="radio" value="vk" v-model="socials2"> VK
    </label>
    <label>
      <input type="radio" value="facebok" v-model="socials2"> Facebook
    </label>
    <hr>
    <p>{{ socials2 }}</p>

    <select>
      <option 
        v-for="s in socialList" 
        :key="s.id"
        :selected="s === defaultSocial"
      >{{ s }}</option>
    </select>
    <select v-model="defaultSocial2">
      <option 
        v-for="s in socialList" 
        :key="s.id"
      >{{ s }}</option>
    </select>
    <hr>
    <p>{{ defaultSocial2 }}</p>

    <input type="text" v-model.number="age">
    <p>{{ age }}</p>
    
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: 'Initial state',
        textarea: 'I am initial text',
        socials: ['vk'],
        socials2: 'facebook',
        socialList: ['instagram', 'vk', 'facebook'],
        defaultSocial: 'instagram',
        defaultSocial2: 'instagram',
        age: 20
      }
    },
    watch: {
      age(value) {
        console.log(value)
        console.log(typeof value)
      }
    }
  }
</script>

<style scoped>
  textarea {
    height: 100px;
    width: 400px;
  }

  p {
    white-space: pre;
  }
</style>