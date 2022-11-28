<template>
  <form @submit="onSubmit">
    <input
      type="text"
      v-model="title"
      placeholder="Thêm công việc mới..."
      class="input-text"
    />
    <input type="submit" value="+ Thêm" />
  </form>
</template>

<script>
import { mapActions } from "vuex";
import { v4 as uuidv4 } from "uuid";

export default {
  name: "TodoForm",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]), // addTodo() === this.$store.dispatch('addTodo')
    onSubmit(event) {
      event.preventDefault();
      // console.log(this.title)
      this.addTodo({
        id: uuidv4(),
        title: this.title,
        completed: false,
      });
      this.title = "";
    },
  },
};
</script>

<style>
form {
  padding: 10px;
}

input[type="text"] {
  width: 100%;
  box-sizing: border-box;
  padding: 10px;
  margin: 6px 0;
  border: 1px solid #888;
  line-clamp: none;
  font-size: 1rem;
}

input[type="submit"] {
  margin: 10px auto;
  padding: 10px 22px;
  border-radius: 10px;
  border: 0;
  font-size: 1.1rem;
  display: block;
  color: #fff;
  background: rgb(24, 223, 6);
  cursor: pointer;
}

input[type="submit"]:hover {
  background: rgba(24, 223, 6, 0.527);
}
</style>
