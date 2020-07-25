<template>
  <div id="app">
    <Header />
    <div class="questions-header">
      <QuestionsHeader />
    </div>
    <div class="questions">
      <router-view />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import QuestionsHeader from "@/components/QuestionsHeader";
export default {
  name: "App",
  components: {
    Header,
    QuestionsHeader
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

* {
  box-sizing: border-box;
}

body {
  font-family: "Roboto", sans-serif;
}

.questions-header {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}

.questions {
  width: 100%;
  display: flex;
  justify-content: center;
}

@media (max-width: 550px) {
  .questions-header {
    margin-bottom: 20px;
  }

  #app {
    padding: 0 15px;
  }
}
</style>
