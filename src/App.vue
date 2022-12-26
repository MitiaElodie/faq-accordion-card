<script>
import DropdownList from './components/DropdownList.vue'

export default {
  name: 'App',
  components: {
    DropdownList
  },

  data() {
    return {
      qaList: [
        {
          question: 'How many team members can I invite?',
          answer: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.',
        },
        {
          question: 'What is the maximum file upload size?',
          answer: 'No more than 2GB. All files in your account must fit your allotted storage space.',
        },
        {
          question: 'How do I reset my password?',
          answer: 'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.',
        },
        {
          question: 'Can I cancel my subscription?',
          answer: 'Yes! Send us a message and we’ll process your request no questions asked.',
        },
        {
          question: 'Do you provide additional support?',
          answer: 'Chat and email support is available 24/7. Phone lines are open during normal business hours.',
        },
      ]
    }
  }
}
</script>

<template>
  <main>
    <div class="faq__container">
      <div class="faq__content">
        <div class="faq__img-container"></div>
        <div class="faq__question-list">
          <h1 class="faq__title">FAQ</h1>
          <DropdownList
            class="faq__dropdown-list"
            :qa-list="qaList"
          />
        </div>
      </div>
    </div>
  </main>
  <footer>
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="https://www.frontendmentor.io/profile/MitiaElodie">Anjara Mitia Elodie</a>.
    </div>
  </footer>
</template>

<style lang="scss">
.faq {
  &__container {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
  }
}

.attribution { font-size: 11px; text-align: center; }
.attribution a { color: hsl(228, 45%, 44%); }
</style>
