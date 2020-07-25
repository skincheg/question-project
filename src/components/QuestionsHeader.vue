<template>
  <div class="questions">
    <div class="questions-head">
      <div v-on:click="previousClick" class="questions-head__link">
        Previous step
      </div>
      <div class="questions-head__number">
        2/20
      </div>
    </div>
    <div class="questions-line">
      <div class="questions-line__active"></div>
    </div>
  </div>
</template>

<script>
import router from "../router";
export default {
  name: "Questions",
  methods: {
    previousClick() {
      router.go(-1);
    }
  }
};
</script>

<style scoped>
.questions {
  width: 500px;
  display: flex;
  flex-direction: column;
}

.questions-head {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}

.questions-head__link {
  cursor: pointer;
}

.questions-line {
  width: 100%;
  height: 5px;
  background-color: rgb(232, 232, 232);
  border-radius: 100px;
}

.questions-line__active {
  width: 20%;
  height: 100%;
  background-color: rgb(244, 192, 23);
  border-radius: 100px;
}

@media (max-width: 550px) {
  .questions-head {
    font-size: 14px;
  }
}
</style>
