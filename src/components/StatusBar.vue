<template>
  <div class="status-bar" v-if="isAuthenticated">
    <p>Công việc đã làm xong</p>
    <ul>
      <li v-for="todo in doneTodos" :key="todo.id">
        {{ todo.title }}
      </li>
    </ul>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "StatusBar",
  computed: mapGetters(["doneTodos", "isAuthenticated"]),
};
</script>

<style>
.status-bar {
  padding: 12px 8px;
  text-align: center;
  background: rgb(240, 240, 240);
  color: black;
}

.status-bar p {
  font-weight: 600;
  font-size: 1.1rem;
  background: rgb(4, 8, 233);
  color: rgb(255, 255, 255);
  padding: 12px 0;
  margin: 4px 62px;
  border-radius: 10px;
}

.status-bar li {
  list-style: none;
  font-size: 1.1rem;
  text-align: center;
  padding-top: 12px;
}
</style>
