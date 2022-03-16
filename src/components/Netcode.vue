<template>
  <li
    :id= name.id
    v-for="name in todos"
    :key= name.id
    class="d-md-flex justify-content-between list-group-item col-sm-12"
    @mouseover="mouseover(name)"
    @mouseout="mouseout(name)"
  >
    <span class = "name-sizing "> {{ name.title }} </span>
    <span class="btn-section col-sm-12 col-md-6 d-flex justify-content-around float-left">
      <Button btntext="Send to Last"
      class="btn btn-warning"
      :class = "name.mousestatus ? 'd-block' : 'd-none'"
      />
      
      <Button btntext="Mark as Done"
      class="btn btn-success" 
      :class = "name.mousestatus ? 'd-block' : 'd-none'"
      />
    </span>
  </li>
</template>

<script>
import Button from "./Button.vue"

export default {
  name: "Netcode",
  components: {
    Button,
  },
  props: {
    name: String,
  },

  created() {
    this.mousestatus = false;
  },

  data() {
    return {
      mousestatus: Boolean,
      todos: [
        {
          id: 1,
          title: "Do the dishes",
        },
        {
          id: 2,
          title: "Take out the trash",
        },
        {
          id: 3,
          title: "Mow the lawn",
        },
        {
          id: 4,
          title: "Bring Grocery",
        },
        {
          id: 5,
          title: "Cut the vegetables",
        },
        {
          id: 6,
          title: "Bake the dessert",
        }
      ],
    };
  },

  // computed: {
    methods: {
      mouseover(name) {
        name.mousestatus = true;
      },

      mouseout(name) {
        name.mousestatus = false;
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

  .btn-section {
    /* float: left; */
  }
}

</style>
