<template>
  <li
    :id= name
    v-for="name in todos"
    :key= name
    class="d-md-flex justify-content-between list-group-item col-sm-12"
  >
    <span class = "name-sizing "> {{ name }} </span>
    <span class="btn-section col-sm-12 col-md-6 d-flex justify-content-around float-left">
      <Button btntext="Send to Last"
      class="btn btn-warning d-block"
      @click=sendlast()
      />
      
      <Button btntext="Mark as Done"
      class="btn btn-success d-block" 
      />
    </span>
  </li>
</template>

<script>
import Button from "./Button.vue"

export default {
  name: "Arrtest",
  components: {
    Button,
  },
  props: {
    name: String,
  },

  created() {
    console.log(this.todos);
    console.log(this.todos.length);
  },

  data() {
    return {
      todos: [
        10, 11, 12, 13, 14, 15, 16
      ],
    };
  },

  // computed: {
    methods: {
      sendlast() {
          console.log("send to last action initiated");
          console.log(this.todos.length);
      },
    },
  // }
 
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.name-sizing {
  font-size: 1.5rem;
}

@media screen and (max-width: 460px) {
  .btn {
    margin-top: 10px;
    padding: 0.175rem .55rem;
  }

}

</style>
