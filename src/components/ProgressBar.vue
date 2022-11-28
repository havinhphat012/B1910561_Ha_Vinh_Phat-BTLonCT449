<template>
  <p class="progress-bar" v-if="isAuthenticated">Thành công: {{ progress }}%</p>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Progressbar",
  computed: mapGetters(["progress", "isAuthenticated"]),
};
</script>

<style>
.progress-bar {
  padding: 10px 16px;
  text-align: center;
  background: rgb(106, 248, 118);
  color: black;
  font-size: 1.1rem;
}
</style>
