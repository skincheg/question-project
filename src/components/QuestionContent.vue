<template>
  <div class="question-wrap" v-if="question.length !== 0">
    <div class="question__text">{{ question[0].text }}</div>
    <div v-if="question[0].options.length <= 2" class="question">
      <div
        class="question__card-wrap"
        v-for="option of question[0].options"
        :key="option.id"
      >
        <router-link :to="'/' + option.routerLink" class="question__card">
          <span>{{ option.text }}</span>
          <img
            src="https://cdn-prod.unimealplan.com/quizStepChoice/b6dd4c29e98012136c9d488c729888fe.svg"
            alt="Man"
          />
        </router-link>
      </div>
    </div>
    <div
      v-else-if="question[0].options.length > 2"
      class="question question_many-cards"
    >
      <div
        class="question__card-wrap"
        v-for="option of question[0].options"
        :key="option.id"
      >
        <router-link :to="'/' + option.routerLink" class="question__card">
          <span>{{ option.text }}</span>
          <img
            src="https://cdn-prod.unimealplan.com/quizStepChoice/b6dd4c29e98012136c9d488c729888fe.svg"
            alt="Man"
          />
        </router-link>
      </div>
    </div>
  </div>

  <div v-else>
    В базе не найдено таких вопросов
  </div>
</template>

<script>
export default {
  name: "QuestionContent",
  props: ["question"]
};
</script>

<style scoped>
.question-wrap {
  width: 500px;
}

.question {
  display: flex;
  justify-content: space-between;
  align-items: stretch;
  width: 100%;
}

.question__card-wrap {
  width: 48%;
}

.question__card {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  font-weight: bold;
  background-color: rgb(245, 245, 245);
  border-radius: 10px;
  color: rgb(92, 92, 92);
  text-decoration: none;
  font-size: 20px;
  width: 100%;
}

.question_many-cards {
  flex-direction: column;
}

.question_many-cards .question__card-wrap {
  margin-bottom: 25px;
  width: 100%;
}

.question__text {
  margin-bottom: 25px;
  font-size: 34px;
  color: rgb(41, 41, 41);
  font-weight: bold;
}

@media (max-width: 550px) {
  .question__card-wrap {
    margin-bottom: 10px;
    width: 100%;
  }
  .question_many-cards .question__card-wrap {
    margin-bottom: 10px;
  }
  .question {
    flex-direction: column;
  }

  .question__text {
    font-size: 25px;
  }

  .question__card {
    font-size: 15px;
  }
}
</style>
