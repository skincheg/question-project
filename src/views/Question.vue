<template>
  <QuestionContent v-bind:question="currentQuestion" />
</template>

<script>
import QuestionContent from "../components/QuestionContent";
export default {
  name: "Question",
  components: { QuestionContent },
  beforeRouteUpdate(to, from, next) {
    console.log(to);
    this.currentQuestion = this.questions.filter(
      question => question.id === +to.path.replace("/", "")
    );
    next();
  },
  mounted() {
    this.currentQuestion = this.questions.filter(
      question => question.id === +this.$route.path.replace("/", "")
    );
  },
  data() {
    return {
      currentQuestion: {},
      questions: [
        {
          id: 1,
          text: "Select your gender",
          options: [
            {
              id: 1,
              text: "Men",
              routerLink: 2
            },
            {
              id: 2,
              text: "Women",
              routerLink: 2
            }
          ]
        },
        {
          id: 2,
          text: "Choose your age",
          options: [
            {
              id: 1,
              text: "20-30",
              routerLink: 3
            },
            {
              id: 2,
              text: "31-40",
              routerLink: 3
            },
            {
              id: 3,
              text: "41-50",
              routerLink: 3
            },
            {
              id: 4,
              text: "41-50",
              routerLink: 3
            },
            {
              id: 5,
              text: "41-50",
              routerLink: 3
            }
          ]
        }
      ]
    };
  }
};
</script>
