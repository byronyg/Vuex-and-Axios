<template>
  <div>
      <h3>Add Todo</h3>
      <div class="add">
          <form @submit="onSubmit">
              <input type="text" v-model="title" placeholder="Add Todo...">
              <input type="submit" value="Submit">
          </form>
      </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
    name: 'Add Todo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        ...mapActions(['addTodo']),
        onSubmit(e) {
            e.preventDefault();
            this.addTodo(this.title); 
        }
    }

}
</script>

<style scoped>
form {
    display: flex;
}
input[type="text"] {
    flex: 10;
    padding: 10px;
    border: 1px solid #8B5CF6;
    outline: 0;
}
input[type="submit"] {
    flex: 2;
    background: #8B5CF6;
    color: #fff;
    border: 1px #8B5CF6 solid;
    cursor: pointer;
}

</style>