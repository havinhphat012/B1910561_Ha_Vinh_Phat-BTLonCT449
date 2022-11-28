<template>
  <div class="navbar">
    <h1>Thời gian biểu</h1>
    <ul>
      <li v-if="isAuthenticated">
        Tổng công việc: {{ todos.length }}
        <button @click="TOGGLE_AUTH">Đăng xuất</button>
      </li>
      <button v-else @click="TOGGLE_AUTH">Đăng nhập</button>
    </ul>
  </div>
</template>

<script>
import { mapMutations, mapGetters } from "vuex";

export default {
  name: "Navbar",
  computed: mapGetters(["todos", "isAuthenticated"]),
  methods: mapMutations(["TOGGLE_AUTH"]),
};
</script>

<style>
.navbar {
  padding: 5px;
  text-align: center;
  background: rgb(240, 240, 240);
  color: black;
}

.navbar h1 {
  background: #141414;
  padding: 22px 0;
  color: #fff;
}

.navbar button {
  font-size: 1.2rem;
  font-family: Arial, Helvetica, sans-serif;
  border: none;
  background: #666;
  color: #fff;
  padding: 10px 32px;
  border-radius: 5px;
  font-weight: 700;
  margin-left: 12px;
}

.navbar button:hover {
  background: rgb(14, 208, 214);
  color: rgb(44, 43, 43);
  cursor: pointer;
  font-weight: 700;
}

.navbar li {
  font-size: 1.1rem;
  font-weight: 600;
  color: rgb(5, 74, 165);
}

.navbar ul {
  display: flex;
  justify-content: space-around;
  align-items: center;
  list-style: none;
  padding: 0;
}
</style>
