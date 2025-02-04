<script> // Options API
export default {
  name: "template",
  data() {
    return {
      name: 'navya',
      status: "active",
      items: ['Dancing', 'Drawing', 'Singing']
    }
  },
  methods:{
toggle(){
  if(this.status=="active") this.status="inactive"
  else if(this.status=="inactive") this.status="overactive"
  else if(this.status=="overactive") this.status="active"

}
  }
}
</script>
<template>
  <h1>hey {{ name }}</h1>
  <p v-if="status == 'active'"> iam here</p>
  <p v-if="status == 'inactive'"> iam hidden</p>
  <p v-if="status =='overactive'">I am some where</p>

  <h2>My hobbies are</h2>
  <ul v-for="item in items" key="item">
    <li>{{ item }}</li>
  </ul>
  <button v-on:click="toggle">click me</button>
</template>
