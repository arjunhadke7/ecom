<template>
  <li
    :id= name.id
    v-for="name in todos"
    :key= name.id
    class="d-flex justify-content-between list-group-item"
    @mouseover="mouseover(name)"
    @mouseout="mouseout(name)"
  >
    {{ name.title }}
    <div class="col-sm-12 col-md-6 d-block">
      <button class="btn btn-warning" 
      :class = "name.mousestatus ? 'd-block' : 'd-none'"
      >
        Send to Last
      </button>
      <button class="btn btn-success" 
      :class = "name.mousestatus ? 'd-block' : 'd-none'"
      >
        Mark as Done
      </button>
    </div>
  </li>
</template>

<script>

export default {
  name: "ListingComp",
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
</style>
